---
layout: page
title: Archives
description: List of articles and posts by date.
---

<div>
  {% for post in site.posts %}

    {% unless post.next %}
      <h2>{{ post.date | date: '%Y' }}</h2>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h2>{{ post.date | date: '%Y' }}</h2>
      {% endif %}
    {% endunless %}

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
  {% endfor %}
</div>