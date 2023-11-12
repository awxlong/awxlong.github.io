# An interesting analogy between language and biology

# On the interesting parallels of language and biology

Reading an interesting paper by Lauren, 

Hi Antonio, I have a question on VAEs.

There are interesting parallels between the problems surfacing in natural language processing (NLP), as well as computational biology. The simplest common denominator is the analysis of sequences: algorithms and modelling paradigms that help process a sequence of words to solve a task like classification can surprisingly work with sequences of genes to classify disease. 

Another concern embeddings. Much as how words have embeddings which can be extracted from open-source libraries like GLoVE and word2Vec, molecules also have expert-coded molecular fingerprints as embeddings. 

Another Imagine that you want to generate sentences. You have a collection of sentences to train a probabilistic model on. Because we can't control what the probabilistic model learns from the given data, how do you make sure you don't generate an ungrammatical sentence like "jogging Octopie went", where we have a "verb-subject-verb" structure. The simplest way would be to set up an intrinsic template like "subject-verb-object"[^1] in order to offset portion of the probabilistic model's support[^3] to not put any probability mass to structures other than "subject-verb-object". Given this, this will first guarantee that sentences follow the correct grammar rules, and second guide [learning](https://awxlong.github.io/blog/2023/sgd/) since the model is not exploring over the whole parameter space, but only that which conform to the supplied template. 

Consider the following analogous task, given some atoms like hydrogen, carbon, oxygen, among others, you want to train a probabilistic model to predict the angle of rotation when such input atoms are assembled together into a compound. This could be relevant for a 3D reconstruction of an assembled molecule. You have a dataset of different atom-atom compounds with their associated rotation angles.  If you only rely on learning, then the resulting probabilistic model may put probability mass on biologically implausible rotation angles, even if the probability mass is negligible. In the end, statistics is just about counting and averaging, meaning that even if you only see that some compound like water has a bond angle of around [105 degrees](http://witcombe.sbc.edu/water/chemistrystructure.html), the model's support would still put probability mass in-between 0 or 200 degrees [^2]. Enumerating all possible rules concerning rotation angles would be impractical, so one can resort to biomedical ontologies.

Arguably, this is how DeepMind's AlphaFold ensures that proteins generated from DNA input sequences are biologically plausible, as can be observed in the model's pipeline. In it, the input sequence first goes through a database search that is subsequently converted into embeddings used to generate the protein structure. Without this first phase, this probabilistic model may output proteins that resemble the ones observed during training, at the risk of following impossible configurations.     


<figure>
  <img src="/assets/img/alphafold-pipeline.png" alt="Sorry, an unanticipated error occured and the image can't load." width="100%" height="auto">
  <figcaption id="afold"> Structural constraints in the first phase concerning genetic database search and structure database search ensures that rotation angles of bonds in the compounds of the protein are biologically plausible, setting structure in learning. Figure extracted from https://www.nature.com/articles/s41586-021-03819-2 </figcaption>
</figure>

Generating implausible proteins, or invalid angle rotations between bonds is akin to generating sentences that violate grammar rules. It is debatable whether the rules can be learnt from data. Rather, the role of rules and constraints might be to shape learning. 

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

If you have answers, share thoughts, you can leave a comment or please email me!

[^1]: Sentences don't follow this simple template, but it helps get the idea across that placing structure into the support of a probabilistic model helps guide learning.  
[^2]: While it is true that some bonds between atoms like a carbon-carbon bond have no restricted rotation angle, others like a [hydrogen peroxide](https://www.sciencedirect.com/science/article/pii/S0022285217302990) is constrained to a setting of rotation degrees (with some uncertainty).  
[^3]: A probabilistic model's support refers to the domain of values for which the output of the model is non-zero. 