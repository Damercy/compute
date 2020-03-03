---
layout: post
title: "How to install Jekyll on Windows"
date: 2020-01-31 20:25:00 +0530
permalink: /:title
---
Jekyll is a lightweight, high performance, blog-ready tool that is highly useful to convert markdown files (and others) into static websites.

I am really liking Jekyll due to it's simple design & customizability. I write my blogs in markdown in my editor and push it to my repo. That's all! No more waiting for your site to load and no more waiting for getting your posts to load.

I can write so much about Jekyll, but I think the official docs and jekyll website has done a better explanation about it than me. You can refer more about Jekyll [here][to-jekyll-site].

## Installing Jekyll on Windows
If you're done getting excited about Jekyll, let's get into installing it so that you can write cool stuff and post it for free on the internet!

#### Prerequisites
1. Ruby version 2.4.0+
2. RubyGems
3. GCC and Make

As a windows user, we needn't worry about installing the above packages manually (although we can do so too).

The easiest way to install Jekyll is using RubyInstaller for Windows.

Install `Ruby+DevKit 2.6.X (x64)` from the [RubyInstaller website.][to-rubyinstaller-site]  

After downloading the above file, follow the setup and install the software. Here's a `crucial step` that needs to be followed:-  
- Before finishing the installation, during the last step of the installation wizard, check the box that enables the option `ridk install`. This installs the essential native files required to run Jekyll on Windows.  

- After you click on finish, another window (prompt) opens. This is,as I like to call it, the `ridk install window`. Just hit ***ENTER*** to install all the dependencies.  

- Finally, after the installation completes, restart your computer (if needed) and then open a new command prompt (or bash if you've got WSL) and type the following command to download and install Jekyll: `gem install jekyll bundler`  

Finally, check if Jekyll has been properly installed by checking it's version by typing `jekyll -v` on the command prompt.

## TL;DR
- Install `Ruby+DevKit 2.6.X (x64)`.
- Check the option `ridk install` during last step of installation wizard. Hit **ENTER** to install everything.
- On command prompt, type: `gem install jekyll bundler`.
- Check your installation skills by typing: `jekyll -v` on the command prompt.



And that's how you install Jekyll on Windows. In case you face any issues during installation, I'd suggest you to refer to the [official docs.][to-official-docs]  

Thanks for reading!

[to-jekyll-site]: https://jekyllrb.com/
[to-rubyinstaller-site]: https://rubyinstaller.org/downloads/
[to-official-docs]: https://jekyllrb.com/docs/
