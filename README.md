[MkDocs]: https://www.mkdocs.org/

[squidfunk]: https://github.com/squidfunk
[Material Theme]: https://github.com/squidfunk/mkdocs-material

[Material Dark Theme]: https://github.com/henrywhitaker3/mkdocs-material-dark-theme
[henrywhitaker3]: https://github.com/henrywhitaker3

[facelessuser]: https://github.com/facelessuser
[PyMdown Extensions]: https://github.com/facelessuser/pymdown-extensions/

[extra.css]: https://github.com/Andre601/wiki-template/tree/master/docs/assets/css/extra.css
[tabbed.css]: https://github.com/Andre601/wiki-template/tree/master/docs/assets/css/extensions/tabbed.css
[mkdocs.yml]: https://github.com/Andre601/wiki-template/tree/master/mkdocs.yml
[LICENSE]: https://github.com/Andre601/wiki-template/tree/master/LICENSE

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
- [PyMdown Extensions]
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
First clone this repository by clicking on the "Use this Template" button.  
Give a name for the repository and confirm your action.

### Setup pages
Now you can setup the pages. To do that, simply add, edit and/or delete Markdown files and folders inside the `docs` folder.

Note:  
You can call the page `index.md` to make it the default page of a folder.  
If, for example, the wiki is hosted under `Andre601.github.io/wiki-template` and you create `docs/about/index.md` will the context of the index.md be shown when connecting to `Andre601.github.io/wiki-template/about`

### Setup GitHub Actions
It's recommendet to use GitHub Actions for automatic publishing of the pages on GitHub Pages.  
To do that, first create a file called `requirements.txt` and add the following content to it.  
```txt
mkdocs-material>=5.0.0
```

Next, create a yml file in the `.github/workflows` directory and add the following content to it:  
```yaml
name: Deploy Site

on:
  push:
    paths: 
    - 'docs/**'
    - '**.yml'
    - 'theme/**'
    branches:
    - master

jobs:
  build:
    runs-on: [ubuntu-latest]
    steps:
    - uses: actions/checkout@v2
    - name: Set up Python 3.7
      uses: actions/setup-python@v1
      with:
        python-version: 3.7
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip setuptools
        python -m pip install -r requirements.txt
    - name: Deploy Files
      run: |
        git config user.name "github-actions[bot]"
        git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
        git remote add gh-token "https://${{ secrets.GH_TOKEN}}@github.com/purrbot-site/Docs.git"
        git fetch gh-token && git fetch gh-token gh-pages:gh-pages
        python -m mkdocs gh-deploy --clean -m "Your commit message (optional)" --remote-name gh-token
        git push gh-token gh-pages
```

The above setup will checkout the code, setup Python 3.7, install all required dependencies and then push the changes to the GitHub Pages branch using MkDocs' `gh-deploy` command and also using the GitHub Actions account for it.  
Note that you need to setup a Personal Access Token (PAT) and set it as Secret with the name `GH_TOKEN` for the repository.

The Action should now trigger every time you push changes to any .yml file or towards the `docs` or `theme directory`.

## Using Netlify
You may want to use [Netlify] to deploy changes or make previews of Pull Requests.

Setting up Netlify is simple and only requires you to do a few steps.

### Authorize their App
You need to allow the Netlify App/Bot to have access to your repository.

### Create files
You need to create a `requirements.txt` and `runtime.txt` file in order to make Netlify work properly with your setup.

The requirements.txt needs to have `mkdocs-material>=5.0.0` set as content and the `runtime.txt` needs `3.7` to be set.  
This is because Netlify uses an outdated and no longer supported version of Python by default and therefore needs to be changed.

After that, just setup netlify on their website and you should be good to go.

## Credits
A big thank you goes to the following people/groups:

[MkDocs] for providing the software, to generate documentation.
[squidfunk] for the [MkDocs Material Theme].
[henrywhitaker3] for the [Material Dark Theme]
[facelessuser] for the [PyMdown Extensions]

## License
This template is served under the MIT license.  
Read the [LICENSE] file for more info.