---
layout: page
title: "Ruta de Aprendizaje C++"
permalink: /cpp-learningpath/  # ¡Debe coincidir con la URL deseada!
---

<h2>📚 Todos los posts de C++</h2>

{% for post in site.categories.cpp_learningpath %}
  <article>
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <time>{{ post.date | date: "%b %d, %Y" }}</time>
    <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
  </article>
{% endfor %}
