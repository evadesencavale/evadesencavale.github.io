---
layout: page
title: Par compagnie
---

{% for company in site.company %}
  <h3>{{ company[0] }}</h3>
  <ul>
    {% for post in company[1] %}
      <li><a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
