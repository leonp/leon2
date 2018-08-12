---
title: 'Getting round GDPR. A case study: Techradar'
layout: post
category: web
---

Many news and big blog sites have introduced onerous and confusing popovers since the introduction of GDPR in May. Unfortunately, this will no doubt result in GDPR banner blindness, where users will simply click 'Accept', thereby allowing the site to install 50 adtrackers, slowing the website to a crawl.

This is not GDPR's fault. [The guidelines are very clear](https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr/lawful-basis-for-processing/consent/). Websites have to:

- ask users to explicitly opt in to share their data
- not use legalese or similarly unclear language

It would be _very_ easy to design a banner that did this. Something like:

{% include pull-quote.html text="We can share your data with advertisers so you get tailored adverts. <a href='#'>Share your data &rarr;</a>" %}

Of course, no-one would ever click this link because no-one has any interest in being served adverts. As a consequence, sites that rely on serving tracking scripts, advertising beacons etc. are getting round GDPR by a technique they know inside out: <i>obfuscation</i>. They _could_ rephrase this request to collect data by being honest about why they need it:

{% include pull-quote.html text="We can share your data with advertisers so you get tailored adverts. <strong>We rely on the money we get from these adverts to pay our journalists. Please <a href='#'>share your data &rarr;</a></strong>" %}

But old habits die hard. Here's the popover [Techradar](https://www.techradar.com/uk) displays when you visit the site:

{% include figure.html url="techradar.jpg" alt="Popover with small text and confusingly labelled buttons" caption="The Techradar advertising opt-in dialogue" %}

There are a few [dark pattern](https://darkpatterns.org/) techniques at play here:

- You only get to access the site immediately by clicking 'I accept'. By not opting-in to advertising you're going to have to do some extra work to see an article. Although technically speaking you're opting in, the fact you have to do this in order to use the site at all makes it virtually compulsory.
- The 'I accept' link is bigger than the _I don't accept_ link (which isn't labelled quite that clearly, of course), and styled as a button. The _I don't accept_ link is labelled 'Show purposes' (and marked up as a `button`, oddly enough) and set in pale blue, hard to see 12 pixel type. The implication is it's a secondary, perhaps technical action.
- 'Show purposes' is confusing. I don't actually want to see how you use cookies. What I want to do is _not_ opt-in. Will clicking this link allow me to not opt in? It should be labelled _I don't accept_. I'm really having to think in order to make my way through this UI.

Unfortunately, clicking 'Show purposes' to not opt-in doesn't end the process there. Instead, it reveals the following:

{% include figure.html url="techradar2.jpg" alt="Another popover with small text and confusingly labelled buttons" caption="The second popover. You're not done yet." %}

Another popover to negotiate, using the same dark pattern techniques. The primary action is not to not opt-in (we're in the land of the double negative), but to accept the site's cookies. The secondary, 'technical' option is to _Reject all_. Presumably that'll do the job:

{% include figure.html url="techradar3.jpg" alt="A third popover with small text and confusingly labelled buttons" caption="Another popover. Another small, confusingly labelled link to click." %}

I get the feeling Techradar _really_ don't want us not to opt-in. Again, the primary action leads us to opt-in, and the alternative is very confusingly labelled. Presumably, 'Leave' means _leave the website_? But I do want to read the article. Oh well, I'll click 'Leave', just to see what happens, but Techradar have put me in a situation where it seems I _have_ to accept cookies in order to use the site. Let's see what happens if you do click 'Leave'. Ah, success! Sort of:

{% include figure.html url="techradar4.jpg" alt="A third popover asking the user to not use an adblocker" caption="Perhaps unsurprisingly, Techradar don't like adblockers. So they throw a popover at you." %}

At least the text here is clearer, and Techradar are honest about why they don't want you to use an adblocker. Incidentally, we'd need to change our more straightforward banner:

{% include pull-quote.html text="We can share your data with advertisers so you get tailored adverts. <strong>We rely on the money we get from these adverts to pay our journalists. Please <a href='#'>share your data &rarr;</a> and turn off your adblocker.</strong>" %}

This is an easy one. We'll continue with our Adblocker, thank you. And we're there. Of course, this being Techradar, we get a popover for our troubles:

{% include figure.html url="techradar5.jpg" alt="A popover asking users to sign up to an email newsletter" caption="Because I really wanted to sign up for a newsletter at this stage." %}

## Are Techradar complying with GDPR?

Technically speaking you _could_ argue Techradar are getting explicit consent in order to collect data about their visitors.  They're obviously not operating in the spirit of the regulations, but I also think they're in breach in at least two areas:

- They make it seem as if you can't use the site unless you opt-in. [According to the ICO website](https://ico.org.uk/for-organisations/guide-to-the-general-data-protection-regulation-gdpr/lawful-basis-for-processing/consent/), you have to <q>Avoid making consent to processing a precondition of a service</q>.
- On the same page, the ICO says you must <q>Be clear and concise</q>. Although this is a subjective requirement, I can't see how anybody could interpret this process as clear and concise in any way.

Bearing in mind the murky history of online advertising, and some sites' reliance on it as a source of income, it's depressingly inevitable that organisations would find ways to get round the new regulations. The only way GDPR will achieve what it set out to do will be through prosecutions. If they don't, people will just click or tap 'Accept' and the online advertising industry will carry on as before, while claiming it's doing the right thing. I'm skeptical. If you've any interest in privacy and you'd like to keep websites fast, make sure you're using a browser that puts you in control of trackers and cookies and use an adblocker. Firefox (or, better still, [Firefox Focus](https://www.mozilla.org/en-GB/firefox/mobile/) on a mobile) is the obvious choice.
