---
layout: distill
title: "Are you Clever Hans or are you actually clever, Hans?" #a post with videos
date: 2023-01-12 21:42:00
description: my (mostly satirical) comments on ChatGPT and Gato, large, transformer-based models that shook the AI community on 2022  #this is what included videos could look like
tags: food-for-thought
categories: blog-post
bibliography: deep-med.bib
---

**Author's update on October, 2023**: I wrote this satirical article a few months after Gato and ChatGPT's release, particularly after having some conversation with ChatGPT. Nowadays, a few of the claims, such as in [Figure 1](#chatgpt), I made back then are less valid. GPT-4 (although it is paid) can now retrieve information online, meaning it _can_ synthesize valid links. It can also solve math problems more accurately. This is partly because for prompts about calculations or theorem proofs it can retrieve an answer from online calculators or provers like WolframAlpha, in addition to its own improvement due to scaling. I'm still skeptical scaling this architecture is the right way forward, but maybe I'm delusional and LLMs are the next step forward for AI...


Somewhere, an influential research group from a highly respected academic sphere published a report that the model they have designed has gotten us humans closer to AGI. They named it HANS, short for Human ANd Smart, and documented that the model consists of a generalist agent who can multi-task: it can play a series of Atari games which denote its ability to interact with a digital environment, hold a quotidian conversation which reflects its dominion of Human English Language, and caption images to show its prowess in image recognition. Because the model was built using a single transformer neural network trained on diverse data, it was originally advertised as evidence that the path to AGI is clear: create a bigger model trained on a larger dataset. Media communicators, however, may have “misunderstood” the message (either intentionally or not), and instead transmitted the overhyped sentiment that this model was a precursor to AGI and suggested it would bring with itself a lot of existential crisis to the unprepared Human society. In the end, what better way to endanger humanity than predicting the next output given some input.

Furthermore, they claimed that there were primitive signs of sentiency in the model after one of the research engineer held and released a private conversation transcript with him/her on topics about physics and emerged from it convinced that he was talking to a 7-8 years old child. 

The above hypothetical scenario is an amalgamation on real-life cases of research groups from Google who have designed models resembling some degree of Human Intelligence on very constrained areas such as multitasking or domain-specific conversation. Please see Gato, a multitasking agent designed by <d-cite key="reed_2022_a"></d-cite> and a subsequent report documenting what it is and what effect it instigated in the public <d-cite key="heikkil_2022_the"></d-cite>. I’ve also included the articles by <d-cite key="sparkes_2022_has, tiku_2022_the"></d-cite> where they have reported on how Google left one of its engineer on paid administrative leave for making claims that one of its language models, called LaMDa, was sentient as a 7-8 years old child after holding a conversation with it on [physics](https://www.technologyreview.com/2021/05/20/1025135/ai-large-language-models-bigscience-project/). I’ve modified some names, such as changing Gato's name to HANS to fulfil the (very) important goal of making a pun in the subtitle. 

Gato, ChatGPT and other enormous, pretrained transformer-based neural networks are mostly arcane models which are inoperable to the common citizen not endowed with high-end computing hardware and software. Their release ignited a catharsis of emotions amongst the public. From opposite sides of the spectrum, there were those who aggrandized their anxiety over existential threats, and there were those sceptics who pointed out that such claims were, essentially, non-sensical. A model that is trained on conveniently, readily available, vast-amount of high-quality compiled dataset reflect not its generalizing capability but rather its overreliance on data, lack of parsimony and the ever-present issue of explainability with these black-box models. Another interesting set of issues is the inconsistent inability to do math, as displayed by ChatGPT:

<figure>
  <img src="/assets/img/chatGPT-math.png" alt="Figure couldn't load due to an unknown error. Sorry.">
  <figcaption id="chatgpt">
  
Figure 1: GPT-3-powered model like ChatGPT can't do math properly, probably because it doesn't understand the notion of algebra, geometry, calculus, among other branches. ChatGPT also fail to provide correct or real links to websites, as well as can't carry out instructions like "don't say anything". 

  </figcaption>
</figure>


In general, GPT-3 powered large language models may struggle to synthesize deterministic output: those of universal nature, i.e., doesn't change regardless of context. Examples include math equations (as shown above), or links to websites. 

Hence, there exist at least some scepticism who wonder whether the model HANS is actually clever, or whether it’s simply reminiscent of clever Hans.


<!-- 
This is an example post with videos. It supports local video files.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/pexels-engin-akyurt-6069112-960x540-30fps.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="assets/video/pexels-engin-akyurt-6069112-960x540-30fps.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    A simple, elegant caption looks good between video rows, after each row, or doesn't have to be there at all.
</div>

It does also support embedding videos from different sources. Here are some examples:

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="https://www.youtube.com/embed/jNQXAC9IVRw" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="https://player.vimeo.com/video/524933864?h=1ac4fd9fb4&title=0&byline=0&portrait=0" class="img-fluid rounded z-depth-1" %}
    </div>
</div> 

-->