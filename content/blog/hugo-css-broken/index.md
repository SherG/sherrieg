---
title: "CSS no longer working on your Netlify Hugo site?"
date: 2022-07-04T21:28:14-05:00
publishdate: 2022-07-04
draft: false
toc: false
---

This weekend the CSS on this site suddenly stopped rendering. After focusing on recent Github changes I recalled that I had recently switched on Netlify's Asset Optimization. I use it for all my sites and turned it on without really thinking about it. 

On a hunch, I turned it off, and everything works fine again. (I had previously verified the CSS - there aren't any errors in it.) 

Here's what I think was happening: my CSS was already bundled and minified. Turning on Asset Optimization causes Cloudfront to take action to bundle and minify the CSS (along with several other actions). And it seems this can cause the CSS to not render. 

I found a forum discussion where a WordPress user experienced something similar but with Cloudflare, so this is where I got the idea. 

Sharing here, so if you are experiencing the same issue, and you have the same conditions, you may want to try turning Asset Optimization off. 
