---
layout: page
title: "Ruta de Aprendizaje C++"
permalink: /cpp_learningpath/  
---

<h2> ☢️ Todos los posts de C++</h2>

Bueno hijos de perra qué pasa realmente. Esta categoría la he creado para subir mis avances en el aprendizaje de C++. A fecha 03 de Febrero del 2025 he decidido pausar mis avances en hacking y enfocarme ÚNICA y EXCLUSIVAMENTE en C++ ya que es una habilidad bastante necesaria para el óptimo y competente desempeño en este rubro, y el que diga lo contrario tiene toda la razón. Aquí podrán encontrar todo lo que usé y creé en esta terrible travesía llamada "Ruta de Aprendizaje C++". Esta ruta constará de tres grandes avances, cada uno de ellos -estimo- tendrá una duración de entre 3 a 5 meses. Según mis proyecciones (mentira) estaré finalizando esto a fines del año 2025. Espero no quedar calvo o con pérdida parcial de mi sistema nervioso somático.

{% for post in site.categories.cpp_learningpath %}
  <article>
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <time>{{ post.date | date: "%b %d, %Y" }}</time>
    <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
  </article>
{% endfor %}

