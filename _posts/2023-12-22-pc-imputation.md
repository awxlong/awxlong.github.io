---
layout: post
title: A probabilistic circuit for imputing missing tabular data #a post with jupyter notebook
date: 2023-12-22 08:42:00
description: using a sum-product network to flexibly impute missing data in Kaggle's Titanic dataset
tags: class-notes food-for-thought
categories: blog-post
disqus_comments: true
related_posts: true
thumbnail: assets/img/pc-logo.png
---

# SPNs for imputing data

The following is a Jupyter notebook ran on Google Colab using Kaggle's Titanic dataset to illustrate a practical use case of a probabilistic circuit, a sum-product network, from [deepprob-kit](https://github.com/deeprob-org/deeprob-kit): to impute missing tabular data.

This notebook is forked from a Kaggle [tutorial](https://www.kaggle.com/code/ttminh27/using-autoencoder-to-impute-missing-data) on using a Tensorflow's autoencoder to impute missing data. Standard autoencoders can't:
- custom fill-in missing data
- flexibly incorporate domain knowledge like what distribution is best used to model a feature
- Furthermore, p;robabilistic circuits can tractably compute missing data through maximum a posteriori estimation. 

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/using_pc_to_impute_missing_data.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/using_pc_to_impute_missing_data.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

