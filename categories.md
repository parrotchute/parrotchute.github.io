---
layout: page
title: Categories
description: List of articles and posts by category.
---

<!-- Get the category name for every category on the site and set them
to the `site_categories` variable. -->
{% capture site_categories %}{% for category in site.categories %}{{ category | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}

<!-- `category_words` is a sorted array of the category names. -->
{% assign category_words = site_categories | split:',' | sort %}

<!-- Build the Page -->

<!-- List of all categories -->
<div>
  {% for item in (0..site.categories.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ category_words[item] }}{% endcapture %}
    <a class="category-mark" href="#{{ this_word | cgi_escape }}">{{ this_word }} 
    ({{ site.categories[this_word].size }})</a>
  {% endunless %}{% endfor %}
</div>

<!-- Posts by category -->
<div>
  {% for item in (0..site.categories.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ category_words[item] }}{% endcapture %}
    <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
    {% for post in site.categories[this_word] %}{% if post.title != null %}
      <div>
        <span style="float: left;">
          <a href="{{ post.url }}">{{ post.title }}</a>
          <!-- Tags -->
          {% for tag in post.tags %}
            <a class="tag-mark tag-mark-small" href="/tags#{{ tag }}">{{ tag }}</a>
          {% endfor %}
        </span>
        <span style="float: right;">
          {{ post.date | date_to_string }}
        </span>
      </div>
      <div style="clear: both;"></div>
    {% endif %}{% endfor %}
  {% endunless %}{% endfor %}
</div>