---
title: More on Hexo
date: 2022-07-05 12:11:30
tags: [Hexo, tutorial]
description: Hexo usage
---

This post explores more on how to use Hexo.

## Wrting

### layout

There are mainly three types of layouts: post, draft, and page.
When using `hexo n`, the default layout is `post`. One can change it by setting the `default_laout` in _config.yml.

#### post

Post is just the Markdown files in `source/_posts` folder. You could either create a post by creating a new Markdown file or use the command `hexo n`*`post_name`* to create a new post.

#### draft

When creating a new post, you can use `hexo n draft`*`draft_name`* to create a new draft, which will be stored in `source/_drafts`.
By default, the draft will not be rendered on the server, but you can use `hexo s --draft` to render the draft.
Once done with the draft, use `hexo publish`*`draft_name`* (`hexo p` for short) to publish the draft (move draft from _draft to_posts will do the samve).

#### page

One can use the command `hexo n page`*`page_name`* to create a new page. It will create a new folder with *`page_name`* under `source` folder. Pages will not be shown as a post on the server, and they need to be accessed directly by specifying the path in the URL.

#### scaffolds

The scaffolds folder controls the default layout of the new file. You can create more Markdown files with a different name and use `hexo n`*`scaffold_name`* to create a new file with that type in the `source/_posts`` folder.

### front matter

Front matter looks like the following on the top of the Markdown file:

``` Markdown
---
title: More on Hexo
date: 2022-07-05 12:11:30
tags: [Hexo, tutorial]
---
```

It is written in either YAML or JSON.

#### tags

you can have tags at the very top of the post using syntax `tags: [tag1, tag2, tag3, ...]`

#### categories

you can have categories at the very top of the post using the following syntax

``` yml
categories:
    - [category1, subcategory1, subsubcategory1, ...]
    - [category2, ...]
- ...
```

### tag plugins

You can use tag plugins to quickly add specific content that will get rendered by Hexo. Most tag plugins have the format `{% tag_name %}`. You can find all tag plugins syntax [here](https://hexo.io/docs/tag-plugins). However, tag plugins would not be rendered using the Markdown editor since they are not Markdown syntax nor HTML.

## asset

asset folder store the static resources you want to access in the Markdown file.
Note that all assets should be in a folder that has the same name as the post.

### setup

in _config.yml, change false to true in `post_asset_folder: false`

### images

One can use the tag plugins `{% asset_img image.png Alt Text %}` to add an image if *image.png* is in the folder with the same name as the post

Install hexo-asset-link (npm i -s hexo-asset-link) to support Markdown image syntax (`![Alt Text](image.png)`). The image.png can either be inside a folder with the same name as the post (access via *post_name/image.png*) or in a folder under source (access via */folder_name/image.png*)

## theme

By default, Hexo has the theme landscape inside the `themes` folder.

### install theme

You can find themes [here](https://hexo.io/themes).

1. read README to make sure if there are prerequisites for installation
2. clone the git repository into the `themes` folder
3. change `theme` in _config.yml to the name of the theme folder

### create your own theme

Check [this tutorial](https://www.youtube.com/watch?v=5ROIU_9dYe4&list=PLLAZ4kZ9dFpOMJR6D25ishrSedvsguVSm&index=12) for more information.

## plugins

You can find plugins [here](https://hexo.io/plugins) and install them by `npm install_plugin_name_``*`--save`.

## configuration

### site settings (_config.yml)

You can set site title, author name, language and so on

### important settings

``` yml
default_layout: post
post_asset_folder: true
theme: next
deploy:
  type: git
  repo: <https://oauth2:yourtoken@github.com/username/username.github.io.git>
  branch: master
```

## Reference

- [Hexo Youtube Tutorial](https://www.youtube.com/watch?v=Kt7u5kr_P5o&list=PLLAZ4kZ9dFpOMJR6D25ishrSedvsguVSm)
- [Adding Images to Hexo Posts with Markdown](https://chrismroberts.com/2020/01/06/using-markdown-in-hexo-to-add-images/)
