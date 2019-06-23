# Libris

A documentation theme for Stackbit.

## Documentation

### Structure

All documentation pages are located in the `docs` folder. You should group the related documentation pages into sections and keep them in subfolders, like `docs/about` or `docs/getting-started`. Here is the example documentation structure:

```
├── content
│   ├── docs
│   │   ├── about               [docs section]
│   │   │   ├── features.md
│   │   │   ├── index.md        [section parent page]
│   │   │   └── overview.md
│   │   ├── getting-started
│   │   │   ├── index.md        [section parent page]
│   │   │   ├── installation.md
│   │   │   └── quick-start.md
│   │   ├── community.md        [page with no children]
│   │   ├── faq.md              [page with no children]
│   │   └── index.md            [docs root page]
│   │   └── ...
│   ├── ...
```

### Navigation

The navigation of the documentation is displayed on the left side on the documentation pages and defined in the `docs_toc.yml` file located in the `data` folder.

In `docs_toc.yml` you should specify the documentation root page and sections in the order you want them to appear in the navigation.

Root definition:

- `title` - the title that will be displayed in the documentation navigation
- `path` - the page path relative to the `content` folder

Sections definition:

- `title` - the title that will be displayed in the documentation navigation
- `subtitle` - the subtitle of the section used in the `overview` template ([see below](#additional-templates))
- `type` - can be either `page` or `collection`. `collection` is specified for documentation subfolders, and `page` is specified for single documentation pages that have no children.
- `path` - the page or subfolder path relative to the `content` folder

### Templates

There are two special templates for documentation pages:
- `docs_parent`. Used for section parent pages.
- `docs`. Used for all other documentation pages, including the documentation root page, section child pages and pages with no children.

For section child pages you should define the `nav_order` parameter in the front matter so you could arrange them in the desired order. For instance:

```
---
title: Features
nav_order: 2
template: docs
---
```

```
---
title: Overview
nav_order: 1
template: docs
---
```

### Callouts

To add a callout to your documentation, simply use the following html markup:

```
<div class="important">
  <strong>Important:</strong> 
  This is the "Important" callout block of text. It indicates a warning or caution.
  Use it for an important message. 
</div>
```

```
<div class="note">
  <strong>Note:</strong> 
  This is the "Note" callout block of text. It signifies a general note.
</div>
```

### Syntax Highlighter

To enable syntax highlighting in your code blocks, add a language identifier. For example, to syntax highlight JavaScript code, specify `javascript` next to the tick marks before the fenced code block:

````
```javascript
if (condition) {
  code to run if condition is true
} else {
  run some other code instead
}
```
````

## Main Navigation

The items of the main menu located at the top can be defined either inside the page front matter or inside the `config.yml` file.

To add a page menu item, you should define the `menus` parametter in the front matter of the page. For instance:

```
---
title: Welcome to Libris
menus:
  main:
    weight: 2
    title: Docs
template: docs
---
```

To add a global menu item, you should define it inside the root `menus` field inside `config.yml`. For instance:

```
menus:
  main:
    - identifier: github
      title: GitHub
      url: "https://github.com/"
      weight: 6
```

## Additional Templates

Besides the usual templates (`blog`, `page`, `post`) and documentation templates mentioned above (`docs`, `docs_parent`), there are two additional templates that can be used for pages:

- `overview` - used to list all the documentation sections in a neat grid.
- `showcase` - used to showcase the users of your product.

## Social Links

To display social icons in the footer, update the `social.json` file located in the `data` folder. You can use any icon supported by [Font Awesome](https://fontawesome.com/icons?d=gallery&s=brands) and just need to specify the appropriate Font Awesome class name as the `icon` value.

## Color palettes

Libris supports the following color palettes:

- blue (default)
- green
- navy
- violet

To change the color palette, update the `palette` variable in config.yml.

## Credits

- [Lato](https://fonts.google.com/specimen/Lato). Licensed under the [Open Font License](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL_web).
- [Font Awesome icons](https://fontawesome.com/). Licensed under the [Font Awesome Free License](https://fontawesome.com/license/free).
- [Unsplash images](https://unsplash.com/). Licensed under the (Unsplash License)[https://unsplash.com/license].
- [Prism syntax highlighter](https://prismjs.com/). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [Reframe.js](https://github.com/dollarshaveclub/reframe.js). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [Smooth Scroll](http://github.com/cferdinandi/smooth-scroll). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [Gumshoe](https://github.com/cferdinandi/gumshoe). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
- [clipboard.js](https://zenorocha.github.io/clipboard.js). Licensed under the (MIT License)[https://opensource.org/licenses/MIT].
