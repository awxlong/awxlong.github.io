---
layout: post
title: Paradigms of AI modelling #a post with bibliography
date: 2023-07-12 09:56:00-0400
description: I share five different paradigms of modelling intelligence #an example of a blog post with bibliography
tags: food-for-thought
categories: blog-post
disqus_comments: true
related_posts: true
thumbnail: /assets/img/5-paradigms-int-ver-beta.png
# related_publications: einstein1950meaning, einstein1905movement
---


Throughout the 7 decades of the pursuit of artificial intelligence, this field has mainly dealt with the fundamental issue of knowledge representation and processing. Here are some modelling paradigms of AI:


# Symbolic reasoning
- Symbolic modelling is based on the following assumptions (see [The promise of AI](https://mitpress.mit.edu/9780262043045/the-promise-of-artificial-intelligence/) by Bryan Smith, chapter 2 on its history):
    - The core of intelligence is thought
    - Thought can be modelled using logic inference
    - Logical inference is performed over an ontology of the world: objects in the world are defined by their properties and relations to one another. 
    - Low level perception of features is less difficult to model than logical inference (it's not that it is easy)   
- What are symbols? Consider them logic predicates and ground atoms
    - Symbols can’t be differentiated
- It takes a non-functional approach to modelling; a simple set of rules can lead to rich and diverse output via recursive application of those rules (consider rules of grammar of certain language or a programming language). 


# (Probabilistic) function approximation 
- Probabilistic modelling is based on the assumptions that:
    - A model that learns from training distribution can generalize to unknown distributions  
    - Vectors/numbers (also called subsymbols), instead of symbols, represent information in the world and thought. Think about measurements of pixel intensity values representating a 'cat' (a mental imagery), instead of the word 'cat'. 
- A parametrized model finds a set of features that can map inputs to a set of outputs via prediction error minimzation. 
    - Finding the parameters of the function is done via statistics, which is essentially counting and averaging. In some sense, one can say that an unknown distribution of data is assumed to be an average of known training data. 
    - This funtional mapping is always done from infinite domain to finite or infinite range, but never from finite domain to infinite range. 

# Reward reinforcement 
- Rather than a representation of knowledge, reinforcement learning is more about a representation of actions and decisions.

- A Reinforcement learning model comes as a set of tuples: agent, actions, rewards, states, and how to transition among states of an environment.

- The main goal is to maximize reward given the current state, which can be either achieved via rules or via function approximation. 

- A core process in reward reinforcement is about searching, a pursuit of novelty. 
    - Reward reinforcement is not about minimizing the divergence to a training distribution, but rather explore. 

- Reinforcement learning, by itself, is loosely related to thought, but more about acting. 

# Causal graphs

- Knowledge is represented via abstractions of entities and how they relate to one another. 

- The nodes and vertices can be stored in a way that they allow for a causal interpretation, i.e., antibiotic causes stronger immune system.
<!-- - 
- Functional approach to modelling, but given the way in which information is stored, it allows causal interpretation of information beyond correlation.  -->

# Meta

- The core idea is modelling about modelling 
- Meta learning, which involves automatically fine-tuning parameters
- Consider genetic algorithms that modify the topology of a network, such as [novelty search](https://link.springer.com/book/10.1007/978-3-319-15524-1)

# Mergers

The above models can be assembled together to expand the capabilities of each, hopefully without compromising each other's strenghts while mitigating their respective weaknesses:

- Knowledge graph embeddings
- [Spatio-temporal And-or graphs](http://www.stat.ucla.edu/~sczhu/Books/Book_2_Parsing.pdf)
- [Deep reinforcement learning](https://www.nature.com/articles/nature14236): so that a RL agent builds a representation of the environment and then act
- Heuristic-driven machine learning methods
- Neuro-symbolic AI
- Can you merge them all? See [_The Master Algorithm_](https://www.amazon.co.uk/Master-Algorithm-Ultimate-Learning-Machine/dp/0141979240) by Pedro Domingos


<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/5-paradigms-int-ver-beta.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A depiction of unification of the above 5 paradigms
</div>
