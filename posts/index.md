---
layout: default
title: Posts
order: 4
is_pagination: true
pagination:
  enabled: true
---

<section class="c-constrain-kids c-linky-visited c-linky-underline">

    <p>I blogged about the web, politics, books and other bits and pieces between 2008 and 2018. I publish <em>everything</em> here, and syndicate elsewhere (or <a href="https://indieweb.org/POSSE"><abbr title="Publish on your own site Syndicate Elsewhere">POSSE</abbr></a>).</p>

</section>

{% for post in paginator.posts %}

<section class="c-prose-headings">

    <ul class="list mb0 mh0 mt4 pa0 c-linky-visited">

    {% unless post.note %}

    <li class="mb4"><a class="f4 pv1 no-underline b" href="{{ post.url }}">{{ post.title }}</a> <time class="mt1 db normal f6 gray lh-copy">{{ post.date | date: "%b %d, %Y" }}</time></li>

    {% endunless %}

    {% if post.note %}

    <li class="mb4 f6"><span class="ttl small-caps tracked">Note: </span>{{ post.content | strip_html | truncate: 200 }} <a class="db f7 pv1 no-underline" href="{{ post.url }}"><time class="mt1 normal f6 lh-copy">{{ post.date | date: "%b %d, %Y" }}</time></a></li>

    {% endif %}

    </ul>

</section>

{% endfor %}

{% if paginator.total_pages > 1 %}

<footer class="cf c-linky-visited">

  {% if paginator.previous_page %}

  <div class="fl">

    <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}">&larr; Newer posts</a>

  </div>

  {% endif %}

  {% if paginator.next_page %}

  <div class="fr tr">

    <a href="{{ paginator.next_page_path | prepend: site.baseurl }}">Older posts &rarr;</a>

  </div>

  {% endif %}

</footer>

{% endif %}
