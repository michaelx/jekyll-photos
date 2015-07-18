# jekyll-photos

Dead simple solution to add a photo gallery to a Jekyll site.

It’s pretty easy to extend Jekyll with a small dose of creativity. Thanks to the template language Liquid, the only thing you often need, is just a new layout file. And well, that’s what we use here as the base:

* `/_layouts/photos.html`: The layout for the overview page, displaying all photo sets.
* `/_layouts/photo_set.html`: The layout for each photo set, displaying every photo of a photo set.
* `photos.md`: The overview page that uses the *photos* layout.
* `berlin.md`: An example photo set (uses the *photo_set* layout).
* `/images/photos/`: The directory for all photos. You can change that in `/_layouts/photo_set.html` if you like.

## Demo

It comes unstyled, so that you can easily add your own CSS-flavour, like I did on my personal site: [Overview Page](http://michaelxander.com/photos/) & [Example Photo Page](http://michaelxander.com/phoenix/)

## Installation

Copy the files and folders of `/jekyll/` into the root directory of your Jekyll project.

Note: If you already have a layout called "photos" or "photos_set" you should edit the files of *jekyll-photos* first.

## Usage

Once everything is in place, you just have to add a new page with the following YAML front matter block:

```yaml
---
layout: photo_set
title: Berlin
permalink: /berlin/
description: "An example photo gallery."

photos:
    set: berlin
    size: 3
---
```

The important part is:

```yaml
---
photos:
    set: berlin
    size: 3
---
```

`set` represents the photo set name and `size` the number of photos that given set contains.

Now rename your 3 photos to: berlin-1.jpg, berlin-2.jpg, berlin-3.jpg and move them to `/images/photos/`. That’s it, you don’t have to do anything else.

Note: If you want to use .png’s you need to adjust `/_layouts/photo_set.html`.

## Extensibility

The goal of *jekyll-photos* is to show how easy it is to implement new site functions. It’s intentionally hold to the basics, and therefor super easy to customize. You could add photo categories for example, or lazy load your photos like I do on my personal site.