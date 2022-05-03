**Congratulations**, you can now write beautiful commit messages.

In this last part, we are going to see how you can use your new favorite tool to also generate nice changelogs and
automate your version numbers.

To do so, you can use [standard-version](https://github.com/conventional-changelog/standard-version).

This tool will generate a changelog based on your commits. It then retrieve the current version of your project and,
depending on the nature of your commits, it will automaticaly bump its version, following
[semantic versioning](https://semver.org/) rules. It is a really good way to add state-of-the-art versioning to your
project!

**NOTE**: By default, `standard-version` is configured for NodeJS projects (i.e using a `package.json` file).
Nevertheless, it is still possible to use any other file to save the version of your software. Please refer to
[this](https://github.com/conventional-changelog/standard-version#can-i-use-standard-version-for-additional-metadata-files-languages-or-version-files)
link to know more about it.

# Installation

First, install the related package

`npm i --save-dev standard-version`{{execute}}

Then, add a new npm command to create a new release

``npm set-script release "HUSKY=0 standard-version"` or `npx npe scripts.release "HUSKY=0 standard-version"`{{execute}}

The `HUSKY=0` environnement variable is used to prevent triggering the previously defined hooks.

# Usage

You can now create as many commits as you want. Once you are ready to deploy a new version, just run

`npm run release`{{execute}}

Your changelog is automaticaly generated in the `CHANGELOG.md`{{open}}, the version of your `package.json`{{open}} file
is bumped and a new git commit and tag is generated.
