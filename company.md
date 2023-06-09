---
layout: page
title: Par ville
---
{% assign postsByCompany = site.posts | group_by: 'company' %}

{% for company in postsByCompany %}
  <h2>{{ company.name }}</h2>
  <ul>
    {% for post in company.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
