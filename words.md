---
layout: page
title: Words
permalink: /words/
---
<br>
<div align="center"> Just some ideas I wanted to share </div>

<ul>
  {% for post in site.posts %}
    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <br>
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}
    <time>{{ post.date | date:"%d %b" }}</time>&nbsp;&nbsp;&nbsp;<a href="{{ post.url }}">{{ post.title }}</a><br>
  {% endfor %}
</ul>

<ul>
{% if tag[0] == 'words' %}
  {% for tag in site.tags %}
    <h3>{{ tag[0] }}</h3>
    <ul>
      {% for post in tag[1] %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
    </ul>
  {% endfor %}
{% endfor %}
</ul>