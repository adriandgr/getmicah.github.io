---
title: 'Side Project: Artist Portfolio'
date: 2017-06-19 07:35:00 -07:00
layout: post
---

<img style='height: 100%; width: 100%; object-fit: contain' src='/uploads/Screenshot%202017-06-19%2010.37.35.png'/> 

I've been working on a side project for an art school friend. He's looking to update his unruly wordpress site into something that's sleeker and easier to manage. 

I modified an existing Tumblr CSS theme which he liked and transformed it into a Jekyll template. [Source code](https://github.com/adriandgr/ce-portfolio) and site content is hosted and served using GitHub pages. Given that he is not comfortable enough editing plain text documents, I also paired it with Siteleaf's fantastic CMS platform that automatically pushes repo commits to GitHub using an intuitive visual interphase.

This project was relatively quick to set up and there are really only two main site components that are interesting to examine.

## Self Generating Navigation

One of the main goals of this project was for it to be as low maintenance as possible while remaining flexible and configurable. This meant taking note of the available editing features of Siteleaf using them in the best way possible. Siteleaf's core actions are focused on authoring new content. This is evident in their choice not to provide any mechanism to edit or update any site template using this visual platform. 

In addition to adding a static page or post, the web app allows users to generate new Jekyll collections with the click of a button. The site navigation takes advantage of this feature by looping over all collections and excluding two auto-generated collections that don't need to be displayed `posts` and `uploads` (used by Siteleaf to store static assets)



```html
{% raw %}<!-- _includes/sidebar -->
<div id="sidebar" class="has_description">
  <a href="/" id="sidebar_title" title="Home">
    <h1>{{ site.title }}</h1>
  </a>

  <h6>*</h6>
  <ul>
    {% for collection in site.collections %}
      {% if collection.label == 'posts' %} 
      {% elsif collection.label == 'uploads' %}
      {% else %}
        <li><a href="/{{ collection.label }}">
        {{ collection.label | capitalize }}</a></li>
      {% endif %}
    {% endfor %}
    <li><a href="/contact">Contact</a></li>
    <li><a href="/cv">CV</a></li>
  </ul>
</div>{% endraw %}
```