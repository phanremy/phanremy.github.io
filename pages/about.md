---
layout: page
title: À propos
description: Le codage change le monde
keywords: Zhuang Ma, 马壮
comments: true
menu: À propos
permalink: /about/
---

Je suis Zhuang Ma, né pour coder, codant pour vivre.

Admirateur de « L'art du code élégant ».

Je crois fermement que la pratique rend parfait et que l'effort change la vie.

## Contact

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
Compte WeChat officiel：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/qrcode.jpg" alt="Programmeur introverti" />
</li>
{% endif %}
</ul>

## Mots-clés des compétences

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
