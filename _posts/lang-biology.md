---
layout: post
title: The interesting analogy between language and biology
date: 2023-11-21 12:42
description: comments on the interesting parallels that surface in NLP and computational biology, and how each informs about problems and solutions about each other
tags: research food-for-thought
categories: blog-post
disqus_comments: true
related_posts: true
authors:
  - name: Xuelong An
toc:
  sidebar: left
thumbnail: /assets/img/alphafold-pipeline.png
  
---
# On the interesting parallels of language and biology: a taster

<!-- Reading an interesting paper by Lauren, 

Hi Antonio, I have a question on VAEs. -->

There are interesting parallels between language and biology. As a result, problems surfacing in natural language processing (NLP) tasks, may well inform us about possible problems and solutions in computational biology. 

The simplest common denominator to observe the parallels concerns the analysis of sequences: algorithms and modelling paradigms like recurrent neural networks and self-attention in transformer that help process a sequence of words to solve a task like text classification can surprisingly work with sequences of genes to classify what disease does an RNA sequence correspond to. This is because at a computational level, a string of nucleotides (adenine (A), thymine (T) or uracil (U) in RNA, cytosine (C), and guanine (G)) can be [represented as a sequence of letters](https://www.sciencedirect.com/science/article/pii/S2001037021000945). 

Another common point concerns the representation of words and biological entities. It would not suffice to represent a word like 'airplane' based solely on this string (i.e. this symbol) so it is common to use a fixed-size embedding vector to denote it. This be extracted from open-source libraries like GLoVE and word2Vec. In parallel, molecules also have expert-coded or learnt [molecular fingerprints](https://pubs.acs.org/doi/epdf/10.1021/acs.jcim.9b00237) as vector embeddings which are readily available in RDKit. Another case is that of obtaining embeddings for biological entities. A gene can be treated as a vocabulary token, while a cell can be treated [as a sentence](https://www.biorxiv.org/content/10.1101/2023.04.30.538439v1.full.pdf). Another work on a similar vein is [Cell2Sentence](https://www.biorxiv.org/content/10.1101/2023.09.11.557287v2), where gene expression (single-cell transcriptomics) is treated as text. 

# Language-agnostic grammar: structure for language and biology 

<!-- Another important i

A priori we need to distinguish between  -->
Inspired by Chomsky's linguistics, there is work on learning a language-agnostic tree-like structure to learn embeddings of text, called [Self-Structured AutoEncoder](https://arxiv.org/abs/2305.05588). This tree-like structure combines bottom-up composition of local contextual embeddings with top-down decomposition of fully contextual embeddings to learn in an unsupervised routine. Self-StrAE achieves competitive autoencoding performance with respect to a LLM, BERT-Based variant, denoting its low parameter efficiency that reflects the parsimonious nature of grammar.

Given the parallels with language, it is interesting to explore how would it work if Self-StrAE is applied to a DNA, or RNA sequence. What will the learnt structure tell us about the DNA sequence. Learnt embeddings would shed light into sequences of DNA which may have fucntional similarities. The compositions found by Self-StrAE would also find sequence motifs, which are short recurring patterns of DNA that map to specific biological functions like protein docking, because of frequent coocurrence leading to similar embeddings.     
<!-- 
how would it work with genes? will it compose motifs -->
# Language respects constraints, so does biology

Another interesting parallel are the constraints underlying both generation of sentences and biological entities/processes.
 
Imagine that you want to generate sentences. You have a collection of sentences to train a probabilistic model on. Because we can't control what the probabilistic model learns from the given data, how do you make sure you don't generate an ungrammatical sentence like "jogging Octopie went", where we have a "verb-subject-verb" structure. The simplest way would be to set up a hidden template like "subject-verb-object"[^1] in order to offset portion of the probabilistic model's support[^3] to not put any probability mass to structures other than "subject-verb-object". Given this, this will first guarantee that sentences follow the correct grammar rules, and second guide [learning](https://awxlong.github.io/blog/2023/sgd/) since the model is not exploring over the whole parameter space, but only that which conform to the supplied template. 

Consider the following analogous task, given some atoms like hydrogen, carbon, oxygen, among others, you want to train a probabilistic model to predict the angle of rotation when such input atoms are assembled together into a compound. This could be relevant for a 3D reconstruction of an assembled molecule. You have a dataset of different atom-atom compounds with their associated rotation angles.  If you only rely on learning, then the resulting probabilistic model may put probability mass on biologically implausible rotation angles, even if that implausible probability mass is negligible. In the end, statistics is just about counting and averaging, meaning that even if you only see that some compound like water has a bond angle of around [105 degrees](http://witcombe.sbc.edu/water/chemistrystructure.html), the model's support would still put probability mass in-between 0 or 200 degrees [^2]. Enumerating all possible rules concerning rotation angles would be impractical, so one can resort to biomedical ontologies.

Arguably, this is how DeepMind's AlphaFold ensures that proteins generated from DNA input sequences are biologically plausible, as can be observed in the model's pipeline. In it, the input sequence first goes through a database search that is subsequently converted into embeddings used to generate the protein structure. Without this first phase, this probabilistic model may output proteins that resemble the ones observed during training, at the risk of following impossible configurations.     


<figure>
  <img src="/assets/img/alphafold-pipeline.png" alt="Sorry, an unanticipated error occured and the image can't load." width="100%" height="auto">
  <figcaption id="afold"> Structural constraints in the first phase concerning genetic database search and structure database search ensures that rotation angles of bonds in the compounds of the protein are biologically plausible, setting structure in learning. Figure extracted from https://www.nature.com/articles/s41586-021-03819-2 </figcaption>
</figure>

Generating implausible proteins, or invalid angle rotations between bonds is akin to generating sentences that violate grammar rules. 

It is debatable whether the rules can be learnt from data. Rather, the role of rules and constraints might be to shape learning. 

are programs the language for thought for computers, if so how NLP mahines aid biological scientific discovery.  

For further thought experiments, imagine whether a model can learn what are the rules of programming languages by only observing code, or infer the rules of grammar from just observing written text. 

Structural 

So I know that autoencoders are able to learn embeddings of the training data, however the training data is usually "static". Imagine now that the training data has a temporal dimension, and measures features that change over time of, say, a cell. Is there work that trains a "recurrent" VAE such that it can learn embeddings that are dependent on time? so if I want to visualize the embeddings, they change depending the time step in which I access them.

Does this make sense?

Lorenzo recommended VAEs that disentangle features of the input, such as a $$\beta$$-VAE, and see whether it can disentangle time. however, the paper he shared mainly worked with celebA. While there are multiple images of faces, each face is just a "snapshot", so maybe the VAE learns to disentangle noses from eyes from mouths, but not necessarily how they can change over time. Also, I'm not thinking of working with images. I'm thinking of tabular data that measures the features of multiple cells across time. 

# NLP inspiring future biomedical research directions


A dictionary with mostly indisputable grammar rules are akin to biological ontologies like the Gene Ontology 
An interesting thought experiment hence, is can this grammar be expanded given the text available, analogous to asking whether 

<figure>
  <img src="/assets/img/expand-ontology.png" alt="Sorry, an unanticipated error occured and the image can't load." width="100%" height="auto">
  <figcaption id="ontology"> .  </figcaption>
</figure>

Mutations as contradictions? -> this sentence "this sentence has five words" has five words

For example, challenges in NLP involve processing a sequence not only forward, but also backward. Consider the sentence: "shift two positions backward of each letter of the word 'trapelo' per the alphabet to decode it", where it is needed to read the sentence back and forth to process the word. Do we have to read a genome forward and backwards?
# Final thoughts
I believe that because we can natively read Human language, research on NLP is more commoditized and well-received by the public than computational genomics, despite the parallels outlined above. I think it is worth for me and anyone interested in computational biology to closely follow the research literature on language modelling to draw inspiration ofr DNA/RNA sequence modelling.  

Finally, I leave you the following thought experiment: we humans can only read human language. While we can not natively understand the language of biology, our AI-based tools can understand them. Statement paraphrase from Demis Hassabis's [statement](https://www.youtube.com/watch?v=Gfr50f6ZBvo) that 'AI may just turn out to be the language to describe biology'

If you have answers, share thoughts, you can leave a comment or please email me!

[^1]: Sentences don't follow this simple template, but it helps get the idea across that placing structure into the support of a probabilistic model helps guide learning.  
[^2]: While it is true that some bonds between atoms like a carbon-carbon bond have no restricted rotation angle, others like a [hydrogen peroxide](https://www.sciencedirect.com/science/article/pii/S0022285217302990) is constrained to a setting of rotation degrees (with some uncertainty).  
[^3]: A probabilistic model's support refers to the domain of values for which the output of the model is non-zero. 