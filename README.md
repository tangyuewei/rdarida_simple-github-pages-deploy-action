![Dependencies](https://david-dm.org/rdarida/simple-github-pages-deploy-action.svg)

# Simple GitHub Pages Deploy Action
Deploys a given folder to gh-pages branch with git.

## Usage
```yml
name: Deploy to gh-pages

on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Install and build
        run: |
          npm install
          npm run build

      - name: Simple deploy with git
        uses: rdarida/simple-github-pages-deploy-action@v1.0.0
        with: # optional
          git-user: '<your GitHub username>'
          git-email: '<your email address>'
          git-base-folder: '<output folder of your build>'
          commit-message: '<your commit message>'
          branch: '<target branch for deployment>'
```

## Available Scripts

In the project directory, you can run:

### `postinstall`
Runs right after `npm install`, and sets up [husky](https://typicode.github.io/husky/#/)

### `format`
Runs Prettier and formats all the **\*.js**, **\*.json**, **\*.yml**, and **\*.yaml** files.

## What's inside?

A quick look at the top-level files and directories.

    .
    ├── .vscode/
    ├── node_modules/
    ├── .editorconfig
    ├── .gitignore
    ├── .prettierignore
    ├── .prettierrc
    ├── action.yml
    ├── LICENSE
    ├── package.json
    ├── package-lock.json
    └── README.md

1. **`.vscode/`**: This directory contains the project specific settings.json.

2. **`node_modules/`**: This directory contains all of the modules of the code that your project depends on (npm packages) are automatically installed.

3. **`.editorconfig`**: EditorConfig helps maintain consistent coding styles for multiple developers working on the same project across various editors and IDEs.

4. **`.gitignore`**: This file tells git which files should not track / not maintain a version history for.

5. **`.prettierignore`**: This is a configuration file for [Prettier](https://prettier.io/). It tells the prettier which files should not format.

6. **`.prettierrc`**: This is a configuration file for [Prettier](https://prettier.io/). Prettier is a tool to help keep the formatting of your code consistent.

7. **`action.yml`**: Contains the Simple GitHub Pages Deploy Action.

8. **`LICENSE`**: This template is licensed under the MIT license.

9. **`package-lock.json`** (See `package.json` below, first). This is an automatically generated file based on the exact versions of your npm dependencies that were installed for your project. **(You won’t change this file directly).**

10. **`package.json`**: A manifest file for Node.js projects, which includes things like metadata (the project’s name, author, etc). This manifest is how npm knows which packages to install for your project.

11. **`README.md`**: A text file containing useful reference information about your project.
