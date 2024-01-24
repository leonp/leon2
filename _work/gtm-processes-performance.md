---
title: Improving GTM processes and website performance
roles: website management, agency management
image: psi-pass.jpg
alt: "Core Web Vitals assessmeent graphs, all showing green with a “Pass” above them."
year: 2023
work-order: 1
summary: "Third-party scripts added through Google Tag Manager can be a major source of website performance problems. By managing and auditing our GTM container we improved page performance by 100%."
---

Most organisations use Google Tag Manager (GTM) to add third party scripts to their website. These will often include chatbots, analytics and marketing services, such as Facebook tracking. This has several apparent benefits:

- Marketing teams don’t have to go to their developers to install tracking/remarketing code
- Marketing teams can give agencies access to their GTM account and thereby their website
- Other departments can install third-party apps such as a chat client by adding a prepared HTML snippet to GTM

This sounds great, but with great power comes great responsibility. Third party scripts can seriously affect the speed at which your website loads, especially on low-spec devices, or anything not connected to reliable, high-speed internet. In other words, they can make browsing your site on a mobile difficult. That’s before you even consider the ethical implications of adding Meta tracking code to your user’s device.

Google also uses page performance as a major factor in deciding how to rank pages in search results.

Before I worked at Anglia Ruskin University (ARU), several parties were able to add third party scripts to GTM:

- The web team
- The marketing team
- Marketing agencies

