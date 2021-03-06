---
layout: post
title: Creating This Blog
date: 2020-03-06 00:00:00 +0000
description: Creating this very blog using Jekyll and GitHub Pages # Add post description (optional)
img:  # Add image post (optional)
tags: [blog, github, jekyll] # add tag
---

GitHub Pages is a great free service from github that allows anyone to create a static website like this and host it for free. Using the Jekyll static site generator, alongside a theme I created the framework for this blog in just a few minutes. I'm sure the content will take a lot longer! 
That is part of the appeal of using a static site generator to create this, as opposed to a more complex system like WordPress. There isnt much upkeep involved here, and the necessary setup is very easy.

### GitHub
If you don't already have a github account, you are going to need one to make use of github pages. Head over to [github.com](https://github.com) and create an account. Your account username will be used to create the initial github pages address, like [vampyrbyte.github.io](https://vampyrbyte.github.io). but we can change this later.

### Finding a Theme
There are plenty of good places to look for finding a Jekyll theme. Check out the [resources page](https://jekyllrb.com/resources/) of the Jekyll website. I found this theme, Flexible-Jekyll, made by Artem Sheludko on [jekyllthemes.io](https://jekyllthemes.io/). Not all themes are free to use, but this one is. At this stage as I'm just starting out I wanted to keep my costs to a minumum so this is a great start. 
In order to start using the theme, we need to create a copy of this theme. The author recomeneds forking the theme on github, so we will start there. Perhaps if you work with github and git often you will have your own way of doing this, but I started by simply clicking the "fork" button at the top right of the github repository page for the theme.
This theme contains all the directory structure and files we will need to get the blog working on github pages

### Github Pages
In order to tell github that this is the repository we want to use for our personal github page we will need to rename it in a specific way. You can only have one "personal" page per github account. Head to the settings page of your newly forked repository, which is likely still called "flexible-jekyll". We need to rename it to be <username>.github.io