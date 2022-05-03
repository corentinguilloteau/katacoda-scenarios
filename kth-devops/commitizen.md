You now have a way to verify your commit messages. But for now, it is not very convenient to use.

You will now setup a toolchain to include the linting directly in your `git commit` workflow, and for this, you are
going to use [husky](https://github.com/typicode/husky).

# Installation

First, install the husky package:

`npm install husky --save-dev`{{execute}}

Next, update your `package.json`{{open}} file to setup husky on prepare

`npm set-script prepare "husky install"`{{execute}}

You can now setup husky

`npm run prepare`{{execute}}

# Create a hook

Now create a husky hook. It is a script that will run each time you will run `git commit`:

`echo '#!/bin/sh . "\$(dirname "\$0")/\_/husky.sh" npx --no --commitlint --edit "\${1}' > .husky/commitlint"`{{execute}}
