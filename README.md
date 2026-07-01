# Material Design Blog for Hugo

A blog hugo theme with Material Design

## Install

```sh
mkdir theme
cd theme
git submodule add https://github.com/ams-www/material-blog-theme.git material
```

## Update

```sh
git submodule update --init --recursive
```

## Configuration

### Menu

You can add entries to menus from `config.toml`.

See [Add Non-content Entries to a Menu.](https://gohugo.io/content-management/menus/#add-non-content-entries-to-a-menu)

This is a example configuration.

```toml
[[menu.main]]
  name = "Posts"
  url = "/posts/"
  weight = 1
  [menu.main.params]
    icon = "article"

[[menu.main]]
  name = "Tags"
  url = "/tags/"
  weight = 2
  [menu.main.params]
    icon = "label"

[[menu.main]]
  name = "About"
  url = "/about/"
  weight = 3
  [menu.main.params]
    icon = "info"
```

**Note:** The `icon` parameter is optional. If provided, the menu will display Material Design icons. If omitted, it will display text links instead. You can find available icon names at [Google Fonts Icons](https://fonts.google.com/icons).

### Social Links

You can add entries to use `config.toml`.

This is a example configuration.

```toml
[[Params.social]]
  name = "GitHub"
  url = "https://github.com/kons10"

[[Params.social]]
  name = "Misskey"
  url = "https://misskey.io/@heroblineg"
```

### Giscus Comment System

This theme supports the Giscus comment system. You can configure it globally in `config.toml` or override it per page in the front matter.

#### Global Configuration (config.toml)

```toml
[params.giscus]
  enabled = true
  repo = "your-username/your-repo"
  repoId = "R_kgDOXXXXXXXXXX"
  category = "giscus"
  categoryId = "DIC_kwDOXXXXXXXXXX"
  mapping = "pathname"
  strict = "0"
  reactionsEnabled = "1"
  emitMetadata = "1"
  inputPosition = "top"
  theme = "preferred_color_scheme"
  lang = "ja"
  loading = "lazy"
```

#### Per-Page Override (front matter)

You can override Giscus settings for individual pages by adding params in the front matter:

```markdown
+++
title = "Your Post Title"
date = 2024-01-01

[params.giscus]
  enabled = true
  repo = "different-username/different-repo"
  repoId = "R_kgDOYYYYYYYYYY"
  categoryId = "DIC_kwDOYYYYYYYYYY"
+++

Your content here...
```

**Note:** Page-level `params.giscus` settings are merged with site-level settings, with page-level values taking precedence. This allows you to override only specific parameters while inheriting others from the global configuration.
