---
layout: distill
title: "The Future of Medicine: Big Data and Democratization" #displaying beautiful tables with Bootstrap Tables
date: 2021-09-24 14:42
description: review on Deep Medicine and The Patient Will See You Now, two books authored by Dr. Eric Topol
tags: books-review
categories: blog-post
disqus_comments: true
related_posts: true
bibliography: deep-med.bib
thumbnail: assets/img/self-patient.png
authors:
  - name: An Xuelong
# datatable: true
toc:
  - name: Overview
  - name: Current challenges
  - name: "AI and Medicine: Big Data and Emancipation"
  - name: "AI and Medicine: Mutual Empathy"
  - name: "Overcoming toda's challenges to identify tomorrow's"
  - name: "Final remarks on AI and Healthcare"
featured: true
---


# Overview

“Deep Medicine”<d-cite key="topol_2019_deep"></d-cite> and “The Patient Will See You Now”<d-cite key="topol_2015_the"></d-cite> are two books authored by Dr. Eric Topol in which he discusses the current challenges and future prospects of the merging of artificial intelligence and the healthcare sector. As always, I don’t seek to provide a summary of both books, but instead to provide some afterthoughts in the hope of igniting a fruitful discussion and inspiration in us for making the most out of the dynamic future, developing the capacities to overcome the difficulties and take advantage of opportunities that the coexistence of AI and humans bring in the diverse sectors of society.

# Current challenges 

Views can be polarized regarding the term “medicine” or “healthcare”. Pessimistic viewpoints tend to qualify it as the healthcare being a sector that tends to make profit from the patient, either though overprized medical tests that provide no useful insight to a patient’s status, expensive drugs unaffordable by low-income families, negative service offered by burnt-out doctors when seeing them and talking for just about 10 minutes without much empathy felt during the discussion, among others. Such situation can be summarized as “paternalistic medicine”, where the unknowing patient offers unconditional obedience to the doctor, which may prove inefficient for treating a disease as it may sometimes lead to an late-stage diagnosis of a disease (i.e. the patient comes to see a doctor at an advanced stage of a disease, say cancer, because he/she didn’t care about his/her health earlier), or high-cost, unnecessary expenditures (i.e. the healthy, yet unaware, patient undergoes expensive CT scans or X-rays that don’t provide meaningful information, all the while exposing him/her to too much radiation). 
 
I personally stand from a more optimistic perspective regarding healthcare, as I highly respect and admire the profession of medicine, and such view has been further reinforced through witnessing how healthcare workers, spanning from doctors to nurses, from radiologists to bioinformaticians, have fought bravely in the frontlines against the SARS-CoV-2 in order to safeguard the health of the common populace. I believe the above negative views over a burdened healthcare sector should not undermine the sacrifices of our healthcare personnel. Of course, that being said, my views still clash with the harsh reality of the current challenges in the healthcare sector, not only the ones above mentioned but also more, such as for instance misinformed patients who do not follow medical guidelines meant to improve their health (i.e. a smoking lifestyle that leads to pulmonary diseases or a high-carb diet despite having diabetes) which is a sign of a lack of communication and eventual empathic cooperation between doctor and patient. 

All the above, and more, have become obstacles for the democratization of medicine, which can be interpreted as a highly efficient, low cost healthcare sector that can serve for safeguarding the health of the majority of a population. And, indeed, as you may have guessed it, AI can help us solve such issues and achieve that. 

# AI and Medicine: Big Data and Emancipation

