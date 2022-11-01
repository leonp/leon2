---
title: "Building a mobile-first university website: Use and report on Google Core Web Vitals"
date: 2022-08-13 16:22:00 +0000
category: web
featured: true
---

I started work as [ARU](https://aru.ac.uk)’s web manager on the last day of May. Since then I’ve gone through the usual round of introductions and getting to know the structure of a large organisation. It’s been fun – and hard work.

I’ve identified performance as the most important area to improve on the website, especially on mobile devices. There are several reasons for this:

- Obviously, prospective students are an important audience, and, according to Google Analytics, more than 70% of visitors to our [Clearing page](https://aru.ac.uk/clearing) use a mobile device.
- ARU has a healthy international student cohort, especially from India. While we should be wary of making assumptions about connectivity and device usage (for example, Indian traffic has a similar level of 4G connectivity as the UK), we need to cater for the possibility that visitors from some countries will not be using a high-spec device on a reliable network, or will be more likely to use a mobile.
- Websites that perform well on mobile are more likely to perform well on any device and screen. Additionally, visitors will use different devices in different contexts at different times. For example, student A may initially scout courses on a mobile during a bus journey. They may then apply for a course using a laptop at home.
- Google likes sites that appear in their search results to perform well. Google search is the biggest source of traffic to ARU.
- We generally score poorly in [Lighthouse reports](https://web.dev/performance-scoring/).
- Better performance will mean more student applications.

In this post I’m going to start outlining what I’m doing in my role as web manager, rather than what I feel we can do technically or with the design of the website.

## Start measuring Google Core Web Vitals (CWVs)

Are [CWVs](https://web.dev/vitals/) the only measure of performance? Nope. Are they a replacement for watching people use your site? No. Do they measure how quickly sites load after you click/tap on a link on a Google search results page (SERP) above everything else? Probably.

But I think they reflect how likely a site performs well. Reducing javascript bundle sizes, optimising images and reducing layout shift are uncontroversial optimisations.

More cynically, if most of our website traffic comes from Google, it makes sense to focus on how Google evaluates performance. And how quickly it loads after a visitor clicks/taps a link _is_ important.

**CWVs have traction.** Developers are familiar with CLS, TTFB etc., while our SEO agency are saying we need to improve our scores. After all, their job is to get our courses appearing higher up SERPs. In turn, the marketing team is aware of the importance of performance. This is good news, as third-party scripts applied via Google Tag Manager (GTM) and the drive to use more imagery and video in the cause of “engagement” will lower our scores.

{% include figure.html url="gtm.jpg" alt="A bus labelled with complex performance improvements stuck on a train track is smashed into by a train labelled “GOOGLE TAG MANAGER”." height="668" width="500" caption="Image from <a href='https://twitter.com/heydonworks/status/1549677090303315969/photo/1'>Heydon</a>." %}

Finally, everyone’s aware of Google and probably believes it knows a thing or two about performance – and why it’s so important. (Incidentally, just last week an agency sent a PDF ranking websites by their Lighthouse scores – it’s a smartish piece of marketing.)

## Start reporting on CWVs

Lighthouse provides colour-coded performance scores, and even a pass or fail. That’s useful for the big, high-level reports I‘m sending out every month, along with Site Improve accessibility and QA ratings.

Is a score out of 100 anything more than a broad indication of how well a site performs across thousands of different devices? In thousands of different contexts? Probably not. But that’s not the main benefit of reporting Lighthouse scores. I’m hoping that raising awareness means that performance becomes more of a consideration when we develop a new feature, design a component, discuss the website roadmap or add a new script via GTM. If it does, that will only benefit our visitors.

## How to report on CWVs

I've started by putting the home page through a [Page Speed Test](https://pagespeed.web.dev/) whenever I need a figure. It’ll fluctuate, but it’s better than nothing. I’m looking at services like [Treo](https://treo.sh/) to automate tests, score over a period of time, and monitor different pages, regions, devices and network conditions.

