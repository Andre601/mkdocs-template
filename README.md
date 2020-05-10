[Material Dark Theme]: https://github.com/henrywhitaker3/mkdocs-material-dark-theme
[henrywhitaker3]: https://github.com/henrywhitaker3

[extra.css]: https://github.com/Andre601/wiki-template/tree/master/docs/assets/css/extra.css
[tabbed.css]: https://github.com/Andre601/wiki-template/tree/master/docs/assets/css/extensions/tabbed.css
[mkdocs.yml]: https://github.com/Andre601/wiki-template/tree/master/mkdocs.yml

# MkDocs Material Template
This is a template repository for anyone that wants to use the MkDocs Material Theme.  
It also ships with a premade Dark theme and some additional settings that are useful.

## Premade Settings

### Theme
This repo ships with the [Material Dark Theme] made by [henrywhitaker3].  
This theme essentially makes the docs appear darker, while keeping things like code-highlighting working.

If you don't want to use it, remove/comment out the `@import "styling/dark.css";` part in the [extra.css] file.

### Extensions
This repository comes packed with the following extensions:

- Admonition
- Codehilite
- toc
- PyMdown Extensions
    - Emoji (With the MaterialX emoji extension)
    - Superfences
    - Tabbed
    - Details
    - MagicLink

You can add/remove extension at your own discretion, but keep in mind that some extensions either conflict with others, or require additional setups like f.e. the Tabbed extension (Requires the [tabbed.css] file).

### Altered HTML files
The template changes the footer of the docs by overriding the [main.html] file with own settings.
This change only includes small colour changes to the text and altering the credits text, to mention MkDocs, Material for MkDocs and the PyMdown Extensions.

To no longer use this, just comment out `custom_dir: 'theme'` under the `theme` section in the [mkdocs.yml].

## Use on GitHub
If you want to use this template for making documentation using GitHub Pages, follow this small tutorial:

### Clone the template