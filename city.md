---
layout: page
title: Par ville
---

{% for city in site.city %}
  <h3>{{ city[0] }}</h3>
  <ul>
    {% for post in city[1] %}
      <li><a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
