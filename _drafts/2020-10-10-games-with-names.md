---
title: "Playing games with names"
category: web
---

There are (very broadly speaking) two popular ways to write CSS and HTML. One I would argue is "better", but the other is more practical and perhaps what most website developers should use, especially if several people are working on a large project with some history. What I’m finding interesting is how each approach can encourage a different way of writing.

One approach attempts to squash CSS's "unpredictability" by applying a set of immutable, single use classes to HTML elements. It's mostly what I use on this site: find yourself [a considered CSS API which has good opinions on type, scale, spacing etc.](https://tachyons.io) and before long you'll be fluent in the notation and prototyping well-designed sites in minutes. Let's call this _utility CSS_.

The other applies a more _with the grain_ philosophy by using the cascade thoughtfully. Utility CSS hates the cascade - its strictly mapped nomenclature represents an attempt to remove inheritance and isolate HTML _things_ as much as possible. The idea is that when developer C updates developer M's HTML, developer Y's code doesn't break unexpectedly.

Again, for want of a better term I'll call this an _axiomatic CSS_ approach. When I add classes to everything I implicitly accept that HTML can pretty much be written in any order, and elements don't have any relationship between each other. In fact, I don't really care what elements I'm using because I can control their appearance by slapping a bunch of classes on them.

The axiomatic approach encourages authors to write HTML _properly_ and think about the relationships between elements. By considering these relationships, I don't have to apply classes to everything in order to style - or "fix" - their appearance. Instead, I can [make use of wildcard, adjacent and child selectors](https://alistapart.com/article/axiomatic-css-and-lobotomized-owls/) such as `* + *`.

Apart from a engendering a feeling of doing things the right way, this approach leverages the original expressive power of the cascade. And on a practical level I'm writing less damn code that's doing a lot more.

## An example of how a CSS methodology can affect how you write

I felt the urge to present an introductory paragraph to posts on this site. The styling is very simple:

`font-size: 1.25rem`

To achieve this, I can use either approach. If I use the utility CSS system Tachyons I write this HTML:

`<p class="f4">... The introductory paragraph ...</p>`

or

`<div class="f4">... The introductory paragraph ...</div>`

or even

`<h3 class="f4">... The introductory paragraph ...</h3>`

(The point being I can use _any_ HTML element.)

Which references this CSS

`.f4 {font-size: 1.25rem;}`

An axiomatic approach could look like this:

HTML:

`<p>... The introductory paragraph ...</p>`

CSS:

`h1 + p {font-size: 1.25rem;}`











