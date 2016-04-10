---
layout: page
title: Archives
description: List of articles and posts by date.
---

<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date:"%b %Y" }}</li>
  {% endfor %}
</ul>