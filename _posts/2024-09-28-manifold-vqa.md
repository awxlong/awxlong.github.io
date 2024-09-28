---
layout: distill
title: "Ideas on transitioning from monolith to manifold of models"
date: 2024-09-28 15:42
description: my thoughts on a visual-question answering pipeline inspired by the Society of Minds
tags: research
categories: blog-post
disqus_comments: true
related_posts: true
authors:
  - name: Xuelong An

thumbnail: /assets/img/publication_preview/inference_m3g.png
---

# From monolith to manifold

The common trend in deep learning is to propose a single model which can achieve SoTA performance on some well-established benchmark. However, models proposed which achieve high performance in different benchmarks carry their advantages and limitations. For example, a VQA model with a vision encoder pretrained on rare skin lesions may answer queries more accurately from patients with these edge cases, but perform badly on common lesions. Another VQA model (which could be an ablation of the former) may perform better at spotting normal skin lesions and perform badly on rare diseases. A question which arises is how can we combine their strengths and address each other's limitations, akin to members of a team compensating for each other's level of expertise. One approach is to combine multiple VQA models to leverage their interoperability so that they can discuss with each other as proposed in https://nips.cc/virtual/2023/76544, transitioning from a monolith model to a manifold of models. The proposed training and inference regime is very similar to the work of García and Lithgow-Serrano, (2024) found in https://aclanthology.org/2024.clinicalnlp-1.45.pdf, where the difference lies in that we propose multiple VQA model responses, instead of responses from a single VQA model, to be summarized by a powerful LLM.

<figure>
  <img src="/assets/img/training_m3g.png" alt="Sorry. Image couldn't load." width="100%" height="auto">
  <figcaption id="train">At a) we extract features from the question Q which is constructed differently per each language model, and from the stack of images I . At b) we fuse the features to be passed to the language model for free-form answer prediction. At c), each VQA model outputs an answer via greedy search (or beam search with a width of 1 ), and is trained by minimizing the cross-entropy loss function between ground-truth tokens and the predicted tokens. In the illustration we depict prompts in Spanish.</figcaption>
</figure>

We take into account memory efficiency, and as such we implement model compression techniques for memory efficiency during fine-tuning, which includes 1) mixed-precision and 2) gradient accumulation to simulate mini-batch gradient descent. Answers are generated via greedy-search. 

<figure>
  <img src="/assets/img/publication_preview/inference_m3g.png" alt="Sorry. Image couldn't load." width="100%" height="auto">
  <figcaption id="inference">Similar to training's stage a), we extract features from the question and images, and fuse them at b) so that at c) each of the language models output a list of answers. At d), the answers of each VQA model is put as context for a prompt to a LLM, where we query for a concise answer that accounts for the different diagnoses offered by each model. In the illustration we depict prompts in Spanish.</figcaption>
</figure>

With memory efficiency concerns, the LLM is 1) quantized, 2) input tensors are loaded with 16-bit precision, 3) and a beam width of 1 (greedy search) is used for answer generation. The code is found at https://github.com/awxlong/manifold-medvqa/tree/main

