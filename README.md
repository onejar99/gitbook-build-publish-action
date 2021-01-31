# GitHub Action for Gitbook Build and Publish

## Introduction

The GitHub Action is used to build GitBook static site files and deploy to GitHub Pages via gh-pages branch.

## How to Use

It's very easy to use it. Add a workflow like shown:

```yaml
name: Build and Publish My GitBook

on:
  workflow_dispatch:
  push:
    branches:
      - master

jobs:
  build-and-deploy:
    name: Build and deploy
    runs-on: ubuntu-latest
    env:
      MY_SECRET   : ${{secrets.GH_ACCESS_TOKEN}}
      USER_NAME   : <Your Git username>
      USER_EMAIL  : <Your Git email>
      BOOK_DIR    : your_book_sources_folder_name

    steps:
    - name: Checkout 🛎️
      uses: actions/checkout@v2.3.1

    - name: Build and Deploy 🚀
      uses: onejar99/gitbook-build-publish-action@v1.0.1
```
