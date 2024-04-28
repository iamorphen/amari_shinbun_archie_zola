# amari\_shinbun\_archie\_zola

The theme for the [amari shinbun](https://git.sr.ht/~deepcode/amari_shinbun).
This theme is a modification of
[archie-zola](https://github.com/XXXMrG/archie-zola).

## Installation

In your Zola project:

```
cd themes
git clone https://git.sr.ht/~deepcode/amari_shinbun_archie_zola
```

You can also add the theme via `git submodule add`.

Add the following in the top level scope of `config.toml`:

```toml
theme = "amari_shinbun_archie_zola"
```

## Configuration

```toml
# View mode; options: {auto | dark | toggle}
mode = "toggle"

# Fetch font and Javascript files from an external CDN?
useCDN = false

favicon = "/icon/favicon.png"

# Copyright attribution shown in the footer.
copyright = "your name"

# Your Google Analytics ID.
ga = "XXXX-XXXXX"

# Config your supported languages. At least one is required.
[extra.translations]
languages = [{name = "en", url = "/"}]

# Configure the multi-language menu and other text.
[[extra.translations.en]]
show_more = "Read more ⟶"
previous_page = "← Previous"
next_page = "Next →"
posted_on = "on "
posted_by = "Published by"
read_time = "minute read"
all_tags = "All tags"
menus = [
    { name = "Home", url = "/", weight = 2 },
    { name = "All posts", url = "/posts", weight = 2 },
    { name = "About", url = "/about", weight = 3 },
    { name = "Tags", url = "/tags", weight = 4 },
]

# Configure social icons in the footer. At least one is required.
[[extra.social]]
icon = "" # Options: {github | gitlab | twitter | <more?>}
name = "" # Link text.
```

### LaTex Math Formula Support

This theme supports LaTex math formulas by using [KaTeX](https://katex.org/).

In your `config.toml`:

```toml
[extra]
katex_enable = true
```

Then, you can use LaTex math formulas in your Markdown files:

```
$$
{x: \mathbf{Num},\ y: \mathbf{Num} \over x + y : \mathbf{Num} }\ (\text{N-Add})
$$
```

You can also use the inline and block style formulas:

```
1. \\( \KaTeX \\) inline
2. \\[ \KaTeX \\]
3. $$ \KaTeX $$
```

### Content Configuration

`transparent = true` in the prelude in `content/posts/_index.md` is part of the
pagination implementation.

Control the pagination, tagging, and authorship in `_index.md` with:

```toml
paginate_by = 3
sort_by = "date"

[taxonomies]
tags = ["tag_one", "tag_two"]

[extra]
author = { name = "foo", social= "<url>" }
```
