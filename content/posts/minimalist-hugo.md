---
title: "Minimalist Hugo"
date: 2019-01-08T13:39:17-06:00
draft: true
---

I'm still trying to get my head around hugo's site model. There is
possibly a relationship between the markdown files your create in the
`content` directory and the structure the theme expects in the
`themes` directory. This relationship isn't strictly defined by
convention, some themes expect blog posts to be in a `post` directory
and others look in `posts`. This also means it may not be trivial to
move from one theme to another, you need to check that the structure
of your content fits with that theme's expectations.

In some cases this isn't true, they gather the list of blog posts from
the markdown files that are in any directory. However I can't figure
out how to add a separate page like "about" or "faq".

As I'm modifying the theme I'm learning more about how all of this
fits together. This seems to be the best way to learn Hugo.
