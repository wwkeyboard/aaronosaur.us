---
title: "Minimalist Hugo"
date: 2019-01-08T13:39:17-06:00
draft: false
---

The [hugo](http://gohugo.io) getting started guide covers the first
few steps to setting up a hugo site. However it's a little confusing
how to get started with your own theme. I was confused how the theme
related to the content so I started building my own theme. Here are a
few notes about how I accomplished that.

The first step is to actually follow the [quick
start](https://gohugo.io/getting-started/quick-start/) guide, it walks
you through some of the basic concepts. A big trick here is in "Step
4" the content you add may need to be in a specific directory
depending on the theme. Some themes make special changes based on the
structure of the `content/` directory. It's hard to fully understand
how it works without building a theme yourself. Hopefully the
documentation for the theme explains any idiosyncrasies. If not pick a
different theme to start with.

The next step is to build a minimal theme yourself. Start by creating
a new empty project, then add the directory `themes/basic`. From here
add a `themes/basic/theme.toml` file. It doesn't need much:

``` toml
name = "Basic"
license = "MIT"
```

Next add a directory `themes/basic/layouts/_default` and add the file
`baseof.html` to that directory. This file will be the initial
template of _all_ of the pages on the site(there are ways to change or
override this file, these kind of specifics are covered in the hugo
docs). This file will have the `<html></html>` tags and the content
will follow the template language that's pretty well explained in the
hugo docs.

To get the index to display you'll also need to add a
`themes/basic/layouts/index.html` layout to get the file
`content/_index.md` to render the site's home page. index.html doesn't
need to be complex.

``` markdown
{{ define "main" }}
<h1>{{ .Title }}</h1>

{{ .Content }}

{{ end }}
```

Will get something to render. This will take the title from the front
matter of `_index.md` and the content of that file and render them in
the template.

Beware that if you start the development server you'll need to set the
post's `draft: false` variable to `true` before it'll show up. I've
been caught by this several times. This will also require you to set
the theme in the project's `config.toml`, this is done in the top
level, the same way the "quick start" guide instructs.

These are quick notes to try and help me remember the process for
starting this. If you have further questions or find an error please
reach out to me on [Twitter](https://twitter.com/wwkeyboard).
