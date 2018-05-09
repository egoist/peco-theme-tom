# peco-theme-tom

A [Peco](https://github.com/egojump/peco) theme which is ported from the blog of Jekyll's author [Tom Preston-Werner](http://tom.preston-werner.com/)

## Installation

```bash
yarn add peco-theme-tom stylus stylus-loader
```

We write CSS in Stylus so `stylus` and `stylus-loader` are required here.

## Usage

In your Peco config:

```yaml
theme: tom
```

__👉 Preview the theme online: https://peco-theme-tom.netlify.com/__

## Recommended config

```yaml
title: Your Site
description: Describe your site
email: email@you.com
# Generate RSS feed
feed: true
url: https://your-website.com

theme: tom
themeConfig:
  github: username
  twitter: username
  # Links in navbar
  nav:
    - title: home
      link: /
    - title: somewhere
      link: https://example.com
```

## License 

MIT &copy; [EGOIST](https://github.com/egoist)