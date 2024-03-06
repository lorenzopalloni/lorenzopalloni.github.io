---
title: "How to create a personal website with Hugo"
date: 2022-04-25T16:41:49+02:00
draft: true
tags: ["hugo", "website"]
---

Hi there! 😊

If you like this website, maybe you would like to have a similar page for yourself too. In this post, I'm going to describe the major steps involved.

### Let's start!

#### 1. Install Hugo
This website has been built using a static site generator called [Hugo](https://gohugo.io/). So, the very first thing to do would be to [install Hugo](https://gohugo.io/getting-started/installing).

In my case ([Arch Linux](../posts/how-to-install-arch-linux.md)), I would run the following:
```sh
pacman -S hugo
```

For Debian-based systems (such as Ubuntu), you would run:
```sh
sudo snap install hugo --channel=extended
```

#### 2. Create a new website
The following command creates a new site, that is basically a folder called \<your-site-name\> that contains the essential elements of a Hugo website.
```sh
hugo new site <your-site-name> --format yml
```

#### 3. Choose a theme
This website use [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, but you can choose whichever you like from this [list of Hugo themes](https://themes.gohugo.io/).

Amend and launch the following command following your previous choices.
```sh
cd <your-site-name>
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

#### 4. Add some content
To add content to your website, you can create a new post or a new section.

The command below creates a new post.
```sh
hugo new posts/<your-post-name>.md
```

The command below creates a new section.
```sh
hugo new <your-section-name>/_index.md
```

To help you understand the difference between a post and a section, I will show you a snapshot of the folder structure of this website.

```sh
.
├── config.yml  # core file for customization
├── content  # root for all the content
│   ├── bio  # section
│   │   └── _index.md  # makes the section a `single` page
│   ├── _index.md  # to rename the section name
│   └── posts  # another section, this has been left as a `list` page (the default)
│       ├── how-to-install-arch-linux.md  # a post, that is a `single` page
│       ├── how-to-create-a-personal-website-with-hugo.md  # another post
│       ├── _index.md  # to rename the section name
│       └── routine.md  # again, another post
├── layouts  # this section overraids the ./themes/PaperMod/layouts/ settings
│   ├── _default
│   │   └── single.html
│   ├── partials
│   │   └── comments.html
│   └── shortcodes
│       └── video.html  # the content allows to embed videos in posts
└── static  # contains files that can be embedded by your pages
    ├── homer-arch.mp4
    ├── LorenzoPalloniCV.pdf
    └── me_thinking_cropped.jpeg
```

#### 5. Start the Hugo server
```sh
hugo server -D
```
This command will start a live server to check changes while developing. The `-D` flag allows to build drafts. It would be helpful to check the changes in the website while you are developing it.

#### 6. Site Configuration
The `config.yml` file is the core file for customization. It is theme-specific and contains the basic settings for your website. You can have a look at [`config.yml`](../../config.yml) file for this website to have an idea of the settings you can change for the PaperMod theme.

#### 7. Let GitHub to host your website
⚠️ ATTENTION ⚠️: Follow the instructions described [here (First Deployment with `GITHUB_TOKEN`)](https://github.com/peaceiris/actions-gh-pages#%EF%B8%8F-first-deployment-with-github_token).

Follow the instructions described [here](https://pages.github.com/).
Pull your new repository.
```sh
git clone git@github.com:lorenzopalloni/lorenzopalloni.github.io.git
```
```sh
cp -r ./<your-site-name>/* -t lorenzopalloni.github.io
cd lorenzopalloni.github.io
mkdir -p .github/workflows/
touch .github/workflows/gh-pages.yml
```

In `.github/workflows/gh-pages.yml` copy the following:

```yml
name: GitHub Pages

on:
  push:
    branches:
      - main  # Set a branch to deploy
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-20.04
    concurrency:
      group: ${{ github.workflow }}-${{ github.ref }}
    steps:
      - uses: actions/checkout@v3
        with:
          submodules: true  # Fetch Hugo themes (true OR recursive)
          fetch-depth: 0    # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: '0.91.2'
          # extended: true

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: ${{ github.ref == 'refs/heads/main' }}
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

### 8. Compile your new website
To compile your new website, you would need to run the following command.
```sh
hugo
```

#### 9. Deploy your new website
To deploy your new website, you would need to push your changes to GitHub.
```sh
git add .
git commit -m "Initial commit"
git push
```
If you have followed all the steps, you should be able to see your new website at `https://<your-github-username>.github.io`.

#### 10. Enjoy your new website 🎉
If you would like to add some features to your website, such as allowing comments of your posts, embedding videos, and more, you can check out another post I wrote about [Personal Website With Hugo Maintainance And Enhancements](../posts/how-to-create-a-personal-website-with-hugo-maintanance-and-enhancements.md).

I hope you have found this post useful somehow.

In case you have any questions or comments, please write them below, I'll be happy to discuss with you. In the meanwhile, have a beautiful day! 😊
