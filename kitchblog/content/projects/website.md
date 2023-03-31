+++
identifier = "website_proj"
disqus_title = "cmt_website" # cmt, shortened for "comment".
disqus_url = "https://kitchvx.github.io/projects/website/"
title = "Making a Site with Hugo."
date = "2023-03-21T17:56:28Z"
author = "Nathan"
authorTwitter = "Kitchvx" #do not include @
cover = "/projects/webproj_cover.png"
tags = ["Web Development"]
keywords = ["Website", "Hugo", "Web Development"]
description = "Going over the entire process on the development of my website, including installing Hugo and using Github Pages."
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
+++

# Overview

In this post, I am going to go through the process on how I got to this point in the website project. I will be going over this post in a guide fashion, so it will be treat as such. As I make this the website isn't 100% complete and this will be updated as the site is changed along the way. I created this website as a place to showcase all my projects and proud achievements that will hopefully get the attention of someone that will then use these posts to kickstart their careers or help someone develop a passion. Now time to get started!

# Prerequisites

Firstly, the website is built upon the [Hugo](https://gohugo.io) framework, before we can get started we need to install Hugo.

- Installing Hugo:

Hugo is supported on [macOS](https://en.wikipedia.org/wiki/MacOS), [Windows](https://en.wikipedia.org/wiki/Windows_10), [Linux](https://en.wikipedia.org/wiki/Linux) and [BSD](https://en.wikipedia.org/wiki/Berkeley_Software_Distribution). I have been using Windows 10 for the development and deployment at this current stage (22/03/23), I have yet to start using Hugo on [Arch Linux](https://wiki.archlinux.org/title/Arch_Linux) which is my perfered distribution. The Linux installation is relatively simple.

- Linux Installation:

Depending on your distro of choice it will be as simple as typing a few commands for your [package manager](https://itsfoss.com/package-manager/), Hugo's documentation goes over this [here](https://gohugo.io/installation/linux/).

For me because I use Arch I will use [pacman](https://wiki.archlinux.org/title/pacman).

1. Update the repositories.

```html
sudo pacman -Syu
```
2. Install Hugo.
```html
sudo pacman -S hugo
```

After Hugo has been installed, make sure you have [git](https://en.wikipedia.org/wiki/Git) as we will be using this too but this should already be installed.

3. Install git.
```html
sudo pacman -S git
```

- Windows Installation:

The Windows installation isn't as simple as Linux's installation, who could've guessed? Firstly you will need to acquire the .zip file and make sure [git](https://en.wikipedia.org/wiki/Git) is installed, the download for git can be found [here](https://git-scm.com/download/win). If you have no way of unzipping the .zip file you can head to [winrar's](https://en.wikipedia.org/wiki/WinRAR) [website](https://www.win-rar.com/start.html?&L=0) to install it, free of charge. Now we can head to the [Hugo release](https://github.com/gohugoio/hugo/releases) page on github to install the latest version (at the time of writting it the latest version is v0.111.3). Once these have been acquired we can start. Extract the files from the zip file, I have placed my Hugo install into `C:\Hugo\bin`, and you will then want to open up the [Environment Variables](https://www.google.com/search?q=what+is+windows+environment+variables) Editor(?) you can find this by pressing `Win + R` and typing `SystemPropertiesAdvanced` in to the dialogue box you then want to find `Path` under User variables for your user, press edit

{{< image src="/images/envtable1.png" alt="Screenshot 1" position="center" style="border-radius: 8px;" >}}

and add your Hugo binaries to it (this will be the location you have the `Hugo.exe` in).

{{< image src="/images/envtable2.png" alt="Screenshot 2" position="center" style="border-radius: 8px;" >}}

Once this is done we can start using Hugo.

My current setup for this is using the terminal to setup a new Hugo site and commit any changes made to Github while using [Visual Studio Code](https://en.wikipedia.org/wiki/Visual_Studio_Code) to edit text/code. Alternatively you can use VS Code to commit changes to Github by installing the [Github Pull](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) extenstion.

# Using Hugo

First things first, you will want to create a github repo and name it something relevent like, for example, "kitch-blog". Mine is just called "hugo", add a license if you feel the need to. Then we need to create the submodule repository, you will want to name this your username followed by "github.io", mine for example is "kitchvx.github.io". Now getting the theme is as simple as going to [themes.gohugo.io](https://themes.gohugo.io). The theme I used is called [terminal](https://themes.gohugo.io/themes/hugo-theme-terminal/). before we clone the theme or start using hugo we need to clone the first repository and to do this you use the following command in your terminal:

```html
git clone https://github.com/YOUR_NAME/YOUR_REPO.git
```

Cd inside the repository using `cd` command and use the `hugo new site` command to generate a static website, you have to name it, I went with `hugo new site kitchblog` and it will generate a site inside a new folder within the repository, cd into it and clone the theme:

```html
git clone https://github.com/panr/hugo-theme-terminal.git themes/terminal
```

Before creating the submodule we need to setup the config and make sure everything is working, for the terminal theme the config should be on the[hugo themes](https://themes.gohugo.io/themes/hugo-theme-terminal/) page but if you don't want to take the small detour, I will embed the code.

{{< code language="toml" title="Terminal Theme Configs" id="1" expand="Show" collapse="Hide" isCollapsed="true" >}}
baseurl = "/" # Set this to your website url.
languageCode = "en-us"
theme = "terminal"
paginate = 5

[params]
  # dir name of your main content (default is `content/posts`).
  # the list of set content will show up on your index page (baseurl).
  contentTypeName = "posts"

  # ["orange", "blue", "red", "green", "pink"]
  themeColor = "orange"

  # if you set this to 0, only submenu trigger will be visible
  showMenuItems = 2

  # show selector to switch language
  showLanguageSelector = false

  # set theme to full screen width
  fullWidthTheme = false

  # center theme with default width
  centerTheme = false

  # if your resource directory contains an image called `cover.(jpg|png|webp)`,
  # then the file will be used as a cover automatically.
  # With this option you don't have to put the `cover` param in a front-matter.
  autoCover = true

  # set post to show the last updated
  # If you use git, you can set `enableGitInfo` to `true` and then post will automatically get the last updated
  showLastUpdated = false

  # set a custom favicon (default is a `themeColor` square)
  # favicon = "favicon.ico"

  # Provide a string as a prefix for the last update date. By default, it looks like this: 2020-xx-xx [Updated: 2020-xx-xx] :: Author
  # updatedDatePrefix = "Updated"

  # set all headings to their default size (depending on browser settings)
  # oneHeadingSize = true # default

  # whether to show a page's estimated reading time
  # readingTime = false # default

  # whether to show a table of contents
  # can be overridden in a page's front-matter
  # Toc = false # default

  # set title for the table of contents
  # can be overridden in a page's front-matter
  # TocTitle = "Table of Contents" # default


[params.twitter]
  # set Twitter handles for Twitter cards
  # see https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started#card-and-content-attribution
  # do not include @
  creator = ""
  site = ""

[languages]
  [languages.en]
    languageName = "English"
    title = "Terminal"
    subtitle = "A simple, retro theme for Hugo"
    owner = ""
    keywords = ""
    copyright = ""
    menuMore = "Show more"
    readMore = "Read more"
    readOtherPosts = "Read other posts"
    newerPosts = "Newer posts"
    olderPosts = "Older posts"
    missingContentMessage = "Page not found..."
    missingBackButtonLabel = "Back to home page"

    [languages.en.params.logo]
      logoText = "Terminal" # Enter your blog name here, mine is "Nathan's Blog".
      logoHomeLink = "/"

    [languages.en.menu]
      [[languages.en.menu.main]]
        identifier = "about"
        name = "About"
        url = "/about"
      [[languages.en.menu.main]]
        identifier = "showcase"
        name = "Showcase"
        url = "/showcase"

[module]
  # In case you would like to make changes to the theme and keep it locally in you repository,
  # uncomment the line below (and correct the local path if necessary).
  # --
  # replacements = "github.com/panr/hugo-theme-terminal -> themes/terminal"
[[module.imports]]
  path = 'github.com/panr/hugo-theme-terminal'
{{< /code >}}

If you are unsure what to do, you can mess around with the configs and check out what everything does. Before seeing the changes you will need to open a terminal and run:

```html
hugo serve -t terminal
``` 
Or you can run it with:

```html
hugo serve --disableFastRender --ignoreCache -t terminal
```

The flag `--disbaleFastRender`  enables full re-renders on changes and the flag `--ignoreCache` ignores the cache directory for faster rebuilding times on local previews when saving changes. Now these times aren't significant but when developing on lower end machines it may help.

Without `--disableFastRender` and `--ignoreCache`:

{{< image src="/images/example1-render-times.png" alt="Example 1" position="left" style="border-radius: 8px;" >}}

With `--disableFastRender` and `--ignoreCache`:

{{< image src="/images/example2-render-times.png" alt="Example 2" position="left" style="border-radius: 8px;" >}}

# Comments
<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    var disqus_config = function () {
    this.page.url = disqus_url;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = identifier; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://kblog-5.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>