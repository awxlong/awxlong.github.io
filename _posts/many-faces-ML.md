<!-- A bird can be denote as "pájaro" in Spanish, "鸟(niǎo) in Chinese,  -->

I bumped into this paper on [X (formerly Twitter)](https://twitter.com/ChristophMolnar)
{% twitter https://twitter.com/ChristophMolnar/status/1718921189333045752 %}

In today's post, I don't want to discuss interpretability or explainability, but rather elaborate on the above idea that in the literature, different authors express completely different ideas despite using the same words, often words of our daily parlance. 

If you have just set foot into the world of artificial intelligence, here are my thoughts and advices on navigating this exciting, but often messy landscape. 

# Terms
explanation, hypothesis, model
    - often refers to some function that is parametrized by $\theta$
    - in rare cases, such as in [Prof. Joshua Tenembaum's talk on Cognition](https://www.youtube.com/watch?v=NsID1iM8gRw), a (physics-) model can refer a simulator implemented in Unity. At least when I began studying AI, the word "model" reminded me of a 3D scale model of something. If I wanted a model of an atom, I could pick some recycled styrofoam balls, stick them together and, bam (pun intended), an atom is synthesized. Nowadays it mainly refers to an 2D equation with some parameters $\theta$, where a 'good' model is defined as having optimal parameters $\theta$ that can make predictions with low error on the training and (hopefully) unseen, test data, compared to a 'bad' model.    
the word "knowledge" 
    - This word may cause some confusion to peers with a philosophy or psychology background. At least to me, prior to studying AI, 'knowledge' meant pieces of information encoded in natural language, e.g. "Mount Chimborazo is actually higher than Mount Everest" somewhere in the brain. I don't know how, nor where, nor whether it is encoded in natural language. 
    - At least in the early days of AI, first order logic constraints such as `smoker(X) :- edema(X)`, read as "it is true that if X is a smoker, then X has edema", does resemble information that we know. 
    - This is not always the case. The words 'prior knowledge', mainly used in Bayesian modelling, has not much to do with logic predicates or natural language. It mainly refers to what you believe on the distribution of the parameters of your model come from before your model is trained on any data. If you think your model ... Guidance on what prior distributions can be used to describe your parameters can be check in this [tweext](https://twitter.com/bindureddy/status/1708664380987220427) 
    - Some researchers may even say that 'knowledge' of the data is encoded in the parameters of the model, which leads us to the next section:
    
The words explainability and interpretability
    - coefficients of variables. 
    - thresholds of a junction in decision trees. 
    - feature maps. A neural network becomes 
    - post-hoc processing of latent variables. 
    - some authors may also refer to the capability to compute the likelihood of the parameters of the data, or at least an approximation of it. This scalar value can be used to compare the performance of different models, and these models can thus be referred to as "provable".  
    - some authors may also settle with a user interface that allows some user to interact with the model. 

    interpretability

# Bottom line

My key advice:
    - don't trust the "intuitive" interpretation of a word, especially if it is used on a quotidian basis. For example, in my personal view, to be "explainable" means to be able to justify its own answer. Just like a friend to whom I ask why didn't they go to a concert by singer Aimer, to be "explainable" (at least when referring to the common meaning of this word in daily life) means that they can give a justification as to why didn't they go (maybe they became sick, or admit they have poor taste in music). 'Explainable' in the machine learning literature has not much to do with this daily life interpretation. 

Finally, the above terms are simply the tip of the iceberg. In the wider research literature, authors can diverge in what they mean by on many terms such as "language", the word "intelligence" itself, and more controversial terms like "artificial general intelligence". Because I don't know the precise meaning of them myself, I refrain from commenting furthermore. 

Happy learning!


