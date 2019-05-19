---
layout: default
title: Posts
in_nav: true
order: 3
is_pagination: true
pagination:
  enabled: false
---

<!-- {% include inline-cats.html %} -->

<p class="f4 mv4-ns">I wrote a blog between 2008&#8211;2018, posting at least twice a month on the web and anything else that interested me. These are the posts that gathered the most interest in that time.</p>

<section>

    {% assign posts = site.posts | where: "featured", "true" %}

    {% for post in posts %}

    <article class="mb4 c-sans-serif c-linky-visited">

        <h2 class="f4 c-lh-title ma0"><a class="no-underline" href="{{ post.url }}">{{ post.title }}</a></h2>

        <p class="mv1 f6 gray"><time>{{ post.date | date: "%b %d, %Y" }}</time></p>

        <p class="ma0 c-serif">{{ post.excerpt | strip_html }}</p>

    </article>

    {% endfor %}

</section>

<!-- {% if paginator.total_pages > 1 %}

    <footer class="measure-wide center pt2 c-sans-serif">

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

          <ul class="list mb0 mh0 mt3 pa0 flex flex-wrap justify-start c-sans-serif">

          {% for trail in paginator.page_trail %}

            {% capture destination %}
            {{ trail.path | replace: '.html', '' }}
            {% endcapture %}

            {% capture current %}
            {{ page.url | replace: '.html', '' }}
            {% endcapture %}

            <li class="w-20 w-10-ns ph1 mb1">

                <a href="{{ trail.path | prepend: site.baseurl }}" class="f6 db tc ph3 pv2 bg-light-gray dark-blue hover-bg-dark-blue hover-white{% if current == destination %} bb bw2 b--dark-gray{% endif %}">{{ trail.num }}</a>

            </li>

          {% endfor %}

          </ul>

      {% endif %}

    </footer>

{% endif %} -->
