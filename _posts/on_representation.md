[15:01, 07/10/2023] awxuelong: we were talking that afternoon:

Hey, I need your opinion on this. Continuing our discussion on scaffolding before, I wanted to ask you about the following questions: how can a model represent the world? Symbolists argue using discrete symbols, while connectionist argue for distributed representation (an average of all training examples). Generative modelling is about finding latents that generate the world.  but all these models are pursuing an internal representation of the world. 

what if we step back and say, we don't need a representation. Instead, the world is the representation itself, and we need tools to parse or extract those representations. What do you think?


[15:03, 07/10/2023] awxuelong: so instead of having an internal representation of a clock, we instead have this and-or graph that can parse anything (including clocks). the result of the parse graph is our representation of it. 

in other words, we don't have an internal representation for every object, we have an universal parsing mechanism that can parse objects, resulting in representations that we denote as internal representations

to give an example, remember Song Zhu Chun's and-or graphs. we used it to parse bottles when we were talking that afternoon:

representation is not a reflection of the natural stimuli. 
    - for example a water molecule. A representation of it would not be the precise 3D model of it, accounting for scale. That would be the water molecule itself.  
    -t could be an abstract template which wich we measure
        - such template can be obtained via averaging prior observations. average is just a weighted aggregation.  a latent that is the average 
    - such abstraction is often of lower dimension and complexity than the reference stimuli. Again with the example of a water molecule, an abstraction of it may be a vectors like [2, 1] to denote 2 hydrogens and 1 oxygen  (please see research on molecular fingerprints) or a symbol like `H_2O`. Both the siluette 
    - abstractions should be dynamic and are related to other abstractions.
    - are some representations more powerful than others?
        - graph vs. molecular fingerprints? why not use both.  
unanswered questions:
    
    - can we control the representation that a machine learns so that it is scientifically meaningful.  

A representation only exists in our imagination or mathematical reality. You can think of this space as [Penrose's Platonic World](https://hrstraub.ch/en/the-theory-of-the-three-worlds-penrose/)
Data representation

in symbolism

Cat is 'cat'

In connectionism

(T, N, D)

keep T fixed

Table: Dimen
Image
graph


Let T vary
A sequence of images
a sequence of graphs
a sequence of tokens
Relational databases