---
title: 'Hexo theme: NexT'
tags:
  - Hexo
  - tutorial
description: Setting up NexT theme for Hexo
mathjax: true
date: 2022-07-07 12:41:08
---

## install

``` bash
git clone https://github.com/next-theme/hexo-theme-next themes/next
```

## upgrade

``` bash
git pull origin master  # (inside the next folder)
```

## configuration

### In _config.yml under the root folder

- change theme to NexT: change `theme:`*`theme`* in _config.yml to `theme: next`

### In _config.yml under next folder

#### Scheme Settings

- change NexT theme:

``` yml
# Schemes
# scheme: Muse
# scheme: Mist
# scheme: Pisces
scheme: Gemini
```

- darkmode: `darkmode: true`

#### Site Information Settings

- icon: put icon under source/*custom_folder*

  ``` yml
  favicon:
      small: /custom_folder/favicon-16x16.png
      medium: /custom_folder/favicon-32x32.png
      apple_touch_icon: /custom_folder/apple-touch-icon.png
      # safari_pinned_tab: /images/logo.svg
      # android_manifest: /manifest.json
  ```

one can use [this site](https://realfavicongenerator.net/) to generate icons

#### Menu Settings

``` yml
menu:
    # Key: /link/ || icon
    home: / || fa fa-home
    about: /about/ || fa fa-user
    tags: /tags/ || fa fa-tags
    categories: /categories/ || fa fa-th
    archives: /archives/ || fa fa-archive
```

Except for home and archives, all custom pages under the menu section need to be created [manually](https://theme-next.js.org/docs/theme-settings/custom-pages.html)

- Adding tags
    1. `hexo n page tags`
    2. add `type: tags` to front matter
    3. edit *custom-name*/index.md to change content
