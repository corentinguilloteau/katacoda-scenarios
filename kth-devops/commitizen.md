Now that commit messages are verified automaticaly, it would be nice to have an easier way to write them to meet the
specifications. This is why we are going to use [commitizen](https://github.com/commitizen/cz-cli).

# Installation

First, install `commitizen`

`npm install --save-dev @commitlint/prompt commitizen`{{execute}}

In your `package.json`{{open}}, add the following configuration:

```
// package.json
"config": {
    "commitizen": {
      "path": "@commitlint/prompt"
    }
}
```

or run the following command `npx npe config.commitizen.path "@commitlint/prompt"`{{execute}}.

Then, add a new hook to husky to run `commitizen` when you want to commit

`npx husky add .husky/prepare-commit-msg "exec < /dev/tty && npx cz --hook || true"`{{execute}}

# Test it

You can now create a commit

`echo "test" > commitizen.md && git add commitizen.md && git commit`{{execute}}

You will be prompted with different choices to help you build a nice and clean commit message.
