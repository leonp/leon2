---
title: 'Building web the right way (and I’m doing it wrong)'
date: 2019-10-13
category: web
featured: false
---

Ever since Heydon published [CSS Inheritance, The Cascade And Global Scope: Your New Old Worst Best Friends](https://www.smashingmagazine.com/2016/11/css-inheritance-cascade-global-scope-new-old-worst-best-friends/) I’ve had a nagging feeling I’ve been building websites _the wrong way_. Since then, Heydon has published [Every Layout](https://every-layout.dev/) with Andy Bell, which proposes a set of standard web modules, layouts and components built on what you might term _traditional_ CSS techniques, making use of inheritance and the cascade.

Every Layout is a great site, not least in how it conceptualises web design. It’s full of nuggets like <q>CSS works best as an exception-based language</q>. This contradicts the approach I’ve used for the last three years or so, which is to try and obliterate all inheritance, and therefore all exceptions, by using class names that map directly to CSS property value pairs (`db` equates to `display: block`, for example). Declarations like `* + * {margin-top: 1.5rem;}` are very rare.

Now, using a radically functional/atomic approach (via [Tachyons](https://tachyons.io)) has worked well for me. I can get a “responsive” website up and running in minutes – I know the notation inside out, even for relatively complex modules such as flex. I don’t have to create “semantic” compnents such as `card` in my CSS; instead, I build them with HTML and call them with includes and layouts. Inside you’ll find the same, consistent set of terse class names.

However, there are several problems with this approach, which are all derived from one fundamental
