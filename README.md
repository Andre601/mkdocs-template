[use]: https://github.com/Andre601/mkdocs-template/generate

[MkDocs]: https://www.mkdocs.org/

[squidfunk]: https://github.com/squidfunk
[MkDocs Material Theme]: https://github.com/squidfunk/mkdocs-material

[facelessuser]: https://github.com/facelessuser
[PyMdown Extensions]: https://github.com/facelessuser/pymdown-extensions/

[Netlify]: https://netlify.com

[mkdocs.yml]: https://github.com/Andre601/mkdocs-template/blob/master/mkdocs.yml
[docs folder]: https://github.com/Andre601/mkdocs-template/blob/master/docs
[workflow]: https://github.com/Andre601/mkdocs-template/blob/master/.github/workflows/deploy.yml

[LICENSE]: https://github.com/Andre601/mkdocs-template/blob/master/LICENSE

[gh-pages]: https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

# MkDocs Material Template
This is a template repository for anyone that wants to use the MkDocs Material Theme.

## Getting Started
To get started, first clone this template by clicking on the Green button labeled [`Use this template`][use].  
On the new screen, give your repository a name and make sure to check `Include all branches`. This will make sure that the `gh-pages` branch is included, or otherwhise publishing the docs to GitHub Pages could cause errors (See [Troubleshooting](#troubleshooting)).

> **Note**  
> GitHub changed how you define from where it takes the pages to build. You are now able to define both a branch and a specific folder from where GitHub would take the files to then deploy them on GitHub Pages.  
> You can read more about this [here][gh-pages].

### Creating pages
To create new pages, just add new markdown files to the [docs folder] of the repository and edit them.  
MkDocs will then turn those into static HTML pages once you [build](#build-pages) or [deploy](#deploy-to-github) the pages.

The template also has some pre-made settings for your convenience to help you with creating documentation much easier.  
In the [mkdocs.yml] will you find many settings that you can alter. Please check the comments and the links they have for more info.

It also contains some extensions that might be useful including:

- Admonition
- CodeHilite
- ToC
- [PyMdown Extensions]

You're free to add, edit or remove any extension at your own discretion, but keep in mind that some expansions might cause compatibility issues with others or require to be downloaded first.  
For that, alter the `requirements.txt` if you also deploy pages using GitHub Actions or [Netlify](#netlify)

## Build Pages
To build pages (locally) can you use the `mkdocs build` command in your prefered command prompt.  
Note that for the successful execution of this command you have to...

- ...be in the folder that contains the `mkdocs.yml`
- ...have Python 3.7 installed
- ...have MkDocs and all required dependencies such as Material for MkDocs installed.  
Note that Material for MkDocs automatically downloads MkDocs and also certain extensions such as the [PyMdown Extensions].

MkDocs would now build the HTML in the defined configuration folder for you to use.

## Deploy to GitHub
If you want to publish the pages on GitHub Pages can you use the [premade workflow][workflow] for this.  
This workflow will setup Python, download Material for MkDocs and all its dependencies and deploy the pages to the `gh-pages` branch to then be viewable under `<username>.github.io/<repository>` (unless you defined a specific CNAME through a CNAME file in the [docs folder]).

Note that in order for this to work will you need to have a `gh-pages` branch already made.

## Netlify
Netlify is an amazing service to build and deploy pages. This template comes with a `runtime.txt` which is used by Netlify to determine the Python version used (They use an old version of Python... Don't ask why).

For more information, please check out their website.

## Dependabot
The repository contains a `dependabot.yml` file inside the `.github` folder which allows automatic updates through GitHub's Dependabot.  
It is configured to target both Python dependencies (inside the `requirements.txt`) and GitHub Actions dependencies, to make sure bot are updated accordingly.

Note that it is configured by default to add the `Type: Update (Dependency)` label and also the `Target: Python (pip)` label for Python and `Target: GitHub Actions` label for GitHub Actions Dependencies.  
Those labels don't exist by default so you have to either create them, or alter the ones in the dependabot.yml (You can also just remove the `labels` sections).

## Troubleshooting
> **The deploy action gives me an error when deploying. What is the issue?**

There can be many issues but the most common ones are that you either don't have a `gh-pages` branch set or that the `requirements.txt` file is missing or its content is invalid.

> **Can I alter the overall style of the pages?**

Yes. Material for MkDocs supports Theme extensions, meaning you can override specific parts of a theme by providing the particular file in a folder and defining this folder as the `custom_dir` one in the [mkdocs.yml].  
This template ships with a `theme` folder that can be used for that and you can just uncomment the aforementioned line in the YAML file.


## Credits
A big thank you goes to the following people/groups:

- [MkDocs] for providing the software, to generate documentation.
- [squidfunk] for the [MkDocs Material Theme].
- [facelessuser] for the [PyMdown Extensions].

## License
This template is served under the MIT license.  
Read the [LICENSE] file for more info.
