---
title: "Using Staticman for comments on a Jekyll site"
category: web
layout: post
---

When you move from a "dynamic" CMS (such as WordPress) to a static system (like Jekyll) you lose comments. You can use something like [Disqus](https://disqus.com/) instead, but hosted, javascript-powered systems have disadvantages:

- You have to login to a service such as Google or Facebook (or Disqus itself) to make a comment
- The comments don't live on your website, but on Disqus's servers. If Disqus goes, so do your comments.
- The comments don't exist on your site until they're called by javascript, so they don't exist to search engines when they crawl your site

Now, if we're looking to move our comments from Facebook, Twitter <i>et al</i> back to our own websites (and we should be), this is a sad state of affairs. We might consider why we moved from WordPress in the first place when it does blogging so well. But there are solutions to this seemingly intractable problem. The foremost being [Staticman](https://staticman.net).

In this post I'll provide an overview of what Staticman does and take you through some of the pitfalls you need to avoid in order to get it working properly. I refer you to [Michael Rose's excellent, comprehensive Staticman and Jekyll guide](https://mademistakes.com/articles/improving-jekyll-static-comments/) for more detailed instructions that'll help you get more "advanced" features working.

## What you'll need

Staticman is smart. This is how it works:

1. A user submits a comment from your website through a standard HTML form (no javascript required)
2. Staticman receives the comment
3. If you've turned off moderation, Staticman pushes the comment to a Github repository. If you've hooked up your website to a Github repository (if you're using a service like Github Pages, Netlify or CloudCannon, for example) this will normally fire a site build, meaning the comment will appear within seconds or minutes.
4. If you haven't turned off moderation, Staticman makes a pull request, which you can choose to accept and merge into your production branch. Again, this will normally fire a site build.

All these moving parts mean you'll need:

- The know how to code an HTML form (although you could always copy and paste something)
- Your website hosted in a Github repository
- Automated site builds
- The know how to handle relatively complex Liquid templates and Jekyll data files (or collections), and a Staticman config file. Again, you may be able to copy and paste something.

Assuming you have all these, or you're willing to copy and paste and experiment, you should be able to get comments working fairly easily. Especially if you avoid these problems:

## Get the Staticman URL right

The Staticman docs provide an incorrect URL for your comment form to submit data to. It should be `https://api.staticman.net/v2/entry/{your github name}/{the github repo}/{the branch}/comments`. The `comments` bit is important.

This means your `form` element would look something like `<form method="post" action="https://api.staticman.net/v2/entry/leonp/leon2/master/comments">`.
