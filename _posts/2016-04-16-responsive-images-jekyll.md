---
layout: post
title: Responsive images in Jekyll without plugins or Bootstrap
tags: 
  - Jekyll
  - CSS
category: 
  - IT
  - Guides
---

```css
img {
  max-width: 100%; 
  display:block; 
  height: auto;
}
```
That is all you need. `margin: 0 auto;` can also be added to center images. If looking for a quick fix is what you needed, you can skip the rest of this post as it will be expanding on the explanation and some other ways of achieving the same results.  

The above snippet also Bootstrap's way of making responsive images, except that Bootstrap has it in a `img-responsive` class instead. The difference between both approaches is that with Bootstrap's way, the `img-responsive` class has to be applied manually to all images, while the other is already applied to all images automatically. The second approach is much better in Jekyll, as you do not have to include HTML syntax within Markdown/Kramdown just to insert a class.

For those who downloaded Lanyon from [here](http://lanyon.getpoole.com/), it is a very outdated version that does not have responsive images and has this in `public\css\poole.css`:

```css
img {
  display: block;
  margin: 0 0 1rem;
  border-radius: 5px;
}
```

If minimal edits is what you want, all you need to do is to include `max-width: 100%;` and be done with it. Alternatively, you can head over to their [repository](https://github.com/poole/lanyon) and download all the latest CSS versions.


To include auto centering of the images, I created a `public\css\poole.css` and inserted this:

```css
img {
  margin: 0 auto;
}
```

And then linked to the new stylesheet in `_includes\head.html`, applying it to all pages:

```html
<link rel="stylesheet" href="/public/css/custom.css"/>
```

While it's much faster and convenient to add `margin: 0 auto;` to `poole.css`, I found it good practice to separate all custom made CSS from those that come as defaults from ready made themes. That way, it'll be much easier for me to update a theme by overwriting the existing files, while still leaving all my own edits intact.