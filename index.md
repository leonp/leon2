---
layout: default
title: Leon Paternoster
display-title: "13 years (and counting) of building websites, managing digital and marketing teams and project managing complex digital projects."
nav-title: "Home"
is_home: true
order: 1
prose-headings: true
hyphens: true
visited-links: true
underlined-links: true
in_nav: true
---

**leon.paternoster@zoho.com** / [LinkedIn](https://uk.linkedin.com/in/leonpaternoster/)

<h2 class="c-lh-title mb3">Work</h2>

{% assign projects = site.work | sort: "work-order" %}

{% for project in projects %}

<figure class="pb4 flex-l flex-wrap-l items-center{% if forloop.index == 1 or forloop.index == 3 %} flex-row-reverse-l{% endif %}">

	<div class="w-50-l{% if forloop.index == 1 or forloop.index == 3 %} pl4-l{% else %} pr4-l{% endif %}">

		<h3 class="ma0 c-lh-title"><a href="{{ project.url }}">{{ project.title }}</a></h3>

		<p class="mv2 measure">{{ project.summary }}</p>

	</div>

	<div class="w-50-l">

		<a href="{{ project.url }}"><img class="db ma0 pa0" src="/images/{{ project.image }}" alt="{{ project.alt }}"></a>

	</div>

</figure>

{% endfor %}
