---
layout: page
title: "Guías hacking"
permalink: /guias/
---

{% for post in site.categories.guias %}
  <article class="post-preview">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d, %Y" }}</time>
    <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
  </article>
{% endfor %}
