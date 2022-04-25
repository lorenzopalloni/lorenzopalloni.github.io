---
title: "How to Replicate This Website"
date: 2022-04-25T16:41:49+02:00
draft: true
---

Hi there! 😊

If you like this website, maybe you would like to have a similar page for yourself too. In this post, I'm going to describe the major steps involved.

### Let's start!

#### 1. Install Hugo
This website has been built using a static site generator called [Hugo](https://gohugo.io/). So, the very first thing to do would be to [install Hugo](https://gohugo.io/getting-started/installing).

In my case (Arch Linux), I would run the following:
```zsh
pacman -S hugo
```

#### 2. Create a new site
The following command creates a new site, that is basically a folder called \<your-site-name\> that contains the essential elements of a Hugo website.
```zsh
hugo new site <your-site-name> --format yml
```

#### 3. Choose a theme
This website use [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, but you can choose whichever you like from this [list of Hugo themes](https://themes.gohugo.io/).

Amend and launch the following command following your previous choices.
```zsh
cd <your-site-name>
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```


#### 4. Add some content

```zsh
.
├── config.yml  # core file for customization
├── content  # root for all the content
│   ├── bio  # section
│   │   └── _index.md  # makes the section a `single` page
│   ├── _index.md  # to rename the section name
│   └── posts  # another section, this has been left as a `list` page (the default)
│       ├── how-to-install-arch-linux.md  # a post, that is a `single` page
│       ├── how-to-replicate-this-website.md  # another post
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
```zsh
hugo server -D
```

#### 6. Site Configuration

```yml
baseURL: "https://lorenzopalloni.github.io"
languageCode: en-us
title: Lorenzo Palloni
theme: "PaperMod"

enableEmoji: true
pygmentsUseClasses: true  # ?

minify:
    disableXML: true
    minifyOutput: true  # ?

params:
    author: Lorenzo Palloni
    description: "Lorenzo Palloni's personal website."
    env: production  # to enable google analytics, opengraph, twitter-cards and schema.

    defaultTheme: auto
    ShowShareButtons: true  # bottom share buttons in single posts
    ShareButtons: false
    ShowReadingTime: true
    ShowCodeCopyButtons: true
    comments: true
    # images: ["me_thinking.jpeg"]  # ?
    # enableInlineShortcodes: true
    # ShowToc: true
    # disableThemeToggle: true
    # disableSpecial1stPost: true
    # displayFullLangName: true
    # ShowPostNavLinks: true
    # ShowBreadCrumbs: true

    profileMode:
        enabled: true
        title: Lorenzo Palloni
        subtitle: >
            Data Scientist
        # imageUrl: "me_thinking_cropped.jpeg"
        # imageTitle: Me thinking
        # imageWidth: 150
        # imageHeight: 150
        buttons:
            # - name: Bio
            #   url: bio/
            #   weight: 1
            # - name: Works
            #   url: works/
            #   weight: 2
            # - name: Posts
            #   url: posts/
            #   weight: 3

    socialIcons:
        - name: github
          url: "https://github.com/lorenzopalloni"
        - name: linkedin
          url: "https://www.linkedin.com/in/lorenzo-palloni-758b76145"

    # homeInfoParams:
    #     Title: "Lorenzo Palloni"
    #     Content: >
    #         Welcome to my website! 😊


#     editPost:
#         URL: "https://github.com/adityatelange/hugo-PaperMod/tree/exampleSite/content"
#         Text: "Suggest Changes" # edit text
#         appendFilePath: true # to append file path to Edit link

    # label:
    #     text: "Home"
    #     icon: icon.png
    #     iconHeight: 35

    # analytics:
    #     google:
    #         SiteVerificationTag: "XYZabc"

    # assets:
    #     favicon: "<link / abs url>"
    #     favicon16x16: "<link / abs url>"
    #     favicon32x32: "<link / abs url>"
    #     apple_touch_icon: "<link / abs url>"
    #     safari_pinned_tab: "<link / abs url>"

    # cover:
    #     hidden: true # hide everywhere but not in structured data
    #     hiddenInList: true # hide on list pages and home
    #     hiddenInSingle: true # hide on single page

    # fuseOpts:
    #     isCaseSensitive: false
    #     shouldSort: true
    #     location: 0
    #     distance: 1000
    #     threshold: 0.4
    #     minMatchCharLength: 0
    #     keys: ["title", "permalink", "summary", "content"]

# taxonomies:
#     category: categories
#     tag: tags
#     series: series

# markup:
#     goldmark:
#         renderer:
#             unsafe: true
#     highlight:
#         # anchorLineNos: true
#         codeFences: true
#         guessSyntax: true
#         lineNos: true
#         # noClasses: false
#         style: monokai

# privacy:
#     vimeo:
#         disabled: false
#         simple: true
#
#     twitter:
#         disabled: false
#         enableDNT: true
#         simple: true
#
#     instagram:
#         disabled: false
#         simple: true
#
#     youtube:
#         disabled: false
#         privacyEnhanced: true
#
# services:
#     instagram:
#         disableInlineCSS: true
#     twitter:
#         disableInlineCSS: true

menu:
    main:
        - name: Bio
          url: bio/
          weight: 1
        # - name: Works
        #   url: works/
        #   weight: 2
        - name: Posts
          url: posts/
          weight: 3
        - name: Rèsumè
          url: "LorenzoPalloniCV.pdf"
          weight: 4
```

ATTENTION here: Follow the instructions described [here](https://github.com/peaceiris/actions-gh-pages#%EF%B8%8F-first-deployment-with-github_token).

#### 7. Add a comment section
In Hugo website there is a little guide to [add Disqus](https://gohugo.io/content-management/comments/).

You would need to sign up on Disqus website, following some instructions.

Create a file in `./layour/partial/comments.html` with a content similar to the one below, that Disqus will provide you through the sign up process.

```html
<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    /*
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    */
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://lorenzopalloni.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
```

#### 8. Let GitHub to host your website
Follow the instructions described [here](https://pages.github.com/).
Pull your new repository.
```zsh
git clone git@github.com:lorenzopalloni/lorenzopalloni.github.io.git
```
```zsh
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

#### 9. How to embed videos in Hugo pages

Add the following in `./layout/shortcodes/video.html`:
```html
<video class="video-shortcode" preload="{{ .Get "preload" }}" width="{{ .Get "width"}}" autoplay="{{ .Get "autoplay"}}" loop="{{ .Get "loop" }}" muted="{{ .Get "muted" }}" controls>
    <source src="{{ .Get "src" }}" type="{{ .Get "type" }}" >
    There should have been a video here but your browser does not seem
    to support it.
</video>
```
Now you can add this line directly in your post, it will detect any video in the `./static` folder.

> {{\< video src="/homer-arch.mp4" type="video/mp4" preload="auto" width=360 \>}}

#### 10. Launch your new website
```zsh
hugo
```

### Bye, bye! 👋

I hope you have found this post useful somehow. In case you have any questions or comments, please write them below, I'll be happy to discuss with you. In the meanwhile, have a beautiful day! 😊

