---
layout: post
title: On the Turing Test and Large Language Models
date: 2023-12-09 09:42:00
description: I argue we Humans are more than next-state prediction machines. 
tags: food-for-thought creative-work
categories: blog-post
disqus_comments: true
related_posts: true
thumbnail: /assets/img/llm_shouting.jpg
toc:
    sidebar: left
---

# On benchmarks of Human intelligence

There is a plethora of claims surrounding the emergence of actual or surpasssing Human intelligence by Large Language Models. One, by one, these contextualized autocomplete models are given the labels of having [working memory](https://arxiv.org/abs/2305.03731v2), [compresses](https://analyticsindiamag.com/text-is-a-projection-of-the-world-says-openais-sutskever/) a ["world model"](https://www.linkedin.com/posts/armand-ruiz_llms-do-more-than-predict-the-next-word-activity-7134512576318623744-7BlG?utm_source=share&utm_medium=member_desktop), "signaling sparks of Artificial General Intelligence


There are a list of benchmarks backing up their claims. These benchmarks come with questions-answers pairs, where high performance signifies that a model can 
However, most if not all benchmarks are tailored for what LLMs can do, even though they're supposed to be designed without having LLMs in mind. A benchmark that tests a faculty of Human Intelligence like "reasoning" should not only explore define reasoning as  . This is in contrast to designing theory-laden benchmarks. No one knows the exact definition of Human capacities like "reasoning", so the design of a benchmark must have assumptions on what are the definitions of whatever capacity it is measuring. The key argument of the present article is that such assumptions have been constrained to framing every faculty as the prediction of the next token, where token can be the next word, image or audio signal. I don't even know what faculties like "memory", "reasoning", "planning" are. But I do know as many researchers may conclude after years of work on this, that it is _not just contextualized, next-state prediction_.   

Because all benchmarks have been designed based on next-token prediction, it is not surprising that a next-token predictor can perform well. Quiet the opposite, it would be surprising if a next-token predictor can't perform well on an auto-regressive task. However, while Human Intelligence most likely consists of next-token prediction, it would be misleading to suggest it _only_ consists of this process. By that line of thought, LLMs haven't even passed the Turing Test, at least by its [original formulation](https://en.wikipedia.org/wiki/Computing_Machinery_and_Intelligence). This is because while it is true that the original objective was for a machine to imitate a human and fool an interrogator, a feat that LLMs can already achieve by producing text that is indistinguishable from Human-produced text, it is often ignored that the Turing Test is executed via a _physical_ exchange of written letters. I don't think this is a trivial matter that can be glanced over, as it is very important to note that LLMs can not write, since they are not instantiated in spacetime, nor have a body with which they have to face the challenge of sensorimotor control in a continuous feedback loop.   


A benchmark of a faculty of Intelligence shouldn't be designed with only one theory of what Intelligence is, i.e., prediction of next-token. This kind of practice is akin to framing questions based on the answer one expects, instead of asking open-ended questions for the sake of curiosity. As such, if I may borrow the sensationalist attitudes of some media personalities, I just want to say "all these benchmarks are wrong, and none of them are useful[^1] to understand Intelligence". 

## Prediction Error Minimization is a strong hypothesis, not overarching

I do want to clarify: I think [prediction error minimization (PEM)](https://www.fil.ion.ucl.ac.uk/~karl/Whatever%20next.pdf) as an integral part of Human intelligence is a resilient hypothesis. Active inference, for instance, states that our brains are constantly predicting the source of the signals we perceive, and consciousness is the result when we infer that the cause of some signals in the environment is caused by ourselves. PEM also tries to explain other phenomena like dreaming, arguing that it is a form of "reverse-learning" that consists of a process of flushing irrelevant memories to while strengthening important synaptic connections, altogether allocate mental resources to make better predictions afterwards. Another important strength of the PEM hypothesis is that the abstract process of "learning" is grounded to physical mechanisms like chemico-modulated, neuronal activations.  I believe these are very strong hypothesis that can withstand harsh criticism. I simply think PEM is not enough to explain the entirety of the Human condition. 

<figure>
  <img src="/assets/img/llm_shouting.jpg" alt="Sorry, an unanticipated error occured and the image can't load." width="100%" height="auto">
  <figcaption id="llm"> Image generated by Dall-E powered MS Bing Image Creator given the prompt "a large language model shouting" </figcaption>
</figure>

My main criticism of PEM is that while it is designed to explain Human intelligence, it seems that it makes no distinction between non-Human animal intelligence and Human intelligence. The non-Human animal brain also has neurons firing, and the PEM may well apply to non-Human animals and Humans alike. However, is that enough? Are we Humans really just a slightly more intelligent animal. I argue it is absolutely not. Non-human animals can't reflect on the mysteries of the mechanisms of the universe, perform scientific experiments, do creative thinking, believe in currency exchange and laundering, or any activity beyond the shackles of genetic predisposition, among others. And furthermore, I don't think PEM explains neither of the aforementioned capacities.  

I just hope sensationalist claims in media stay as they are: "sensationalist". They're only meant to spark sensation, not actually to determine the course of public-policy making (at least not now), instilling fear of Humanity's imminent destruction or even [existential crisis](https://www.youtube.com/watch?v=lfXxzAVtdpU) on what humanity is.  What I'm most worried about is that these sensationalist claims limit our own perspective on how amazing Human intelligence is, and that it is beyond PEM. 

As previously said, I don't know what Human intelligence is in its entirety, but I'm confident it at least includes in addition to learning: reasoning, sensorimotor control, creativity/imagination, curiosity, consciousness, intrapersonal understanding, interpersonal understanding, among others.    

# Proposing an Extended Turing Test

To share some thoughts on a more comprehensive Turing Test, I do want to clarify that it is designed to measure Intelligence, not accuracy of next-predicted tokens. As such, a preliminary concept to convey concerns [Roger Penrose's 3 worlds](https://hrstraub.ch/en/the-theory-of-the-three-worlds-penrose/): 1) Platonic, 2) Physical and 3) Subjective. Almost all existing benchmarks measuring any faculty of Human Intelligence, such as to produce language, focus on evaluating in the Platonic space, the space of abstract ideas. There do exist benchmarks measuring faculties in the physical space, such as in robotics, with examples including (cute) [robots playing football](https://www.youtube.com/watch?v=RbyQcCT6890) against one another [^2], however, these benchmarks then don't measure faculties in Platonic space. 

I will also focus on the breadth of tasks, instead of the depth. This means the Extended Turing Test (better named Extended Turing Benchmark) has as many diverse tasks as possible, instead of having a single task modality, such as predicting the next text-token, but it is semantically diverse within this domain (predict the next token in English, in Spanish, in Chinese, among others). Following the main idea of this article, I won't be focusing on next-token prediction either, though it is an integral part of it. I also note this is not meant to be the final Extended Turing Benchmark, and feedback is most welcomed. 


| Task                                                             | Challenging aspects                                                   | 
|------------------------------------------------------------------|-----------------------------------------------------------------------|
| Solve a mathematical conjecture, like Goldbach's Conjecture    | The answer is not given in the training set                           |   
| Achieve a United Nation's Sustainable Development Goal          | Requires interplay of Platonic and Physical space                     |   
| Find a cure for a disease of global concern                      | Requires physical experimentation and searching over hypothesis space |   
| Propose a plan for a successful start-up                          | Same as above                                                         |   
| Break a world record                                             | Same as above                                                         |   
| Ask questions                                                    | Same as above                                                         |   
| Solve a conflict of global concern                               | Requires interplay of Platonic, Physical and Subjective spaces        |   
| Open-ended debate on moral dilemmas, such as the Trolley Problem | No correct answer, requires proficiency in Subjective space           |   


<!-- Furthermore, this Extended Turing Benchmark is meant to be agnostic to humans -->


[^1]: I don't actually mean all benchmarks are wrong. Some benchmarks have indeed yielded insight into what constitutes Human intelligence, and they are good attempts at quantifying faculties of intelligence like visual reasoning, and analogy-making.   

[^2]: The match caused some sensation despite it is not played against humans, further exacerbating a point made earlier that sensorimotor control, in addition to PEM, is an integral part of Intelligence. As such, I can't understand how and why autoregressive models are advertised as the key to Artificial General Intelligence.  