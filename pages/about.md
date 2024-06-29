---
layout: page
title: À propos
description: The only constant is change
keywords: Rémy Phan, Ruby on Rails
comments: true
menu: À propos
permalink: /about/
---

Je m'appelle Rémy Phan, programmeur Ruby on Rails depuis 2019.

Admirateur des principes de qualité.

Je crois fermement que la seule constante dans la vie est le changement.

## Contact

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
Compte WeChat officiel：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/qrcode.jpg" alt="Ma vie on Rails" />
</li>
{% endif %}
</ul>

## Mots-clés

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
