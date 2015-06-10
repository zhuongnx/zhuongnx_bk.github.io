---
layout: post
title: "Blogging Basics"
date: 2015-06-10 13:11:58 +0700
comments: true
categories: octopress
---
Octopress offers some rake tasks to create post and pages preloaded with metadata and according to Jekyll's naming conventions.
It also generates a global and a category based feed for your posts (You can find them in `atom.xml` and `blog/categories/<category>/atom.xml`)

If you are using zsh in the command line, then please add `alias rake=noglob rake` to your zsh config to prevent the `zsh: no matches found` error that occurs when running these rake tasks.

<!-- more -->

## Blog Posts

Blog posts must be stored in the `source/_posts` directory and named according to Jekyll's naming conventions: `YYYY-MM-DD-post-title.markdown`
The name of the file will be used as the url slug, and the date helps with file distinction and determines the sorting order for post loops.

Octopress provides a rake task to create new blog posts with the right naming conventions, with sensible yaml metadata.

### Syntax

```sh
rake new_post["title"]
```

`new_post` expects a naturally written title and strips out undesirable url characters when creating the filename. The default file extension for new posts is `markdown` but you can configure that in the `Rakefile`.

### Example

```sh
rake new_post["Blogging basics"]
# Creates source/_posts/2015-06-10-blogging-basics.markdown
```

The filename will determine your url.
With the default permalink settings the url would be something like `http://site.com/blog/2015/06/10/blogging-basics/`

Open a post in a text editor and you'll see a block of yaml front matter which tells Jekyll how to processes posts and pages.

```sh
---
layout: post
title: "Zombie Ninjas Attack: A survivor's retrospective"
date: 2011-07-03 5:59
comments: true
external-url:
categories:
---
```