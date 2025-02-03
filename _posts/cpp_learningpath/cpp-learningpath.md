---
layout: page
title: "Ruta de Aprendizaje C++"
permalink: /cpp-learningpath/
---

{% for post in site.categories.cpp_learningpath %}
  <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <small>{{ post.date | date: "%b %-d, %Y" }}</small>
  <p>{{ post.excerpt }}</p>
{% endfor %}
