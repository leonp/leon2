---
title: "In defence of view source"
category: web
---

Ever late to the web discussion party, I read CSS Tricks’ hardline stance on <i>View Source</i>, where Chris argues he’d be happy to get rid of it because you can glean more info about a page from dev tools.

{% include figure.html url="view-source.jpg" alt="The Firefox right-click menu in OS X with View Source highlighted" caption="View source is just a right-click away" %}

While this is true, I think <i>View Source</i> offers an easy to load glimpse into the document author’s (or designer's) mind; what they consider important, what they’re good at, what they’re not good at, even their “ethics” (assuming the bastard hasn't inlined and minified everything, although even this suggests something):

{% include figure.html url="skinny-minified.jpg" alt="The source code from the Skinny Guardian website" caption="Skinny Guardian, inlined and minified" %}

This is not information you'll get quite as readily from dev tools, which focuses on the page's granular, technical foundations rather than the way it's been authored. When you <i>View Source</i> you can see straight away how the author indents their <abbr title="HyperText Markup Language">HTML</abbr>, any comments they've added, how keen they are on divs, how keen they are on classes, whether they overuse IDs and what approach (if any) they take to CSS. That's a lot of information from skimming a page:

{% include figure.html url="lp-source.jpg" alt="The source code leonpaternoster.com" caption="Is that an unnecessary closing <code>div</code> I can spy?" %}

So interpreting my page, you could perhaps conclude I generally employ the correct HTML elements (a "proper" use of `b`, no less), use `divs` sparingly but practically, use Tachyons (or some form of atomic <abbr title="Cascading Style Sheets">CSS</abbr> framework) and use a templating system that messes up indentation slightly. As to what this says about me, I'll leave up to you.

The document's `head` is always interesting, giving clues to how SEO-crazy the author is, what software they use and some of the "ethical" considerations they've made:
