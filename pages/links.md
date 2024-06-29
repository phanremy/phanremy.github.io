---
layout: page
title: Liens
description: Un blog sans liens est solitaire
keywords: Liens d'amitié
comments: true
menu: Liens
permalink: /links/
---

> Dieu a créé les parents. Heureusement, nous pouvons choisir nos amis.

<!-- <ul>
{% for link in site.data.links %}
  {% if link.src == 'life' %}
  <li><a href="{{ link.url }}" target="_blank">{{ link.name}}</a></li>
  {% endif %}
{% endfor %}
</ul> -->

> Liens d'amitié

<ul>
{% for link in site.data.links %}
  {% if link.src == 'www' %}
  <li><a href="{{ link.url }}" target="_blank">{{ link.name}}</a></li>
  {% endif %}
{% endfor %}
</ul>
