# Linting your commit

Once you've learned what conventional commits, you will want a way to make sure your commit messages are well formated.

For this purprose, we are gonna use [commitlint](https://github.com/conventional-changelog/commitlint).

## Installation

First, install the `commitlint` package:

`npm install --save-dev @commitlint/cli`{{execute}}

## Commit convention

Next, we want to specify the commit convetion we want to use. Many conventions exists but we are going to use the
classic conventional commits one.

Install this specific convention

`npm install --save-dev @commitlint/config-conventional`{{execute}}

And then, create a `commitlint.config.js` file to tell `commitlint` to use this convention.

`echo "module.exports = {extends: ['@commitlint/config-conventional']};" > commitlint.config.js`{{execute}}

**NOTE:** You can obviously customize this convention to better match your workflow and your project, for example by
specifiying new scopes. For this, use the following [rules](https://commitlint.js.org/#/reference-rules).

## Lint your commit message

You can now try to lint your commit message using the following command:

`echo "<your_commit_message>" | npx commitlint`

For example, `feat: implemented new feature` is a valid commit:

`echo "feat: implemented new feature" | npx commitlint`{{execute}}

On the other hand `sdfsdf` is NOT a valid commit:

`echo "sdfsdf" | npx commitlint`{{execute}}