Over time, this meant we were loading hundreds of kilobytes of scripts, often unnecessarily. This became evident when we began routinely measuring our [PageSpeed Insights](https://pagespeed.web.dev/) test score. The home page averaged between 15-20/100 on each test.

A typical university website loads the following third-party scripts. The weights and loading times are provided by a PageSpeed Insights test:

- Gecko chat engine: 287kb / 306ms
- Gecko chat engine fonts: 179kb / na
- Clarity: 29kb / 419ms
- TikTok analytics: 254kb / 323ms
- GTM itself: 113kb / 718ms
- gtag1 (for Google ads): 92kb / inc. in GTM
- gtag2 (for Google ads): 80kb / inc. in GTM
- Hotjar analytics: 60kb / 97ms
- Google Analytics: 21kb / 30ms
- Facebook Events: 91kb / 46ms
- Snapchat: 39kb
- Bing ads: 17kb
- Quantcast: 14kb
- LinkedIn ads: 23kb

This comes to a total of 1.3MB and takes 2 and a half seconds to load on a mobile phone on a 4G connection – that’s on top of any images and other content you’re loading. If you have two agencies’ scripts running, double that.

**Your GTM container needs to be managed in order to minimise the impact of running third party scripts.** Here are four steps I took to get the container in order, and ultimately improve our PageSpeed Insights score by 100%.

## 1. Set up a process for adding new scripts to your GTM container (and document it)

Only one person or team should be responsible for adding scripts to the website, and that should be an employee, not an agency. In ARU’s case, that’s me or, if I’m not available, a member of the web team.

GTM allows changes to be tested, staged and merged before being committed to the website, so agencies can still create tags, triggers and events. However, the container manager should be the only person who commits those changes to the default workspace.

As well as determining _who_ can make changes to the default workspace it’s also important to establish rules for _naming_ these changes. These will include:

- Identifying who is making the change (in the tag or trigger title)
- Identifying the service the tag relates to
- A summary of the change (in the tag or trigger title)
- A longer description of the change (in the tag or trigger text box)

As the number of tags and triggers in your worskpace can proliferate, it’s important to be able to find and review them quickly. Here’s an example of a good tag:

`[Agency abbreviation] - Tag - Google - UG Visited ARU on demand`

This format allows us to:

- Identify all tags created by the specific agency
- Identify all tags relating to Google services
- Understand what the tag does

Finally, document these processes and rules. This can be useful for new members of the team and when you’re working with a new agency. It also allows you to quickly find all the outgoing agency’s tags and triggers, so these can be paused or deleted.

## 2. Manage and audit your scripts

Contracts come to an end, and you’ll find yourself onboarding new SEO or advertising agencies at some point.

When an agency leaves you should remove all their tags and triggers. They don’t just affect your site’s performance – they can still gather website data.

Removing tags is relatively simple. However, triggers can be difficult if you’re using them to fire tags not provided by the departing agency. You’ll need to go through all your triggers and record what tags they fire. If a trigger fires a tag you want to keep, rename it using your established convention. It’s laborious work, but will ensure you’re not breaking anything.

## 3. Only load scripts on the pages you need them

Once you’re on top of what tags and triggers you’re loading in your container, you can start to refine _how_ you load them.

By default, a trigger and its associated script will load when the page loads and on every page on the website. Sometimes you want scripts to run everywhere, but more often than not that’s unnecessary.

{% include figure.html url="page-view-all-page-views.jpg" alt="Default GTM trigger creation options." caption="The easiest and quickest way to create a trigger." %}

For example, your chatbot probably doesn’t need to load in your _Policies and documents_ section. Hotjar – a service that records visits and activity on your site – probably only needs to load on key pages, or anywhere you’re troubleshooting.

GTM offers a set of trigger filters that help determine whether a script loads. The easiest to use is the _Page path_ filter. Let’s say you’re only interested in analysing a directory on your site. You could set the filter value to contain `/path/to/your/directory`. Conversely, you can tell a trigger to fire when it _doesn’t_ contain a particular directory path.

{% include figure.html url="hj-afterLoad-contains-subject-areas.jpg" alt="The trigger editing screen showing a selected directory." caption="Setting a page path restricts where tags are triggered." %}

If you want to analyse more than one page or directory, you can set up several triggers.

## 4. Set up a new afterLoad custom event

Having considered where tags and their scripts are triggered on the site, the final piece of the jigsaw is to control _when_ they fire during the page loading process.

Web pages load in a specific order. GTM allows us to fire tags at any stage during this process. By default, a trigger can fire during:

- **Consent initialisation**. This is when GTM will check whether the visitor has consented to load any third party scripts (including Google Analytics).
- **Page initialisation**. This is before the page starts building.
- **Page view**. This is as the page starts to build.
- **DOM view**. This is when the page has built its structure by parsing its HTML.
- **Window loaded**. This is when the page has finished downloading any resources it needs, such as images, embeds and javascript.

By default, scripts will load at the Page view stage. While this ensures they’re loaded even if, say, another script or image doesn’t load, this can have a dramatic effect on the visitor’s experience. Recall how long third-party javascript can take to load. If you choose to fire a tag at this stage, it will _completely_ block the page loading. The visitor will literally see nothing until it’s done.

You could choose to trigger a script at the Window loaded stage, but this would block the downloaded images, scripts and embeds rendering and running. Instead, we can create a custom event that runs 1.5s after the Window loaded stage, and tell triggers to fire after this custom event.

Don’t worry if that sounds complicated. There are quite a few [how-to guides](https://adigital.agency/blog/pagespeed-tricks-for-loading-third-party-scripts-via-gtm) out there, and it’s a trivial piece of work for an agency with any GTM exprience.

Once we have our custom event (which we don’t have to name _afterLoad_, but it should be descriptive), we can set up a new _Custom event_ type trigger that:

- Only fires in certain conditions, such as when a visitor goes to a spcified page path
- Fires 1.5s after the Window loaded event

{% include figure.html url="hj-afterLoad-contains-subject-areas.jpg" alt="The trigger editing screen showing a selected directory." caption="Make sure you use the exact event name that you specify in your javascript." %}

Once we do this, we can be sure that the page content has loaded before our third-party scripts, resulting in a better experience for our visitors. This is what PageSpeed Insights measures when evaluating a page.

## The results

By loading scripts once, in the appropriate places and at the right time in the page loading process, we can see dramatic improvements in our PageSpeed Insight scores.

{% include figure.html url="pgr-psi.jpg" alt="PageSpeed Insights results for ARU’s postgraduate research page, showing a score of 43/100." caption="43/100 isn’t perfect, but it’s a big improvement." %}

Take [ARU’s postgraduate research page](https://www.aru.ac.uk/research/postgraduate-research). Before we audited and updated our GTM tags and triggers, this would score between 15-25 in any given test. Now it scores between 40-50. There are still improvements to be made, but these are down to the developer team. Just as we can damage user experience through GTM, we can also make make it better.