In “The Patient Will See You Now”, a recurrent theme has been exploiting the era of Big Data for empowering the patient with sufficient knowledge in order to make healthcare a more efficient interaction between doctor and patient. Different from the above described scenario, in the future, it’s expected that doctors will not unilaterally seek the unknowing patient to understand his/her health, but rather, the patient can readily visit the doctor and hold a more balanced/bilateral discussion about his/her health and, if required, the necessary treatment. This is thanks to the patient being equipped with enough knowledge of his/her own health status extrapolated from the understanding of own family history, genome tests, heart rate monitored through an own electrocardiogram, among other covariates that can be taken through cheap sensors that may be embedded in a smartphone, a symbol of the era of Big Data where each one of us can become data miners and make this data generated benefit each one of us ([Figure 1](#self-test)). 

<figure>
  <img src="/assets/img/self-patient.png" alt="Figure couldn't load due to an unknown error. Sorry.">
  <figcaption id="self-test">Figure 1: Smartphones are expected to be embedded with a “laboratory on a chip (LOC)”. This allows for performing miniaturized lab tests or making these lab tests and their results portable. This opens the possibility of making disease diagnosis a way of life, and isn’t that the key to curing the majority of diseases? Images extracted from (left to right): https://threadreaderapp.com/thread/1076894405867462656.html, https://www.imedicalapps.com/2011/11/cardiodefender-mobile-ecg-diagnostic-system-accessed-smartphone/#,  https://www.hearingreview.com/miscellaneous/oaktree-introduces-smartphone-enabled-digital-otoscope
  </figcaption>
</figure>


Such a phenomenon has been called by Dr. Topol as the “emancipation” of the patient thanks to Big Data generated, owned and made useful by each one of us. Thus, what this big data can build for each individual is a personalized biological Geographic Information System (GIS) that spans from the exposome, epigenome, microbiome, metabolome, proteome, transcriptome, genome, anatome, physiome and phenome throughout one’s entire life. Indeed, this would constitute a panoramic view from pre-womb to tomb ([Figure 2](#gis)).

<figure>
  <img src="/assets/img/human-gis.jpg" alt="Figure couldn't load due to an unknown error. Sorry.">
  <figcaption id="gis"> 
  Figure 2: The Human GIS cropped from The Patient Will See You Now. In the book, it’s estimated that the human GIS might oscillate around 10 TB of data 
  </figcaption>
</figure>


Among the opportunities that generating one’s own data brings is that an efficient and constant monitoring of one’s health status can help us achieve what may be the core of futuristic medicine:

- Early detection: This is due to the patient equipped with enough cheap equipment materialized as sensors embedded in smartwatches or smartphones able to track different variables relevant to determine one’s health status. This could lead to at-home monitoring. Among the data that can be assessed, there is:

- Tracking family history and genome data: it is to my believe that genome data may prove pivotal and become the next blockbuster in medicine. Not only does genome, coupled with family history, allow us to discover at an early stage a disease like cancer, there are other aspects regarding the human genome such as the transcriptome (RNA) or epigenome that further diversifies the amount of possibilities that can be taken advantage of in the early diagnosis of a disesase. Particularly, I’ve written about how miRNA, part of the human transcriptome, can serve as a disease and tissue-specific, non-invasive and cheap (when coupled with CRISPR-CAS system) diagnostic tool for the early detection of a disease like cancer and Alzheimer and also leaves a window of opportunities for becoming a therapeutic agent. 
- Monitoring the gut microbiome: in order to understand how diet, and the gut microbiome’s composition shapes the health of the individual. This field is yet to be thoroughly understood. 
- Tracking real-time health covariates: as said above, health factors like heart rhythm or blood glucose are expected to be more finely tracked and made useful by the patient through either micro-chips or bio-sensors which can provide useful data in a lot of aspects of healthcare other than the patient understanding his/her own health status, but also for instance, providing information about how a drug has interacted with molecules inside the body through these kind of biosensors, which influences its own design and delivery.
- Even rare cases of disease can be early diagnosed as long as enough data is available. Throughout “The Patient Will See You Now”, Dr. Eric Topol discussed a consistent finding that about 3/4 of a sample of interviewees would be willing to make their anonymized medical records be publicly analyzable, since it’s for the benefit of the majority (and minority) of patients who may have share similar patterns or symptoms of a disease. What this leads to is what Dr. Topol has termed as Massive Online Open Medicine (MOOM) (an adaptation of Massive Online Open Course) that’s meant to harness your data, the data of people who surround you, and those who surround them, to build a database that can be used to crack from the simplest diagnoses to complicated, rare cases of disease.  

- Early discussion: the emancipated patient can now seek expertise from the knowledgeable doctor instead of providing unconditional obedience. My opinion would be here in seeking balance, whereby being better equipped with medical data doesn’t mean undermining medical professionalism. For instance, in an special issue (issue 52) of The Batch, Dr. Topol mentioned how clinicians should spend their time talking to patients instead of staring at monitors and typing in electronic health records, since this could be done by AI, thus liberating them from this repetitive work. Thus, there shouldn’t be a replacement of the doctor, but rather a simplification of his/her load of work in order to allocate more time for doctor-patient face to face interaction. 

- Early treatment: which would become the best cure of a disease, as mentioned in a past blog. 
 
# AI and Medicine: Mutual Empathy 

Not far in the past I do acknowledge that I believed AI will sweep across the different fields of society, and in medicine it may well replace radiologists (sorting out X-rays), ophthalmologists (sorting out eye images), pathologists (sorting out tissue exams), cardiologists (diagnosing ECGs readings) or dermatologists (sorting out skin images). However, after reading “Deep Medicine”, I believe a more down-to-earth view is that, at least in the near future, AI can only serve as a helpful medical assistant that will help ease the burden on the mentioned medical professions, and not replace them. This is mainly because an important characteristic AI lacks is being holistic, or multitasking, a symbolic feature of narrow AI. A radiologist may not only examine X-ray images, he/she may also review the patient’s profile involving medical history, family history, or, perform even more diverse functions such as running and directing research teams, alleviating patient’s burden of their results, which requires emotional support, so all in all, this leaves AI the room of only becoming a very efficient virtual assistant that may very well alleviate the burden on doctor’s shoulders, on healthcare, and improve its efficiency during interaction with patients. 

# Overcoming today's challenges to identify tomorrow's

Of course, despite having discussed the futuristic prospects of AI in the healthcare sector, reality is that there are still a lot of challenges to be overcome in order for an efficient merging of both sectors.  Those that can be mentioned include: 
- As Dr. Topol mentioned, there is already too much big data available, yet too little knowledge. This foreshadows the long road of mining all these data, subsequently process it and train efficient models, evaluate them and deploy them. For example, one such area in which a lot of knowledge is yet to be unthread is the human gut micriobiome and how it influences the host’s health; subsequently how would this knowledge be used by AI models to monitor patient’s health. 
- However, model deployment in real life clinical settings is also a challenge: it’s already a daunting challenge to design machine learning algorithms used to process the available big data and train their respective models. Apart from this logistic hurdle, there are still ongoing trial and error, human-centered research seeking to identify and solve issues concerning developing a symbiotic relationship between a model and clinicians in real life settings[^1] <d-cite key="beede_2020_a"></d-cite>. For example, images of a retina fed into a model trained to diagnose diabetic retinopathy may have been of higher quality than retina images taken in a poorly equipped clinic, thus rendering the model unable to process these real-life inputs on site. This example thus exposes the difference in the pace in which developed countries progress in the field of AI & Medicine, versus how the majority progress. 
- Fundamentally, the merging of AI and medicine carries with it a different set of regulations and caution compared to, for instance, models deployed to predict user’s shopping preferences. It concerns the welfare, and maybe even life quality, of the user, thus there are barriers of skepticism to overcome before even adapting it to real-life. Ways to overcome such obstacles can be through more rigorous, longitudinal evaluations, such as the golden standard for empirical evidence gathering, randomized control trials for AI models in medicine <d-cite key="kelly_2019_key"></d-cite>. It’s worth noting here that there are already randomized trials that demonstrate the utility of AI. For example, Chinese researchers have shown that deep neural networks can identify lesions missed by gastroenterologists during endoscopy and colonoscopy <d-cite key="topol_2019_it"></d-cite>.
- Another way to address issues concerning regulations surrounding AI is the development of self-explanatory AI (also named X-AI)
- Of course, impact in lifestyle, as well as sociocultural implications of AI models intervening in healthcare should also be addressed, with issues such as data privacy to safeguard one’s GIS, or democratization of medicine echoed by Dr. Topol throughout his books. 

A particular example that struck me when reading “The Patient Will See You Now”, is that by the year 2015 when this book was published, it was mentioned that there existed a company startup called Theranos. This company had the innovative idea of providing affordable and portable diagnostic tests for a lot of diseases using just a blood sample from the patient. This seemed to promise a lot of potential. However, years later it turned into a defunct company for allegations of fraud[^2]. We can learn from this real world case scenario that although the merging of AI and Healthcare is very attractive, promising and revolutionary, we should still retain our senses of skepticism, caution and honesty when materializing such potentials. 

# Final remarks on AI and Healthcare

As mentioned throughout the text, the merging of AI and the Healthcare sector can be thought be revolutionary, and it’s going to drastically change our lives. It may redefine the patient-doctor relationship, such as emancipating the patient with data while liberating the doctor from burden. 
Of course, perhaps a logical question that follows is when can we witness such a change? In my opinion, that day may come sporadically. We might transition through phases, instead of changing fundamentally our lifestyle in an instant. Although it’s true that part of the population of certain countries is already using smartwatches and smartphones to monitor health biomarkers like heart rate, we are still far from exploiting the full potential of our devices that has been mentioned throughout the text.  

All in all, as long as we’re able to face the challenges brought by medicine and AI, we can grasp perhaps unlimited potential from its symbiotic relationship. In the future, we may be able to save lives without even having to touch the scalpel or perform surgeries. Most diseases could be prevented through daily monitoring of health. Perhaps medicine will not only teach us the technicalities of anatomy, pharmacology, or biology, but also focus on the empathic relationship between the patient and doctor. This is because our devices, our machines, can perform diagnosis at a (maybe) more accurate rate and accumulate far more information than a human can (funnily, our machines can go through med school for us). What do you think will happen? How do you plan to address the future challenges and opportunities? What do you expect from AI and Healthcare? 


[^1]: Case study from special issue 52 of The Batch (you can subscribe to a mailing list): https://www.deeplearning.ai/thebatch/?utm_campaign=The%20Batch&utm_medium=email&_hsmi=87523675&_hsenc=p2ANqtz-9Bz_mGy2bjkmt-GvaSVleiSgwrPPkDCcCiSgjQ2zZD18RIeRcVpmHfmy-KCGBrl0PNOJun&utm_content=87523675&utm_source=hs_email 

[^2]: Please consult: https://www.msn.com/en-gb/news/world/disgraced-theranos-ceo-to-blame-mental-illness-in-her-fraud-trial-defence/ar-BB18V45b


<!-- 
Using markdown to display tables is easy. Just use the following syntax:

```markdown
| Left aligned | Center aligned | Right aligned |
| :----------- | :------------: | ------------: |
| Left 1       | center 1       | right 1       |
| Left 2       | center 2       | right 2       |
| Left 3       | center 3       | right 3       |
```

That will generate:

| Left aligned | Center aligned | Right aligned |
| :----------- | :------------: | ------------: |
| Left 1       | center 1       | right 1       |
| Left 2       | center 2       | right 2       |
| Left 3       | center 3       | right 3       |

<p></p>

It is also possible to use HTML to display tables. For example, the following HTML code will display a table with [Bootstrap Table](https://bootstrap-table.com/), loaded from a JSON file:

{% raw  %}
```html
<table
  id="table"
  data-toggle="table"
  data-url="{{ '/assets/json/table_data.json' | relative_url }}">
  <thead>
    <tr>
      <th data-field="id">ID</th>
      <th data-field="name">Item Name</th>
      <th data-field="price">Item Price</th>
    </tr>
  </thead>
</table>
```
{% endraw  %}

<table
  data-toggle="table"
  data-url="{{ '/assets/json/table_data.json' | relative_url }}">
  <thead>
    <tr>
      <th data-field="id">ID</th>
      <th data-field="name">Item Name</th>
      <th data-field="price">Item Price</th>
    </tr>
  </thead>
</table>

<p></p>

By using [Bootstrap Table](https://bootstrap-table.com/) it is possible to create pretty complex tables, with pagination, search, and more. For example, the following HTML code will display a table, loaded from a JSON file, with pagination, search, checkboxes, and header/content alignment. For more information, check the [documentation](https://examples.bootstrap-table.com/index.html).

{% raw  %}
```html
<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/table_data.json' | relative_url }}">
  <thead>
    <tr>
      <th data-checkbox="true"></th>
      <th data-field="id" data-halign="left" data-align="center" data-sortable="true">ID</th>
      <th data-field="name" data-halign="center" data-align="right" data-sortable="true">Item Name</th>
      <th data-field="price" data-halign="right" data-align="left" data-sortable="true">Item Price</th>
    </tr>
  </thead>
</table>
```
{% endraw  %}

<table
  data-click-to-select="true"
  data-height="460"
  data-pagination="true"
  data-search="true"
  data-toggle="table"
  data-url="{{ '/assets/json/table_data.json' | relative_url }}">
  <thead>
    <tr>
      <th data-checkbox="true"></th>
      <th data-field="id" data-halign="left" data-align="center" data-sortable="true">ID</th>
      <th data-field="name" data-halign="center" data-align="right" data-sortable="true">Item Name</th>
      <th data-field="price" data-halign="right" data-align="left" data-sortable="true">Item Price</th>
    </tr>
  </thead>
</table> 
-->
