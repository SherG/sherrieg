---
title: "About this site"
date: 2022-03-29T21:28:14-05:00
publishdate: 2022-03-29
draft: false
toc: false
categories:
- Websites
tags:
- Hugo
- GoatCounter
---

I never had a website back in the 1990s - so I finally gave myself a 1990s-style website. Okay - that was a joke. 

I launched this site because I wanted to have a place to share interests and experiences that don't fit in with my other websites. 

## Style

I wanted something spartan, taking inspiration from the blogs of developers who include nothing unnecessary and engineer according to purpose. 

(<em>Exception example: the hilarious hamburger menu on <a href="https://www.zachleat.com/" target="blank">Zach Leatherman's site</a>. But even that cascading menu has a purpose: it suggests a question: "Is a hamburger menu the best choice for every website?" Zach's navigation solution - simple hyperlinked text - takes one click. </em>)

I previously had a site on this domain (a couple of years ago), with a slick design, but in recent years I've tired of the "glitz glut" -- When everyone can have a visually 'beautiful' website, a beautiful website doesn't mean much. 

Often there's a disconnect between the purpose of the website and what the design "says." Example: someone who is just thinking of having an online store, and has no products, can put up a site that looks like Nordstrom's. Or, when someone who just wants a personal blog has a design that conveys: "Every article is a publishing event!" 

I think there are cases where a bit of visual modesty can better communicate what a site is about. And in some cases (I'm not using my blog as an example), you can stand out <em>more</em>.


## Speed: the non-negotiable

This site gets a 100/100 on Google's Page Speed Insights. That's thanks to the JAMstack approach, the developer's set up, and Netlify.

It's hard to beat .8 seconds to interactive for mobile and .2 seconds to interactive for desktop. 

My <a href="https://www.spearfishcap.com/" target="blank">Spearfish site</a>, another JAMstack site deployed via Netlify, also scores 100/100. I add that fact in case you're unfamiliar with Netlify or JAMstack and think only sites - or homepages - with no images can be fast.

There are plenty of examples of high-performance JAMstack sites that have lots of 'bells-and-whistles' - like <a href="https://www.smashingmagazine.com/" target="blank">Smashing</a> magazine.


## Details

This theme is from software engineer Zachary Betz. I've made a few style edits. My goal was to get it up and running and tweak things as I go along. So I'll be adding tags and categories later, for example. 

* I'm <a href="https://github.com/SherG/zblogtest/" target="blank">using Github</a> and deploy via Netlify. 
* Given this is a Hugo site, all content is created in Markdown. That also makes it easy to switch to a new design. 
* I'm not using a CMS although it's easy to append the Netlify CMS if I want to later. (I've become accustomed to creating articles in Markdown directly in Github. I'm currently switching to using the Drafts app.)
* I added <a href="https://www.goatcounter.com/" target="blank">GoatCounter</a> analytics. There's no personal tracking and no GDPR needed. 

### Adding GoatCounter to a Hugo Site

* If you have a config.toml file, follow the <a href="https://robb.sh/posts/adding-goatcounter-analytics-to-hugo/" target="blank">instructions here</a>. 
* If instead you have a config.yaml file, look for "params" and add your GoatCounter subdomain:

```yaml
goat_counter_code: sherrieg
```

So my params section now looks like this: 

```yaml
params:
  show_search: true
  show_debug_table: false
  goat_counter_code: sherrieg
  date_format: Jan 2, 2006
```


On this site, in the themes directory, under layouts/partials there's a related script-goatcounter.html file:

```go
{{ if not site.IsServer }}
  {{ with site.Params.goat_counter_code }}
    <script
      data-goatcounter="https://{{ . }}.goatcounter.com/count"
      src="//gc.zgo.at/count.js"
      async
    ></script>
  {{ end }}
{{ end }}
```
