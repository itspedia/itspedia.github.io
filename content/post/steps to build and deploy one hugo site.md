---
# Common-Defined
title: "Steps to Build and Deploy one Hugo Site"
date: 2025-03-27T21:20:23+08:00
lastmod: 2025-03-27T21:29:20+00:00
draft: false
tags: ["Hugo", "Webhook", "Git"]
categories: ["index", "Hugo"]
author: "hongxing"

# User-Defined
# You can close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: false
# You can also define another contentCopyright
contentCopyright: '<a rel="license noopener" href="https://creativecommons.org/licenses/by-nc-nd/4.0/" target="_blank">CC BY-NC-ND 4.0</a>'
reward: false
mathjax: true
---

## Build one website locally by using Hugo
This can be done by following the guide, [quick-start](https://gohugo.io/getting-started/quick-start).

## Deploy the website on GitHub repository
You can use [GitHub Pages](https://docs.github.com/en/pages/quickstart) to [host your hugo site](https://gohugo.io/host-and-deploy/host-on-github-pages).

## Deploy the website on ECS 

- Have one ECS instance
- Setup web server, like nginx, on this ECS instance
- Use [webhook](https://github.com/adnanh/webhook) and git to pull the static file from git repository
  the flag -secure is used to enable https access.
