---
layout: distill
title: Reflections on the Hacking the Human Vasculature Kaggle Competition
date: 2024-03-09 08:42:00
description: transfer learning from nnUnet's hepatic vessel segmentation to renal vessel segmentation
categories: blog-post
disqus_comments: true
related_posts: true
thumbnail: assets/img/nnU-Net_overview.png
---

George Tang and I participated in the SenNet + HOA Hacking the Human Vasculature [Kaggle Competition](https://www.kaggle.com/competitions/blood-vessel-segmentation). We didn't manage to submit good results prior to the competition deadline 😅. However, after the competition deadline, we managed to obtain a competitive segmentation DICE score that could have earned us ~10th place in the competition. 


# Training the model
- My training notebook is at: https://www.kaggle.com/code/awxlong/hack-vasculature-transfer-learning
    - It consists of adapting the nnUnet proposed in https://github.com/MIC-DKFZ/nnUNet loaded with pretrained weights on hepatic vessel segmentation downloaded from https://zenodo.org/records/3734294/files/Task008_HepaticVessel.zip?download=1
    - Finetuning the nnUnet architecture to the provided dataset in the competition for 15 epochs
- My inference notebook is at: https://www.kaggle.com/code/awxlong/hack-vasculature-transfer-learning-inference
    - It consists of loading the weights trained above and inferring over the test dataset.
    - We adopt [post-processing steps](https://www.kaggle.com/competitions/blood-vessel-segmentation/discussion/475074) by 3rd place winner (shout-out to ForcewithMe) which consists of tuning a threshold for binarizing the segmentation mask which helped us boost the performance of our model up to a competitive 0.67 Dice score. For reasons unknown, without their post-processing step, my segmentation DICE score was stuck at ~0.001.

# Reflection

- Prior to transfer learning, I've attempted finetuning the foundational model MedSAM adapted from https://github.com/bowang-lab/MedSAM. My validation DICE score was stuck at ~0.18, and I argue this is because foundational models are harder to fine-tune as well as the this task was "syntactically" different to what the foundational model was previously trained on. Blood vessels are thinner, and resulting segmentation masks are more sparse compared to the datasets that MedSAM was trained on, which were most likely images of larger organs. 'Semantically' however, MedSAM would have been very appropiate for this task because technically it had 'medical' knowledge on what organs are. 
- My personal advice is that if you opt for transfer learning, focus on the 'syntax' of the task some model was trained on. In my case, I chose nnUnet's hepatic blood vessel segmentation because I noticed the masks it was previously trained on are 'sparse' and 'thin'. I wouldn't prefer, for instance, some segmentation model pretrained on 'ocular blood vessels' because even though they are 'semantically' the same task, syntactically, their segmentation masks are thin, but they weren't sparse.  


# Presentation

I did a presentation for the Nexus Lab Sympossium on March 9th, with slides here attached below:

{% pdf "/assets/pdf/hacking-the-human-vasculature.pdf" %}
