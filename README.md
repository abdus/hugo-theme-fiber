<p  align="center">
<img src="https://i.imgur.com/WXrwYMu.png?cachebuster" alt="hugo theme fiber" />
</p>

<p align="center">
  <img 
    src="https://img.shields.io/github/repo-size/abdus/hugo-theme-fiber"
    alt="github repo size" 
  />
  <img 
    alt="GitHub last commit" 
    src="https://img.shields.io/github/last-commit/abdus/hugo-theme-fiber"
  />
  <img 
    alt="GitHub" 
    src="https://img.shields.io/github/license/abdus/hugo-theme-fiber"
  />
  <img 
    alt="GitHub commits since latest release (by SemVer including pre-releases)" 
    src="https://img.shields.io/github/commits-since/abdus/hugo-theme-fiber/latest?include_prereleases"
  />
</p>

A Hugo theme for the minimalists. Fiber uses minimum JavaScript and CSS to
so that you site could load faster! Also posses a clean UI which is great for
eyes!!

## [Table of Contents](#table-of-contents)

- [Installation](#installation)
    + [Using Submodule](#using-submodule)
    + [Directly downloading theme](#directly-downloading-theme)
- [Features](#features)
  * [SEO Ready](#seo-ready)
  * [Shortcodes](#shortcodes)
    + [ASCIINema](#asciinema)
    + [Can I Use](#can-i-use)
  * [Click to Copy Code](#click-to-copy-code)
  * [Beautiful Notes](#beautiful-notes)
- [Theme Set-up](#theme-set-up)
  * [Listing content in Homepage](#listing-content-in-homepage)
    + [List of blogs, notes etc](#list-of-blogs--notes-etc)
    + [Listing custom content](#listing-custom-content)
  * [Code Highlighting](#code-highlighting)
  * [Menu Items](#menu-items)
  * [Site Title](#site-title)

## Installation

There are two ways this theme could be used with any Hugo-based sites.

1. Using Git Submodules(recommended)
2. Directly downloading theme to `<hugo-site-root>/themes/`

#### Using Submodule

1. Create your site using `hugo new site SITE_NAME`
2. `cd` to `SITE_NAME`
3. Initialize a git repo: `git init`. This is needed because we have to add a git submodule.
4. Add submodule by runing `git submodule add git@github.com:abdus/hugo-theme-fiber.git themes/hugo-theme-fiber`
5. Now, start Hugo server locally using `hugo serve`

If there is an update in theme repository, you can pull them using `git submodule update --remote`

#### Directly downloading theme

> Use this method if you cannot use Git for some reason.

1. Download [this](https://github.com/abdus/hugo-theme-fiber) and extract its
   content to `SITE_ROOT/themes/hugo-theme-fiber/`.
2. Start hugo locally by executing `hugo serve` from terminal.

## Features

### SEO Ready

This theme is loaded with basic SEO as well as with minimal JSON-LD data
from Schema.org

### Shortcodes

Apart from out-of-the-box shortcodes, it does have a few other useful shortcodes
which can be proven helpful at times.

#### ASCIINema

Embed an AsciiNema Cast. Shortcode to use: `{{< asciinema id="id of a public cast" >}}`

#### Can I Use

This shortcode shows latest data from [caniuse.com](https://caniuse.com) website.
Useful for web developers. Example:

```html
{{< caniuse feature="abortcontroller" periods="future_1,current,past_1,past_2" >}}
```

### Click to Copy Code

Visitors of the website can copy content of any codeblock with just one click.
This will not break code indentations!

### Beautiful Notes

Anything you put inside `content/notes`, would get rough-annotations. This makes
it easier to recognize important things from notes.

Rough Annotations are controlled using tags like `strong`, `em` and `strikethrough`.
To generate a new `notes` entry, first you must create directory `content/notes`.
Then use `hugo new notes/file-name.md` to generate a Note. This file would
contain information about how to annotate things with above mentioned tags.

## Theme Set-up

### Listing content in Homepage

Homepage can be configured in two different ways. You can either list your
favorite/most-important section from`content` directory.

Or place custom content inside it.

Or you can do both! Make sure to create a file `content/_index.md` that have
a property `title` inside fromtmatter. This `title` property is useful for
SEO. Example:

```markdown
---
title: "Welcome to my Homepage"
---

<!-- content goes here -->
```

#### List of blogs, notes etc

In order to create a listing of content in homepage, you need to set a
variable called `mainSections` in `config.toml` file. Example:

```toml
[params]
mainSections = ["posts"]
```

#### Listing custom content

To list custom content, simply place them inside `content/_index.md` with
appropriate frontmatter.

### Code Highlighting

By default, Hugo would not use any classes. But this would not work for this
theme as some of the features depends on that.

You need to trun on classes for codeblocks. Here's how you'd do it:

```toml
# file: config.toml
[markup]
[markup.highlight]
codeFences = true
noClasses = false
```

### Menu Items

By default, there's only one menu item in top menu. To add more items in there,
one needs to define menu items inside `config.toml`. Following is an example
from my [site's](https://abdus.xyz) `config.toml`:

```toml
[menu]

  [[menu.main]]
    identifier = "me"
    name = "Me"
    url = "/me/"
    weight = 10


  [[menu.main]]
    identifier = "keys"
    name = "keys"
    url = "/keys/"
    weight = 10

  [[menu.main]]
    identifier = "categories"
    name = "categories"
    url = "/categories"
    weight = 10

  [[menu.main]]
    identifier = "notes"
    name = "notes"
    url = "/notes/"
    weight = 10
```

### Site Title

Site title is controlled by following params in `config.toml`:

```toml
[params]
  title = "abdus.xyz"
  mainSections = ["posts"]
```
