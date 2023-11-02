---
layout: post
title: The many interpretations of terms in artificial intelligence #a post with bibliography
date: 2023-11-01 09:42:00-0400
description: Some thoughts concerning how to interpret quotidian words appearing in AI research in a non-quotidian way. #an example of a blog post with bibliography
tags: food-for-thought
categories: blog-post
disqus_comments: true
related_posts: true
toc:
    sidebar: left

# related_publications: einstein1950meaning, einstein1905movement
---

I bumped into this paper on [X (formerly Twitter)](https://twitter.com/ChristophMolnar)
{% twitter https://twitter.com/ChristophMolnar/status/1718921189333045752 %}

In today's post, I don't want to discuss interpretability or explainability, but rather elaborate on the above idea that in the AI literature, different authors express completely different ideas despite using the same words, often words that appear in our daily parlance, yet acquire uncommon interpretations. 

If you have just set foot into the world of artificial intelligence, here are my thoughts and advices on navigating this exciting, but often messy landscape. 

# Terms

#### **Explanation, hypothesis, model**

When I began studying AI, the word "model" elicited the mental imagery of a 3D scale model of something. If I wanted a "model" of an atom, I could pick some recycled styrofoam balls, stick them together and, bam (pun intended), an atom is synthesized. 

Nowadays it mainly refers to a equation or function with some parameters $\theta$, where a 'good' model is defined as having optimal parameters $\theta$ that can make predictions with low error on the training and (hopefully) unseen, test data, compared to a 'bad' model. 

In rare cases, such as in [Prof. Joshua Tenembaum's talk on Cognition](https://www.youtube.com/watch?v=NsID1iM8gRw), a (physics-) model can refer a simulator implemented in Unity.  

#### **Knowledge** 

This word may cause some confusion to peers with a philosophy or psychology background. At least to me, prior to studying AI, 'knowledge' meant pieces of information encoded in natural language, e.g. "Mount Chimborazo is actually higher than Mount Everest" somewhere in the brain. I don't know how, nor where, nor whether it is encoded in natural language. 

At least in the early days of AI, first order logic constraints such as `smoker(X) :- edema(X)`, read as "it is true that if X is a smoker, then X has edema", does resemble 'knowledge' encoded in a way that seems familiar to us. 

However, this is not always the case. The word 'knowledge', such as in 'prior knowledge', mainly used in Bayesian modelling, has not much to do with logic predicates or natural language. It mainly refers to what you believe on the distribution of the parameters of your model come from before your model is trained on any data. If you think your model must be parametrized by weights that more often take extreme values, you can set a prior belief with distributions with heavier tails. Guidance on what prior distributions can be used to describe your parameters can be checked in this [tweext](https://twitter.com/bindureddy/status/1708664380987220427) 

Lastly, sometimes researchers may even say that 'knowledge' of the data is encoded in the parameters of the model, which leads us to the next section:

#### **Explainability and interpretability**

Explainability and interpretability are terms that can be used interchangeably, as shown in the above paper. I avoid making a distinction in this post, and just focus on sharing what is usually meant by either term.

The simplest manifestation of explainability can be observed with simple linear models like linear or logistic regression. Here explainability simply refers to the presence of coefficients estimated per each input variable of the model. These coefficients' magnitudes often denote the contribution of the variable to the overall prediction of the model. Other non-linear, machine learning models such as decision trees are by design explainable, and such quality mainly refers to the thresholds appearing at each junction in the decision trees. 

Concerning deep learning, particularly convolutional neural networks (CNN), explainability can refer to the computation of feature maps on the input space to see on average, what are the filters of the CNN observing when solving a task like classification given an image. Deep generative models (DGM) that leverage neural networks and learn latent representations of the data can also become 'explainable' if there is some post-hoc (i.e. after training) processing of embeddings, such as dimensionality reduction through principal component analysis, that can map the embeddings on 2D space. In such space, it is hoped that the DGM learns disentangled features, albeit how are they interpreted is mainly up to the researchers, not by some objective reason. 

Explainability in the eyes of some authors may also refer to the capability of the researcher to compute a numerical value of the likelihood of the parameters of the data, or at least an approximation of it, such as the evidence lower bound. This scalar value can be used to compare the performance of different models, and these models can thus be referred to as "provable".  

Other authors may also define explainability when deep neural networks, despite being black boxes, can accept inputs or display its predictions through a user-friendly interface that allows them to interact with the model. 

# Bottom line

My key advice in this brief article is to convince you not to trust the "intuitive" interpretation of a word, especially if it is used on a quotidian basis. For example, in my personal view, to be "explainable" means to be able to justify its own answer. Just like a friend to whom I ask why didn't they go to a concert by singer Aimer, to be "explainable" (at least when referring to the common meaning of this word in daily life) means that they can give a justification as to why didn't they go (maybe they became sick, or admit they have poor taste in music). 'Explainable' in the machine learning literature has not much to do with this daily life interpretation. 

Finally, the above terms are simply the tip of the iceberg. In the wider research literature, authors can diverge in what they mean by on many terms such as "language", the word "intelligence" itself, and more controversial terms like "artificial general intelligence". Because I don't know the precise meaning of them myself, I refrain from commenting furthermore. 

Happy learning!


