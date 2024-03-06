---
title: "Personal website with Hugo: Maintainance and Enhancements"
date: 2024-03-06T10:31:21+01:00
draft: false
tags: ["hugo", "website"]
---

Hi there! 😊

If you would like to create from scratch a personal website with Hugo, you can follow the steps described in the post [How to create a personal website with Hugo](../posts/how-to-create-a-personal-website-with-hugo.md).

### General maintainance

#### Theme update (or change)
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

#### Create a new post
```sh
hugo new posts/<your-post-name>.md
```
Where `<your-post-name>` is the title of your new post. Remember the extension `.md`.

#### Create a new section
The command below creates a new section.
```sh
hugo new <your-section-name>/_index.md
```
Where `<your-section-name>` is the title of your new section. Remember the extension `_index.md`.

### Enhancements
#### How to embed videos in Hugo pages
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

#### Allow comments in your website
In Hugo website there is a little guide to [add Disqus](https://gohugo.io/content-management/comments/).

You would need to sign up on Disqus website, following some instructions.

Create a file in `./layout/partial/comments.html` with a content similar to the one below, that Disqus will provide you through the sign up process.

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
