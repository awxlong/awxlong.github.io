---
layout: distill
title: "CureSeek: Quantized LLM Therapeutic Agent"
date: 2025-08-31 15:42
description: my code for the CUREBench competition on training LLMs for therapeutic reasoning via external tools
tags: research
categories: blog-post
disqus_comments: true
related_posts: true
authors:
  - name: Xuelong An
---

# CureSeek Therapeutic Agent: Code for CURE-Bench

We participated in the [CURE-Bench competition](https://www.kaggle.com/competitions/cure-bench) on therapeutic reasoning via external tool usage with LLMs, and we open-source our code at https://github.com/awxlong/cureseek_therapeutic_agent.

Our approaches emphasizes affordability on low computational budget:

1. We first tried supervised-finetuning a Qwen-distilled, quantized [DeepSeek-R1](https://www.kaggle.com/models/deepseek-ai/deepseek-r1/transformers/deepseek-r1-distill-qwen-1.5b) of 1.5 billion parameters. The competition has no training data, and the validation data has no reasoning traces before arriving to an answer. We annotated validation data by using both quantized [TxAgent](https://huggingface.co/mradermacher/TxAgent-T1-Llama-3.1-8B-GGUF) and prompting DeepSeek-R1-distill-qwen-1.5b to explain how to arrive at the correct answer for questions in the validation set. Please see [experiments/self_correction_deepseek.py](experiments/self_correction_deepseek.py) where we perform batch inference of input validation data. 
      
      1.  This augmented validation set was treated as our 'training' set to fine-tune a base DeepSeek-R1-distill-qwen-1.5b, and the code is in [experiments/sft_deepseek.py](experiments/sft_deepseek.py), and the supervised finetuning pipeline is mainly elaborated upon https://www.kaggle.com/code/danielphalen/grpotrainer-deepseekr1. This approach didn't seem to work. Inference with base DeepSeek-R1-distill-qwen-1.5b yielded higher test score, suggesting fine-tuning may have impaired its internal reasoning. 

2. We next tried simply performing inference with quantized TxAgent, which yielded a score close to the competition's baseline of $0.5$. Please check [experiments/quantized_txagent_inference.py](experiments/quantized_txagent_inference.py). The code is written to support multiprocessing to speed up inference on Kaggle.
       
      1.  Inference with quantized TxAgent leads to many `No answer` entries as the model requires external tools to find out more information about novel drugs, their contraindications, their recommended dosage, among others, prior to inferring an answer. Nonetheless, because we are constrained by computational budget, we aimed at keeping answers within $2048$ tokens, so we didn't use the original [TxAgent](https://github.com/mims-harvard/TxAgent) which is very, very computationally expensive (e.g. recommended H100 GPU usage with more than 80GB of memory and maximum tokens of $>90000$). 
      
      2. To keep inference affordable, we needed to feed information on drugs that TxAgent didn't know about. To do this, we first use the above DeepSeek-R1-distill-qwen-1.5b to extract relevant drug entities in the test questions; please check [experiments/entity_extraction_deepseek.py](experiments/entity_extraction_deepseek.py). We use the extracted entities to construct (complex) queries which can be used to retrieve information about drug entities from the European PMC and PrimeKG; please check [experiments/rag_context_augmentation.py](experiments/rag_context_augmentation.py). 

      3. The extracted information served as 'augmented' context to do RAG-based inference for a second time on 'No answer' entries using quantized TxAgent with [experiments/quantized_txagent_inference.py](experiments/quantized_txagent_inference.py). This raised the test score a little bit. We didn't have enough time anymore, so for remaining `No answer` entries we simply filled them in via similarity-based semantic search using Qwen2-1.5B-instruct. This consists of extracting embeddings of the partial answer of quantized TxAgent, then measuring its cosine similarity with each of the MCQ answers and outputting the one with the highest similarity. This raised the final test score accuracy to $0.42$; please check [semantic_search.py](semantic_search.py).   

We are wondering whether there exists a very simple solution to this complicated CURE-Bench benchmark, perhaps by simply doing online RAG (searching Google via an API), and then using a quantized TxAgent to reason over the search results...