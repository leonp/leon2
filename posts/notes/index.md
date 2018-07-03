---
layout: default
title: Notes
---

{% assign posts = site.posts | where: "note", "true" %}

{% include note-list.html %}
