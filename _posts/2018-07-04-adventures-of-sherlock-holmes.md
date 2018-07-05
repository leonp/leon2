---
title: 'The Adventures of Sherlock Holmes in HTML'
layout: post
category: work
---

I made a website from the 1892 Sherlock Holmes collection <cite><a href="https://www.adventuresofsherlockholmes.co.uk">The Adventures of Sherlock Holmes</a></cite>. 12 stories, some of which you may well recognise, originally published in serial form in <cite>The Strand</cite> magazine.

I'm not a huge Holmes fan, but these stories provided a few minutes' Victorian pleasure. They _have_ generated some excellent pastiches and adaptations: the best probably being Anthony Burgess' <cite><a href="https://en.wikipedia.org/wiki/The_Devil%27s_Mode">Murder to Music</a></cite>, along with some of the Cumberbatch and Freeman BBC episodes.

So, bearing in mind my slightly _meh_ attitude to the books, and the fact you can easily download them for free, why do this?

## HTML is the best format for online books

What I mean is: I like the idea of navigating to a website and starting to read. You don't need a new device or software; just your browser and a phone, tablet or PC (assuming the text's been responsively styled). Pick up your reading at any time from another device.

The Sherlock Holmes stories seemed just right for this. They're short (most can be read in 15-30 minutes), not too high brow and are freely available in pretty decent HTML on Gutenberg. Victorian readers would have bought the magazine every month; in a better world, you could possibly see modern readers subscribing via RSS, and reading each new episode in their RSS software (another advantage: HTML is infinitely portable). An attentive reader could also start (cross)referencing via the magic of hyperlinks to create all sorts of interesting rabbit holes.

## The technical challenge

Behind the scenes I'm using my normal technical stack: Jekyll, Tachyons, Github and Netlify. The stories are broken down into a chapters collection, which can be used to automatically generate a table of contents. Disappointingly, I discovered only the first story, <cite>A Scandal in Bohemia</cite>, is divided into chapters, so this wasn't really necessary. I did get to use my favourite HTML elements, `details` and `summary` (I've no idea why these aren't all over the internet).

You can bookmark your place in the text by clicking on the `#` sign that appears when you hover over or tap a paragraph. Your mileage may vary on a phone: Firefox on iOS X doesn't seem to add the fragment to any bookmarks when you save them. If you're reading across devices you'll also need to use a cloud bookmarking service (ironically enough, Firefox offers a good, free cloud account). This isn't perfect, but it's keeping it no-login-required pure <span role="img" aria-label="Cheery face">☺️</span>. I'm using the excellent [anchor.js](https://www.bryanbraun.com/anchorjs/) for this.

I've also been using a very simple "framework" I made a few months back. [Jekyll Tachyons](https://github.com/leonp/jekyll-tachyons) creates a basic Jekyll site complete with the Tachyons framework. Most interestingly, you can choose to place styles in the document `head` or in a separate stylesheet, and pick and choose the Tachyons modules it loads. I'm also using it on this site.

There are lots of possibilities here. I could index the text with Algolia to make it searchable and somehow categorised. If only I had the time to look into the potential of plain HTML and text.

- [The Adventures of Sherlock Holmes](https://www.adventuresofsherlockholmes.co.uk)
- [Jekyll Tachyons framework](https://github.com/leonp/jekyll-tachyons)
