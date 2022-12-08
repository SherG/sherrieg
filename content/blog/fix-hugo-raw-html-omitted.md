---
title: "Merry Fixmas: How to fix the Hugo error <!-- raw HTML omitted -->"
date: 2022-12-08T21:28:14-05:00
publishdate: 2022-12-08
draft: false
toc: false

---

I recently updated one of my Hugo sites and afterwards all links added with HTML were stripped out. In View Source the links were commented out with this: 

```
<!-- raw HTML omitted -->
```

In some cases, the wrapped text was removed. In other cases, not.

Thanks to a <a href="https://stackoverflow.com/questions/63198652/hugo-shortcode-ignored-saying-raw-html-omitted/63206852#63206852" target="blank">Stackoverflow contributor</a>, I got the answer and added this fix below to my config.toml file. Sharing this here in case someone out there's searching for a solution too.

```
[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
```
