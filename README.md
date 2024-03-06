#### Lorenzo Palloni's personal website
[https://lorenzopalloni.github.io](https://lorenzopalloni.github.io)

## Development
Live server to check changes while developing:
```sh
hugo server --buildDrafts
```

## Theme update (or change)
When you reclone the repo you may need to run the following command.
Check if `./theme/<theme-name>/` is an empty folder.
```sh
git submodule update --init --recursive
```

Update the theme (git submodule).
```sh
git submodule update --remote --merge
```

To find a new theme, you can check [https://themes.gohugo.io/](https://themes.gohugo.io/). Then you can add it to this repo as a git submodule, for example:
```sh
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```
Read more about git submodules [here](https://www.atlassian.com/git/tutorials/git-submodule).
