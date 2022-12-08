---
title: "Merry Fixmas: How to fix the Hugo error <!-- raw HTML omitted -->"
date: 2022-12-08T21:28:14-05:00
publishdate: 2022-12-08
draft: false
toc: false

---

I recently updated some stackbit files on one of my Hugo sites and afterwards all hyperlinks added with HTML were commented out + made invisible on the live site. In View Source the links were commented out with this: 

``` html
<!-- raw HTML omitted -->
```

In some cases, the wrapped text was invisible on the live site. In other cases, not. 

Thanks to a <a href="https://stackoverflow.com/questions/63198652/hugo-shortcode-ignored-saying-raw-html-omitted/63206852#63206852" target="blank">Stackoverflow contributor</a>, I got the answer and added this fix below to my config.toml file. Sharing this here in case someone out there's searching for a solution too.

``` toml
[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
```

<aside>&#x1F4A1; Fun fact: TOML stands for <a href="https://toml.io/en/" target="blank">Tom's Obvious Minimal Language</a></aside>
