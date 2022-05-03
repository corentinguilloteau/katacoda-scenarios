You now have a way to verify your commit messages. But for now, it is not very convenient to use.

You will now setup a toolchain to include the linting directly in your `git commit` workflow, and for this, you are
going to use [husky](https://github.com/typicode/husky).

# Installation

First, install the husky package:

`npm install husky --save-dev`{{execute}}

Next, update your `package.json`{{open}} file to setup husky on prepare

`npm set-script prepare "husky install"` or `npx npe scripts.prepare "husky install"`{{execute}}

You can now setup husky

`npm run prepare`{{execute}}

# Create a hook

Now create a husky hook. It is a script that will run each time you will run `git commit`:

`npx husky add .husky/pre-commit 'npx commitlint --edit $1'`{{execute}}

This script will run `commitlint` on your commit message each time you make a new commit, and will let you actually
create the commit only if the message is valid.

# Create a commit

You can now create a commit. You will see that your commit has to meet the conventional commits specifications to be
accepted.

This commit is a valid commit:

`touch readme.md & git add readme.md & git commit -m "chore: added readme"`{{execute}}

And this commit is not:

`touch readme.md & git add readme.md & git commit -m "added readme"`{{execute}}
