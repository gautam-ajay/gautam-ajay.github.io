---
layout: page
title: Ideas
permalink: /ideas/
---
<br>
<div align="center"> Just some ideas I wanted to share </div>

<ul>
{% for post in site.posts %}
  {% if post.tags contains 'words' %}
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
  {% endif %}
{% endfor %}

</ul>
