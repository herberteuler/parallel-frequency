# hnop - A minimal Haskell project structure

This is based on [the minimal Haskell project][semantichnop],
but with default values that I think I'll use for most of my Haskell play projects.

Some of the defaults I'm interested in are:

 * GHC compiler warnings: enabled and fatal
 * cabal packages that [play nice with each other][stackage]
 * Some compiler optimisations, e.g. use a threaded runtime

If by some off chance anybody other than myself comes across this and finds it useful:
feel free to fork it and customise it to your own liking.

I don't play with Haskell often enough to know of all the latest best practices,
so if you think I missed something that should be enabled by default, please let me know :-)

## How to use this as a base for your new project

##### 1. Fork/clone this repo, but use the name of the new project

```bash
$ git clone git@github.com:apauley/hnop.git my-new-project
```

##### 2. Create _my-new-project_ in GitHub

But don't let GitHub initialise it with any files such as a README, LICENSE or .gitignore

##### 3. Change the git origin to the new project

```bash
$ cd my-new-project/
$ git remote rm origin
$ git remote add origin git@github.com:apauley/my-new-project.git
```

##### 4. Customise and rename hnop references

```bash
$ git mv hnop.cabal my-new-project.cabal
```

 * Modify my-new-project.cabal
 * Modify README.md
 * Find and change any mentions of hnop that you may have missed:

```bash
$ git grep -i hnop
```

##### 5. Push and track the new upstream master

```bash
$ git commit -a -m 'Customised initial config'
$ git push -u origin master
```

## Building

Needed only once after cloning the repo:

```bash
$ cabal sandbox init
$ cabal update
```

Compile and install after each code change:

```bash
$ cabal install -j
```

## Running the command-line executable

The binary is placed in this repository checkout under *.cabal-sandbox/bin/hnop*

```
$ .cabal-sandbox/bin/hnop
```

[semantichnop]: http://semantic.org/hnop/
[stackage]: https://www.stackage.org/
