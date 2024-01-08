---
layout: default
title: Leon Paternoster
display-title: "Building websites, managing digital and marketing teams and project managing complex digital projects since 2008."
nav-title: "Home"
is_home: true
order: 1
prose-headings: true
hyphens: true
visited-links: true
underlined-links: true
hide-title: true
---

## About

<div class="flex items-center mv3">

	<div class="w-third w-25-ns w-20-l pr3">

		<img class="db ma0 pa0 br-100" src="/images/lp-2024-01.jpg">

	</div>

	<div class="w-two-thirds w-75-ns w-80-l pl3">

		<p class="f6 f5-l">I’m Leon, web manager at Anglia Ruskin University. I’ve been building websites, managing digital and marketing teams and project managing complex digital projects since 2008. <a class="white" href="/about">Read more about me</a>.</p>

	</div>

</div>

## Contact

<ul class="list ph0">

	<li>leon.paternoster@gmail.com</li>
	<li><a href="https://uk.linkedin.com/in/leonpaternoster/">LinkedIn</a></li>

</ul>

## Work

<div class="mt3">

{% assign projects = site.work | sort: "work-order" %}

{% for project in projects %}

	<div class="mb2 mb0-l flex-l">

		<div class="w-75-l pr2-l"><a class="db" href="{{ project.url }}">{{ project.title }}</a></div>

		<div class="w-25-l pl2-l tr-l f6">{{ project.year }}</div>

	</div>

{% endfor %}

</div>