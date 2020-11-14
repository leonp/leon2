---
title: Developing the Suffolk Libraries website (v3)
roles: project management, strategy, information architecture
image: sl-website-v3.jpg
alt: "Themed history of women’s rights events listed on the Suffolk Libraries website."
year: 2019-2020
partners: Clearleft
---

## Background

Pre-2019 the Suffolk Libraries website was designed, coded and maintained by me. We updated the site by compiling it locally and pushing changes to Github, which in turn fired a site build. If you’re wondering what most these terms mean, you’re probably not alone – we were using a fairly technical, arcane set of tools to publish content.

We had employed and trained an editor to use Markdown, Jekyll and Github in order to update the website. While [this static set up was fast and stable](/posts/static/), we were limiting the number of possible editors and I was spending too much time coding, especially as my role had changed. The time had come to move to a more traditional content management system (CMS) and hosting.

At the same time, we had been [developing a visual brand for the library service](/work/suffolk-libraries-rebrand/) and a communications strategy that aimed to explain what the library did in terms of its benefits, rather than its purely transactional nature. For example, library websites often assume users know exactly what title they want to borrow, or event they want to go to. We wanted to provide recommendations and suggest events based on interests, while showcasing our staff’s knowledge and expertise.

## Aims

- To move to a traditional CMS that enabled more editors to easily edit and publish content
- To maintain the site’s speed and reliability so a small team’s members didn’t have to worry about hosting and databases
- To enable editors to publish content that was on brand and present it in a more engaging way
- To introduce users to new content and services, while making it easy for them to find information if they knew exactly what they wanted

## Approach

### Information architecture research

We researched and tested a new website structure with digital agency [Clearleft](https://clearleft.com). This consisted of a series of workshops, stakeholder and customer interviews and card sorts with 15 members of the public.

This gave us a (sometimes sobering) insight into how the public saw us. While we were aware of all the great events we run, the eLibrary and free access to services such as Ancestry, often the public had no idea. Many of them saw us simply as a transactional service where you could pick up a book you were interested in, and then return it a few weeks later.

We therefore came up with a website structure that focused on user actions, such as _borrow_, _visit_ and _research_, and mixed several services within these sections. For example, the _Borrow_ section points customers to information on borrowing physical and e-titles, while also providing lots of recommendations and suggestions.

{% include figure.html url="sl-nav.jpg" alt="Screenshot of the Suffolk Libraries website navigation bar consisting of short verbs and nouns such as “Visit” and “Borrow”." caption="The Suffolk Libraries website navigation bar" %}

This use of verbs and customer-friendly nouns also made sure we resisted the tempatation to simply reflect the organisation’s structure in the website. For example, the _Advice_ section contains information from the Health and Wellbeing and Stock and Content teams.

### Choosing a CMS

The next stage involved choosing a CMS to work with. This involved an exercise in prioritising what we wanted, including factors such as speed and stability, maintainability, developer support and the ability to create pages using components such as callouts, promo boxes and accordions.

We looked at several options, narrowing the list down to three:

- WordPress
- Statamic
- Kirby

In the end we plumped for [Statamic](https://statamic.com/), a flat file CMS. We felt this offered a good balance between speed and security and features, mainly because it used text files to store data rather than a database. It also offers the really flexible and extendible [Bard editor](https://statamic.dev/fieldtypes/bard), which enables editors to build complex pages from components and collections.

{% include figure.html url="sl-bard.jpg" alt="Screenshot of the bard editor." caption="The Bard editor. Note how editors can insert graphical elements as well as items from collections such as recommendations and events, and even child page menus. (And yes, you can get married in a library.)" %}

### Content strategy, or: What we publish

With a CMS in place we could start deciding on what components and types of data we could publish in order to meet our communications aims.

Firstly, we have a flexible set of graphical components that can cobine to create pages. These include:

- a “promo picker”, i.e. graphic, text and link to something, in three different sizes
- accordions to handle content that can be hidden and disclosed when required
- alert boxes
- cards
- in-content navigation, such a z-bar pattern, series of cards or a simple list
- embedded content

By combining these elements, we can create complex pages that are flexible enough to convey lots of information. Take [the home page](https://www.suffolklibraries.co.uk/), which consists of a series of promo pickers, embeds and cards:

<details>

	<summary class="pointer c-link b">Show the Suffolk Libraries home page</summary>

	{% include figure.html url="sl-home-page-2.jpg" alt="Screenshot of the Suffolk Libraries home." caption="These components can be easily edited and shifted around the page." %}

</details>
