# Sphinx Static Site Generator

## Table of Contents

- [Sphinx Static Site Generator](#sphinx-static-site-generator)
  - [Table of Contents](#table-of-contents)
  - [About](#about)
  - [Installing the Remote Container](#installing-the-remote-container)
  - [Using this Remote Container](#using-this-remote-container)

## About

This is the Sphinx Static Site Generator. It can create web pages using RestructuredText and Markdown.

The configured Sphinx theme for this development containeris the [Alabaster theme](https://alabaster.readthedocs.io/en/latest/).

This development container is configured to push pages to a desired GitHub Page branch using Travis CI. You can learn more about GitHub Pages [here](https://pages.github.com/) and Travis CI [here](https://travis-ci.org/).

Documentation for Sphinx can be found [here](https://www.sphinx-doc.org/en/master/).

## Installing the Remote Container

0. Install [Docker](https://www.docker.com/).
1. Download the branch as a zip file.
2. Extract the contents to a project directory.
3. Install the [Remote Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension from the VSCode marketplace.
4. When prompted, open the Remote Container or [read the docs](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers#getting-started).

## Using this Remote Container

After opening the development container, you can start by editing the `source/index.rst file` and the `conf.py` file.
