# Parchment Docs Theme

A minimal two-column parchment-style documentation theme for GitHub Pages.

Designed for reflective projects, personal tools, research notebooks, and quiet technical documentation.

## Features

- Two-column layout with left navigation panel.
- Handwriting-inspired, eye-friendly typography.
- Parchment-style background with soft ink colours.
- Mobile-responsive. Sidebar collapses into top navigation.
- Zero local setup. Works directly with GitHub Pages.

## Live example

See the theme in action on the InkSlate documentation site: [https://aninditabasu.github.io/inkslate/](https://aninditabasu.github.io/inkslate/).

An example page, with all the supported elements, is at [https://aninditabasu.github.io/parchment-docs/](https://aninditabasu.github.io/parchment-docs/)

## How to use

In your own repository root, create a file named `_config.yml` with the following code snippet:

```
remote_theme: AninditaBasu/parchment-docs
plugins:
  - jekyll-remote-theme
```

Then, in each Markdown file, add the following line to the frontmatter:

```
layout: default
```

Your site is now set up to automatically use the parchment-docs layout every time that you build it through GitHub Pages.

## Recommended folder structure

```
_layouts/
  default.html
assets/
  style.css
images/
  image1.png
topics/
  topic_1.md
  topic_2.md
index.md
```

## Configuration

You can customise the `parchment-docs` theme by specifying fields in your site's `_config.yml` file. Here's an example snippet that you can use:

```
title: The title of your website
author: Your name
description: A human-friendly, SEO-friendly, RAG-friendly description.

remote_theme: AninditaBasu/parchment-docs
plugins:
  - jekyll-remote-theme

```

The following settings are available:

| Key            | Purpose                                       |
| -------------- | --------------------------------------------- |
| `title`        | Displayed as the site name in the sidebar     |
| `author`       | Used in the footer copyright line             |
| `description`  | Used in the HTML `<meta>` description tag     |
| `remote_theme` | Must be set to `AninditaBasu/parchment-docs`  |
| `plugins`      | Must include `jekyll-remote-theme`            |

## Navigation

The navigation menu is defined in the `_layouts/default.html` file. Edit the `<nav>` section to add or delete links from the ToC, like this:

```
<nav>
  <a href="{{ '/' | relative_url }}">Home</a>
  <a href="{{ '/topics/getting_started.html' | relative_url }}">Getting started</a>
  <a href="{{ '/topics/advanced_settings.html' | relative_url }}">Advanced settings</a>
</nav>
```

## Logos and favicons

You can display a custom logo in the sidebar and a favicon in the browser tab. Place your images in an `images` folder in your project root, like so:

```
images/
  logo.png
  favicon.png
```

Logo requirements:

- Recommended size: 256 × 160 px
- Format: `PNG` with transparent background
- Recommended orientation: Horizontal

Favicon requirements:

- Recommended size: 32 × 32 px
- Format: `PNG`

You can have your favicon in more than one size, for example:

| File                  | Purpose              |
| --------------------- | -------------------- |
| `favicon-32.png`      | Browser tabs         |
| `favicon-16.png`      | Bookmarks            |
| `favicon.png` (256px) | Hi-DPI / pinned tabs |

If you do, place all your favicon files in the `images` folder and call them in the `default.html` file.

```
images/
  favicon-16.png
  favicon-32.png
  favicon.png
```

In the `default.html` file:

```
<link rel="icon" type="image/png" sizes="32x32" href="{{ '/images/favicon-32.png' | relative_url }}">
<link rel="icon" type="image/png" sizes="16x16" href="{{ '/images/favicon-16.png' | relative_url }}">
<link rel="icon" type="image/png" href="{{ '/images/favicon.png' | relative_url }}">
```

## License

MIT
