---
layout: post
title: Deciding when to use narrow AI-based or heuristic-driven solutions for a problem #a post with jupyter notebook
date: 2022-02-06 08:42:00-0400
description: some thoughts concerning the decision to leverage or not artificial intelligence to tackle a problem
tags: class-notes
categories: blog-post
disqus_comments: true
related_posts: false
thumbnail: assets/img/non-linearity-vs-linearity.png
---
For the original notebook, please go to my respective [repository](https://github.com/awxlong/notes-re/blob/main/narrow-ai-vs-heuristic/On%20the%20decision%20of%20using%20narrow%20AI-based%20or%20heuristic-driven%20solutions.ipynb)

What follows is an embedded notebook:

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/narrow_heuristic.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/narrow_heuristic.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


<!-- 

To include a jupyter notebook in a post, you can use the following code:

{% raw %}

```html
{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/blog.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/blog.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}
```

{% endraw %}

Let's break it down: this is possible thanks to [Jekyll Jupyter Notebook plugin](https://github.com/red-data-tools/jekyll-jupyter-notebook) that allows you to embed jupyter notebooks in your posts. It basically calls [`jupyter nbconvert --to html`](https://nbconvert.readthedocs.io/en/latest/usage.html#convert-html) to convert the notebook to an html page and then includes it in the post. Since [Kramdown](https://jekyllrb.com/docs/configuration/markdown/) is the default Markdown renderer for Jekyll, we need to surround the call to the plugin with the [::nomarkdown](https://kramdown.gettalong.org/syntax.html#extensions) tag so that it stops processing this part with Kramdown and outputs the content as-is.

The plugin takes as input the path to the notebook, but it assumes the file exists. If you want to check if the file exists before calling the plugin, you can use the `file_exists` filter. This avoids getting a 404 error from the plugin and ending up displaying the main page inside of it instead. If the file does not exist, you can output a message to the user. The code displayed above outputs the following:

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/blog.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/blog.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
    {% jupyter_notebook jupyter_path %}
{% else %}
    <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}

Note that the jupyter notebook supports both light and dark themes. 
-->
