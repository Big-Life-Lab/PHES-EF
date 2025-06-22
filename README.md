# Public Health Environmental Surveillance Evaluation Framework (PHES-EF)

A website to support the transparent development and reporting of PHES-EF

This repository is a template to get started with creating the website using Quarto.

The website can be accessed at: https://big-life-lab.github.io/PHES-EF/

## Requirements to build the website

* [Quarto](https://quarto.org/)
* Tinytex by running the command `quarto install tinytex`
* If you're going to use R in your notebooks, follow [this](https://quarto.org/docs/computations/r.html) guide on Quarto
* If you're going to use Python in your notebooks, follow [this](https://quarto.org/docs/computations/python.html) guide

## Repository organization

* The `.github` folder contains [GitHub actions](https://github.com/features/actions) that automatically builds the website on every pull request (PR) and publishes the website on every push to master. For more information refer to the [continuous integration](#continuous-integration) section.
* The `qmd` folder should contain the .qmd files that will be rendered in your website. For every new qmd file added to the folder, make sure to add an entry to the `qmd/_quarto.yml` file. 

## Rendering the Website

The following commands can be used to build the documentation:

* When working on the documentation you can run the command `quarto preview ./qmd` in the terminal to get a live preview of your changes every time you make a change.
* For publishing, you can run the command `quarto render ./qmd`.

## Publishing the Website

This template uses [GitHub Pages](https://pages.github.com/) to host the Quarto website. 

You can use [these](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) instructions to enable GitGub pages for your repository. Make sure the publish branch is set to `gh-pages` and the folder is set to `/ (root)`. These [instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) go over how to do that.

**The gh-pages branch may not be available for selection until your website is published for the first time.**

## Continuous Integration

Continuous integration is done using GitHub actions. Currently, there are two actions:

1. PR merges trigger a rendering of the website which allows you to check if the changes in a branch has broken the build. **The website is not publicly published.**

2. Commits to the main/master branch triggers a new version of the website to be published.

### Setup

-   [build-docs-composite-action.yml](./.github/actions/build-docs-composite-action/action.yml) contains a reusable action to build the docs using quarto
-   [check-pr.yml](./.github/workflows/check-pr.yml) contains the action run when a PR is made and commits pushed to it
-   [publish-docs.yml](./.github/workflows/publish-docs.yml) contains the action run when a push is made to master. The documentation is published to github pages in this action.

test commit by haolan_2025_06_22