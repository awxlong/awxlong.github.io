---
layout: distill
title: Thoughts on David Deutsch’s The Beginning of Infinity #a post with videos
date: 2023-01-20 21:42:00
description: my review of the book The Beginning of Infinity by David Deutsch grounded on the topic of artificial intelligence. #this is what included videos could look like
tags: books-review
categories: blog-post
disqus_comments: true
bibliography: 2023-my-main-refs.bib
thumbnail: assets/img/begin-infty.jpg
authors:
    - name: An Xuelong
---

<figure>
  <img src="/assets/img/begin-infty.jpg" alt="Figure couldn't load due to an unknown error. Sorry.">
  <figcaption id="chatgpt">
    Cover of the book The Beginning of Infinity, extracted from https://www.amazon.co.uk/the-beginning-infinity-explanations-transform/dp/0140278168 

  </figcaption>
</figure>

_The Beginning of Infinity_ is an enlightening book by David Deutsch. It sheds light into the nature of scientific progress, which consists not of extrapolating past successes, but rather exploring unanswered questions and propose a plethora of hypotheses in order to advance knowledge through trial and error. 

The Black Swann Philosophy[^2] is perhaps a central tennet in Deutsch's book. Namely, concerning the successful theories which try to explain certain phenomena in the real world, we should not ask why are they good, but rather how are they bad and how can they change to improve their causal, explanatory power. 

In order to make progress in any scientific field, we have to ask new and harder problems each time. Because any solution given to these problems is theory-laden[^1], to improve on theories we need new problems which guide new theories. The path to a good answer or theory is not straight, but rather bent. In searching for a good theory/explanation/answer to a problem, we may have to take a detour in identifying tangential problems that could, maybe luckily, help us answer an original question. 

This has made me reflect on how we should make progress in artificial intelligence. On one hand, we can gaze at the current successes in the history of AI and expand on deep learning. 

Well, ever since the start of the 21st century, thanks to the increase of computational power and omni-presence of data, what used to be small neural networks that could only approximate Boolean logic or very small-scale digit recognition have scaled up to large deep learning models which are achieving state-of-the art performance on several benchmarks meant to measure a certain faculty of human intelligence: human vision or NLP through QA. What empowers these results are the well-deserved research poured into deep learning which explore novel architectures, and optimization techniques, thus redefining the new state-of-the-art performance on several canonical benchmarks. See for instance how interest on deep learning have increased six-fold over the past decade according to <d-cite key="zhang_2021_chapter"></d-cite>.

From this trend of successes, one can ask: how can we go beyond current state-of-the-art performance? Successes in deep learning suggest that we can further extrapolate deep learning’s infrastructure, which should map to increases in functional performance. See an analysis done <d-cite key="kaplan_2020_scaling"></d-cite> on neural language models, which showed that language modeling performance improved smoothly as the neural model's size, dataset size, and amount of compute used for training increased. We can refer to this idea of scaling deep neural networks as the scaling hypothesis:


However, careful observers have noted that there are some very problematic caveats to the scaling hypothesis. It’s the (ignored) elephant of in the room. Namely:

1. brittleness due to inability for robust generalization beyond the training set distribution, 
2. lack of explainability tied to the lack of computational semantics, 
3. and lack of parsimony due to this evident over-reliance to big data, and unacceptable levels of computational power consumption as argued by Garcez & Lamb, (2020)
4. benchmarks with misleading metrics of success and design. For example, ImageNet contain biases such as object-centric bias, i.e. images tend to show the object to be classified centred, without being rotated, well-illuminated, and without confounding objects <d-cite key="barbu_2019_objectnet"></d-cite> 


Given the current issues, we can return to the original question of can we make further progress in AI. Thanks to David Deutsch's book, I feel like we shouldn't rely only on extrapolating current successes, i.e., scaling current transformer-based models and hope for the emergence of intelligence. 

We may have to revisit the original questions that kickstarted the field AI, revise our underlying assumptions, and propose novel hypotheses: 

- what can we do beyond prediction error minimization with neural networks? Or what is something novel we can do in addition to learning how to regenerate a given dataset?
- what can we do to optimize search during logical deduction over a combinatorial growing space of pieces of knoweldge? 
- what consitutes a good representation of data? Do we even _need_ a representation of the data?


[^1]: My interpretation of "theory-laden" is that we can only formulate hypotheses based on the conclusion we want to reach. Thus, in order to reach novel conclusions, we have to endlessly hypothesize. Hence the book's title is The Beginning of Infinity.  

[^2]: the Black Swann Philosophy gears us to think that a good theory not only explain why a natural phenomena happens this way, but also why it doesn't happen in another way. The story behind it is that if you want to prove that all swans in the park are white, you shouldn't think about searching only for white swans, but also actively look for black ones. If actively trying to disprove your hypothesis fails, then your hypothesis is robust to counter-arguments.  