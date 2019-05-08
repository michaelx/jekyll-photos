# jekyll-photos

Dead simple solution to add a photo gallery to a Jekyll site.

It’s easy to extend Jekyll with a small dose of creativity. Thanks to the template language Liquid, the only thing you often need is a new layout file. That’s what we use here as the foundation:

* `/_layouts/photo_set.html`: The layout for each photo set, displaying every photo of a photo set.
* `photos.html`: The overview page, displaying all photo sets.
* `berlin.md`: An example photo set.
* `/images/photos/`: The directory for all photos. You can change it in `/_layouts/photo_set.html` if you like.

## Demo

*jekyll-photos* is unstyled, so that you can easily add your own CSS-flavor. Examples from my personal website: [Overview page](https://michaelxander.com/photos/), [a photo set](https://michaelxander.com/photos/new-york/).

## Installation

Copy the files and folders of `/jekyll/` into the root directory of your Jekyll project.

> **Note:** If you already have a layout called `photos` or `photos_set`, just rename the files of *jekyll-photos*.

## Usage

Once everything is in place, you only need to add a new page with the following YAML front matter block:

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

`set` represents the photo set name and `size` the number of photos that the set contains.

Now, rename the three photos to berlin-1.jpg, berlin-2.jpg, and berlin-3.jpg, and move them to `/images/photos/`. That’s it!

> **Note:** If you want to use a different file format for your photos or images, you need to adjust `/_layouts/photo_set.html`, or make it configurable. You could also use [Jekyll File Exists](https://github.com/michaelx/jekyll_file_exists) to automatically detect what extension is available.

## Extensibility

The goal of *jekyll-photos* is to show how easy it is to implement new site functions. It’s intentionally hold to the basics, which makes it easy to customize. For example, you could add photo categories or lazy load photos (like I do on my personal site).