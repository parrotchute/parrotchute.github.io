---
layout: post
title: Responsive images in Jekyll without plugins or bootstrap
tags: 
  - Jekyll
  - CSS
category: 
  - IT
  - Tutorials
published: true
---


http://stackoverflow.com/a/25564005
http://failtime.freeshell.org/2015/06/21/responsive-images-with-jekyll/
https://thornelabs.net/2014/11/30/centering-images-with-jekyll-and-markdown.html

Works with Markdown/Kramdown so you don't need to resort to adding classes to img tags to get it to work. 

Probably one of the most lightweight way to achieve this.


```css
img {
    max-width: 100%; 
    display:block; 
    height: auto;
    margin: 0 auto;
}
```
Remove `margin: 0 auto;` if you do not want the image centered.