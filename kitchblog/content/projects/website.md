+++
identifier = "website_proj"
disqus_title = "cmt_website" # cmt, shortened for "comment".
disqus_url = "https://kitchvx.github.io/projects/website/"
title = "Making a Site with Hugo."
date = "2023-03-21T17:56:28Z"
author = "Nathan"
authorTwitter = "Kitchvx" #do not include @
cover = ""
tags = ["Web Development"]
keywords = ["Website", "Hugo", "Web Development"]
description = "Going over the entire process on the development of my website, including installing Hugo and using Github Pages."
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
+++

# Overview

In this post, I am going to go through the process on how I got to this point in the website project. As I make this the website isn't 100% complete and this will be updated as the site is changed along the way. I created this website as a place to showcase all my projects and proud achivements that will hopefully get the attention of someone that will then use these posts to kickstart their career. Now time to get started!

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

The Windows installation isn't as simple as Linux's installation, who could've guessed? Firstly you will need to aquire the .zip file and make sure [git](https://en.wikipedia.org/wiki/Git) is installed, the download for git can be found [here](https://git-scm.com/download/win). If you have no way of unzipping the .zip file you can head to [winrar's](https://en.wikipedia.org/wiki/WinRAR) [website](https://www.win-rar.com/start.html?&L=0) to install it, free of charge. Now we can head to the [Hugo release](https://github.com/gohugoio/hugo/releases) page on github to install the latest version (at the time of writting it the latest version is v0.111.3). Once these have been aquired we can start. Extract the files from the zip file, I have placed my Hugo install into `C:\Hugo\bin`, and you will then want to open up the [Enviroment Variables](https://www.google.com/search?q=what+is+windows+environment+variables) Editor(?) you can find this by pressing `Win + R` and typing `SystemPropertiesAdvanced` in to the dialogue box you then want to find `Path` under User variables for your user, press edit

{{< image src="/images/envtable1.png" alt="Screenshot 1" position="center" style="border-radius: 8px;" >}}

and add your Hugo binaries to it (this will be the location you have the `Hugo.exe` in).

{{< image src="/images/envtable2.png" alt="Screenshot 2" position="center" style="border-radius: 8px;" >}}

Once this is done we can start using Hugo.

My current setup for this is using the terminal to setup a new Hugo site and commit any changes made to Github while using [Visual Studio Code](https://en.wikipedia.org/wiki/Visual_Studio_Code) to edit text/code. Alternatively you can use VS Code to commit changes to Github by installing the [Github Pull](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github) extenstion.

# Using Hugo


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