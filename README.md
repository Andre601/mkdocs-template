[MkDocs]: https://www.mkdocs.org/

[squidfunk]: https://github.com/squidfunk
[Material Theme]: https://github.com/squidfunk/mkdocs-material

[Material Dark Theme]: https://github.com/henrywhitaker3/mkdocs-material-dark-theme
[henrywhitaker3]: https://github.com/henrywhitaker3

[facelessuser]: https://github.com/facelessuser
[PyMdown Extensions]: https://github.com/facelessuser/pymdown-extensions/

[Netlify]: https://netlify.com

[tabbed.css]: https://github.com/Andre601/mkdocs-template/blob/master/docs/assets/css/extensions/tabbed.css
[mkdocs.yml]: https://github.com/Andre601/mkdocs-template/blob/master/mkdocs.yml
[theme]: https://github.com/Andre601/mkdocs-template/blob/master/theme

[LICENSE]: https://github.com/Andre601/mkdocs-template/blob/master/LICENSE

# MkDocs Material Template
This is a template repository for anyone that wants to use the MkDocs Material Theme.  
It also ships with a premade Dark theme and some additional settings that are useful.

## Premade Settings

### Theme
This repo ships with the [Material Dark Theme] made by [henrywhitaker3].  
This theme essentially makes the docs appear darker, while keeping things like code-highlighting working.

If you want to use it, uncomment the `extra_css:` section and either `- 'assets/css/styling/dark.css'` or `- 'assets/css/extra.css'` in the [mkdocs.yml].

### Extensions
This repository comes packed with the following extensions:

- Admonition
- Codehilite
- toc
- [PyMdown Extensions]

You can add/remove extension at your own discretion, but keep in mind that some extensions either conflict with others, or require additional setups like f.e. the Tabbed extension (Requires the [tabbed.css] file to be used).

### Altering HTML files
You can alter specific parts of the documentation by adding html files to the [theme] folder.  
After you've added the HTML files, make sure to also uncomment the `custom_dir: 'theme'` section of the [mkdocs.yml].

## Use on GitHub
If you want to use this template for making documentation using GitHub Pages, follow this small tutorial:

### Clone the template
First clone this repository by clicking on the "Use this template" button.  
Give a name for the repository and confirm your action.

### Setup GitHub Actions
> **Requirements**:  
> - `gh-pages` branch setup. Easiest way would be to clone your repository locally and make an initial `gh-deploy` using MkDocs.

This repo already ships with a `deploy.yml` file inside the `.github/workflows` directory and a `requirements.txt` which is needed for the GitHub action to work properly.  
If you alter the action and use additional dependencies, can you just add them to the aformentioned txt file to automatically download them.

It's important to point out, that in the GitHub Action file you need to replace `Andre601` and `mkdocs-template` with your user/organisation name and the repository name respectively.

The Action should now trigger every time you push changes to the mkdocs.yml file or towards the `docs` or `theme` directory.

### Change pages
Now you can setup the pages. To do that, simply add, edit and/or delete Markdown files and folders inside the `docs` folder.

**Tip**:  
You can call the file `index.md` to make it the default page of a folder.  
If, for example, the wiki is hosted under `andre601.github.io/mkdocs-template` and you create `docs/about/index.md` will the content of the index.md be shown when connecting to `andre601.github.io/mkdocs-template/about`

Remember to always add the pages to the `nav` section in the `mkdocs.yml` so that MkDocs will display them in the navigation.

## Using Netlify
You may want to use [Netlify] to deploy changes or make previews of Pull Requests.

Setting up Netlify is simple and only requires you to do a few steps.

### Authorize their App
You need to allow the Netlify App/Bot to have access to your repository.

### Create files
This repository already ships with a `runtime.txt` and `requirements.txt` which makes sure that Netlify uses the right Python version and also downloads the required dependencies respectively.  
By default does Netlify use an outdated version of Python, which is also no longer supported (Don't ask me why they do that...) and the `runtime.txt` forces Netlify to use Python 3.7.

After the above steps can you just setup netlify on their website and you're good to go.

## Credits
A big thank you goes to the following people/groups:

[MkDocs] for providing the software, to generate documentation.
[squidfunk] for the [MkDocs Material Theme].
[henrywhitaker3] for the [Material Dark Theme]
[facelessuser] for the [PyMdown Extensions]

## License
This template is served under the MIT license.  
Read the [LICENSE] file for more info.
