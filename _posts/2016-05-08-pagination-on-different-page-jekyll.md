---
layout: post
title: Setting up Pagination on a different page in Jekyll
tags: 
  - Jekyll
  - Pagination
category: 
  - IT
  - Guides
---

One of the problems I encountered when setting up this site was shifting the pagination feature to a different page as I wanted my site to be more like a landing page with a blog as one of its side contents. By default, pagination is set up on the home page under `index.html` and placing the same Markdown code under a different page such as `blog.md` or `blog.html` did not automatically work.

wsgeorge gave a great solution on [stackoverflow](http://stackoverflow.com/a/27016002) and below are the steps reproduced for including pagination for the `/blog/` path.

1. Create a new folder called `blog`
2. Create a new html file called `index.html` under the new `blog` folder
3. Copy all the code from `\index.html` into `\blog\index.html`
4. Remove all pagination Markdown code from `\index.html` and customize it the way you want it, as pagination only works on a single page
5. Under `\_config.yml`, add `paginate_path:    '/blog/page:num/'`

As an extra, to keep things consistent, I changed `permalink` from `pretty` to  `/blog/:title/` so that all blog posts start with `/blog/` in their path.

And that's it! For a live working version, you can check it out [here](/blog).