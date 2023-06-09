---
layout: page
title: Par ville
---
{% assign postsByCity = site.posts | group_by: 'city' %}

{% for city in postsByCity %}
  <h2>{{ city.name }}</h2>
  <ul>
    {% for post in city.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
