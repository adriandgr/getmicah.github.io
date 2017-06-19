---
title: 'Side Project: Artist Portfolio'
date: 2017-06-19 07:35:00 -07:00
layout: post
---

<img style='height: 100%; width: 100%; object-fit: contain' src='/uploads/Screenshot%202017-06-19%2010.37.35.png'/> 

Working on this side project for an art school friend. He's looking to update his unruly wordpress site into something simpler and easier to manage. 

I combined an existing Tumblr CSS theme which he liked and transformed it into a Jekyll template. [Source code](https://github.com/adriandgr/ce-portfolio) and site content is hosted and served using GitHub pages. Given that he is not comfortable enough editing plaintext documents, I also paired it with Siteleaf's fantastic CMS platform that automatically pushes repo commits to GitHub using an intuitive visual interphase.

```html
<!-- _includes/sidebar -->
    <div id="sidebar" class="has_description">
      <a href="/" id="sidebar_title" title="Home">
        <h1>{{ site.title }}</h1>
      </a>

      <h6>*</h6>
      <ul>{% for collection in site.collections %}{% if collection.label == 'posts' %}{% elsif collection.label == 'uploads' %}{% else %}
        <li><a href="/{{ collection.label }}">{{ collection.label | capitalize }}</a></li>{% endif %}{% endfor %}
        <li><a href="/contact">Contact</a></li>
        <li><a href="/cv">CV</a></li>
      </ul>
    </div>
```