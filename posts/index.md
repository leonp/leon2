---
layout: default
title: Posts
order: 4
is_pagination: true
pagination:
  enabled: true
---

{% include inline-cats.html %}

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

    <footer class="measure-wide center pt2 bt b--light-gray">

        <div class="cf mb3">

          {% if paginator.previous_page %}

              <div class="fl">

                <a class="b dark-blue hover-dark-red" href="{{ paginator.previous_page_path | prepend: site.baseurl }}">&larr; Newer posts</a>

              </div>

          {% endif %}

          {% if paginator.next_page %}

              <div class="fr tr">

                <a class="b dark-blue hover-dark-red" href="{{ paginator.next_page_path | prepend: site.baseurl }}">Older posts &rarr;</a>

              </div>

          {% endif %}

        </div>

      {% if paginator.page_trail %}

          <ul class="list mb0 mh0 mt3 pa0 flex flex-wrap justify-start">

          {% for trail in paginator.page_trail %}

            {% capture destination %}
            {{ trail.path | replace: '.html', '' }}
            {% endcapture %}

            {% capture current %}
            {{ page.url | replace: '.html', '' }}
            {% endcapture %}

            <li class="w-20 w-10-ns ph1 mb1">

                <a href="{{ trail.path | prepend: site.baseurl }}" class="f6 db tc ph3 pv2 bg-light-gray dark-blue hover-bg-dark-pink hover-white{% if current == destination %} bb bw2 b--dark-gray{% endif %}">{{ trail.num }}</a>

            </li>

          {% endfor %}

          </ul>

      {% endif %}

    </footer>

{% endif %}
