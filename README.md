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

### Giscus comments

The theme supports [Giscus](https://giscus.app/) comments on single pages. First, enable GitHub Discussions for the repository used for comments and install the Giscus GitHub App for that repository. Then add the repository and Discussion category values provided by the Giscus configuration page to your site's `config.toml`:

```toml
[params.giscus]
  enabled = true
  repo = "owner/repository"
  repoId = "YOUR_REPOSITORY_ID"
  category = "Announcements"
  categoryId = "YOUR_CATEGORY_ID"

  # Optional settings
  mapping = "pathname"
  strict = "0"
  reactionsEnabled = "1"
  emitMetadata = "0"
  inputPosition = "bottom"
  theme = "preferred_color_scheme"
  lang = "ja"
```

The comments section is not rendered unless `enabled` is `true` and all four required repository/category values are set. It is included on single pages by default; set `comments = false` in a page's front matter to disable it for that page. Optional settings use the values shown above when omitted.

See the [Giscus documentation](https://giscus.app/) for repository requirements and available configuration values.