- Adding categories: similar to tags
- Adding Google Canlendar: check [here](https://theme-next.js.org/docs/theme-settings/custom-pages.html#Adding-Google-Calendar-Page)
- Adding 404 page:
    1. `hexo n page 404`
    2. set `relative_link: false` in root/_config.yml
- Adding others
    1. `hexo n page`*`custom-name`*
    2. edit front matter
    3. edit *custom-name*/index.md to change content (can also use index.html instead of index.md)

icons are from [Font Awesome](https://fontawesome.com/)

You can display/hide icons and badges by setting the followings:

``` yml
menu_settings:
    icons: true
    badges: true
```

#### Sidebar Settings

- avatar: `avatar: url: /NexT_icon/avatar.png`
- social: name: link || icon

  ``` yml
  social:
      GitHub: https://github.com/yourname || fab fa-github
      E-Mail: mailto:yourname@gmail.com || fa fa-envelope
  ```

#### footer

- since *year*: display *year* to the current year
- icon:
  - name: link to [Font Awesome](https://fontawesome.com/)
  - animated
  - color: in HEX code
- copyright: if none, will use the author's name
- powered: whether to show "Powered by Hexo & NexT"

#### post

- preamble text
  - write <!-- more --> to break article manually
  - enable `excerpt_description: true` and have a `description` field in front matter to display the excerpt
  - without the previous two, the whole post will be considered as a preamble and displayed
- `tag_icon: true`: use tag icon instead of #
- donate

  ``` yaml
  reward_settings:
      enable: true

  reward:
      wechatpay: /NexT_icon/wechatpay.jpg
      alipay: /NexT_icon/alipay.jpg
      paypal: /NexT_icon/paypal.png
  ```

- follow me (self-explanatory)
- `post_edit`: enable editing source code (if one pushes source code to GitHub)
- `post_navigation: left`: older post is on the left

#### misc

- `preconnect: true`: Initiating an early connection
- `mobile_layout_economy: true`: reduce margin on device with narrow width
- `codeblock.copy_button.enable: true`: enable copy button
- `back2top: enable: true`: enable back to top button

#### font setting (self-explanatory)

#### search engine optimization (SEO)

1. go to verification methods and choose HTML Tag
2. get `<meta name="verification" content="XXXXXXXXXXXXXXXXXXXXXXX">`
3. copy `XXXXXXXXXXXXXXXXXXXXXXX` to the verification field

## Third-party services

### Math Equations

#### Setting

- `every_page: false`: will not render page unless the front matter has `mathjax: true`
- `mathjax`: more powerful than the `katex` option but slower

  - `enable: true`: enable mathjax
  - `tags: ams`: automatic equaiton numbering if surround by `\begin{xxx} ... \end{xxx}` block

#### prerequisite

install [pandoc](https://pandoc.org/installing.html)
install `hexo-renderer-pandoc`:
  
  ``` bash
  # inside the hexo blog folder
  $ npm un hexo-renderer-marked
  $ npm i hexo-renderer-pandoc
  $ hexo clean
  $ hexo g
  ```

#### [Examples](https://theme-next.js.org/docs/third-party-services/math-equations.html#Examples)

Equation without ams:
$$ x = {-b \pm \sqrt{b^2-4ac} \over 2a} $$

---

Equation with ams:
$$\begin{equation}
x = {-b \pm \sqrt{b^2-4ac} \over 2a}
\end{equation}$$

---

Equaiton with tag
$$ x = {-b \pm \sqrt{b^2-4ac} \over 2a} \tag{custom tag}$$

---

Equation with label (must have either ams or tag):
$$\begin{equation} \label{eq1}
x = {-b \pm \sqrt{b^2-4ac} \over 2a}
\end{equation}$$
and then use `$\eqref{label_name}$` to reference the equation $\eqref{eq1}$

---

Multi-line equation with one ams:
$$\begin{equation} \label{eq2}
\begin{aligned}
x &= +{-b \pm \sqrt{b^2-4ac} \over 2a} \\
  &= -{-b \pm \sqrt{b^2-4ac} \over 2a}
\end{aligned}
\end{equation}$$

---

Multi-line equation with multiple ams:
$$\begin{align}
x &= +{-b \pm \sqrt{b^2-4ac} \over 2a} \\
  &= -{-b \pm \sqrt{b^2-4ac} \over 2a}
\end{align}$$

---

Multi-line equation with multiple ams and certain line without number:
$$\begin{align}
x &= +{-b \pm \sqrt{b^2-4ac} \over 2a} \nonumber \\
  &= -{-b \pm \sqrt{b^2-4ac} \over 2a}
\end{align}$$

### Comment Systems

- `lazyload: true`: don't load the comment system until needed
- disable comments on certain posts: in the front matter, include `comments: false`

#### Disqus (directly quoted from [here](https://theme-next.js.org/docs/third-party-services/comments.html#Disqus))

Disqus is a global comment system that improves discussion on websites and connects conversations across the web.

  1. Create an account and log into [Disqus](https://disqus.com/). Once logged in, click the `GET STARTED` button on the homepage, then select `I want to install Disqus on my site` option and you will see the `Create a new site` interface.
  2. Enter your `Website Name`, which will serve as your Disqus shortname, and select a Category from the drop-down menu. Then click `Create Site` button.
  3. Choose `I don't see my platform listed, install manually with Universal Code`, configure Disqus for your site, and click `Complete Setup` button.
  4. Set the value `enable` to `true`, add the obtained Disqus shortname (`shortname`), and edit other configurations in `disqus` section in the {% label primary@NexT config file %} as following:

      ```yml
      disqus:
        enable: false
        shortname: your-short-disqus-name
        count: true
      ```

## [Analytics](https://theme-next.js.org/docs/third-party-services/statistics-and-analytics.html#Google-Analytics)

- make sure you config the `url` in the hexo _config.yml file
- Google Analytics:

  - create an account
  - edit tracking_id field, fill with `MEASUREMENT ID`
  - others are similar

## Search Services

1. `$ npm install hexo-generator-searchdb`
2. edit hexo _config.yml file and add the followings

    ``` yml
    search:
      path: search.xml
      field: post
      content: true
      format: html
    ```

3. edit next _config.yml file
    - `local_search.enable: true`: enable local search
    - `local_search.top_n_per_article: -1`: show all results per article

## Chat Services

### Chatra

1. Visit [Chatra](https://app.chatra.io/) and create an account
2. edit `chatra.enable: true` and fill in your `chatra.id` in Chatra -> Settings -> Preferences -> Public key

## External Libraries

- Pjax delivers a fast browsing experience
- Fancybox/Medium Zoom allows image zoom in, while Fancybox also supports videos
- lazyload will not load the image until needed. Run `hexo clean` once change this setting
- Quicklink enables preloading and speeds up subsequent page-loads
- motion allows animation, disable it to run faster. Check all effects [here](https://theme-next.js.org/animate/)

## Tag Plugins

NexT has its own [tag plugins](https://theme-next.js.org/docs/tag-plugins/) beside Hexo

## Reference

- [Hexo Youtube Tutorial](https://www.youtube.com/watch?v=Kt7u5kr_P5o&list=PLLAZ4kZ9dFpOMJR6D25ishrSedvsguVSm)
- [NexT: Getting Started](https://theme-next.js.org/docs/getting-started/)
