---
layout: default
title: Home
display-title: 'Hello<span class="dark-pink">.</span>'
is_home: true
in_nav: true
order: 1
---

<section>

    <h2 class="f4 c-lh-title mt4 c-sans-serif">About</h2>

    <div class="c-linky-underline c-linky-visited c-prose-headings c-hyphens">

        <p>I’m Leon, head of digital and marketing at <a href="https://www.suffolklibraries.co.uk">Suffolk Libraries</a>. I developed <a href="https://dootrix.com/verso/">Verso</a>, a new, lightweight self-service system for libraries. I also blog about the web, work and anything else I’m interested in.</p>

    </div>

</section>

<section>

    <h2 class="f4 c-lh-title mt4 c-sans-serif">Work</h2>

    {% assign posts = site.posts | where: "category", "work" %}

    {% for post in posts %}

    <article class="mb4 c-sans-serif c-linky-visited">

        <h3 class="f5 c-lh-title mt0 mb2"><a class="no-underline" href="{{ post.url }}">{{ post.title }}</a></h3>

        <p class="ma0 c-serif">{{ post.excerpt | strip_html }}</p>

    </article>

    {% endfor %}

</section>
