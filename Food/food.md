---
layout: page
title: Food
permalink: /food/
---
<br>
<div align="center"> A collecton of loose guidelines and techniques make your food taste fucking good.</div>

<ul>
    {% unless food.next %}
      <h3>{{ food.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ food.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ food.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <br>
        <h3>{{ food.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}
    <time>{{ food.date | date:"%d %b" }}</time>&nbsp;&nbsp;&nbsp;<a href="{{ food.url }}">{{ food.title }}</a><br>
  {% endfor %}
</ul>

