
---
title: "Having a play with GitHub Pages"
published: true
---

Getting sick of paying for hosting costs associated with supporting a Wordpress CMS with a LAMP back-end, I had a look around for statically aware site hosting, and came across Jekyll on GitHub Pages.

Having found a few people succesfully staticising their dynamic Wordpress sites, that is where I started. Unfortunately after years of tinkering and migrating my site across GCP, AWS, and Azure my database was in a fairly ugly state. Even using plugins such as WP2Static, I continually ran into issues with my media library, and missing resources for old blog posts. I gave up for the time being, with the plan to eventually resurect my old blog posts from scratch some day.

My first attempts were somewhat futile, not wanting to spend too much time setting up my ruby local environment, and spending what seemed to be too long on making a Jekyll site look pretty. My end result is forking a popular GitHub project https://github.com/github/personal-website. The comprehensive readme made changing a few environmnetalised variables simplistic, and I had a nice site (nlittle.com) up and running in no time. The integration with your GitHub profile was great, as it automagically pulls in yout Avatar and other customisable profile details - which is awesome.

Some easy customisation using Cloudflare for adding the required CNAME DNS entries to use my custom nlittle.com domain and strict SSL enforcement. Cloudflare also gives you the benefit of baked in security and optimisation along with neat dev tools to enable expedited cache busting when you're making regular changes to your site and want to see them quicker. 

A small gotcha, that I found common after reasearch was the lack of a new blank anchor reference for an attachment. My fix was to upload a PDF (my attachment) to my local repository and link it in wiki markdown with the following: 

# Markdown for relative URI attachment in a new tab:
<!--Add in:-->
<a href="{{site.baseurl}}/Nick%20Little_CV.pdf">My CV is here</a>

<!--To this file:--> 
https://raw.githubusercontent.com/colddaemon1/colddaemon1.github.io/master/_posts/2020-05-11-nickcv.md

The escape characters of course required for the spaces in the filename.

So, there you go! I'm stil having a few teething issues - but at least I have a free site up and running that I can post with. 
