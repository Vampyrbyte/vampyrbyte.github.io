---
layout: post
title: Creating This Blog
date: 2020-03-06 00:00:00 +0000
description: Creating this very blog using Jekyll and GitHub Pages # Add post description (optional)
img:  2021-03-06/jekyll.png # Add image post (optional)
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
In order to tell github that this is the repository we want to use for our personal github page we will need to rename it in a specific way. You can only have one "personal" page per github account. Head to the settings page of your newly forked repository, which is likely still called "flexible-jekyll". We need to rename it to be "yourusername".github.io. in my case my username is "vampyrbyte" so I renamed the repository to be "vampyrbyte.github.io"

![github pages configuration](/assets/img/2021-03-06/githubpages.png)

Now at this stage, we will need to make some changes to some of the files to personalise the site. We could edit the files in github directly, but that is likely to get old rather quickly.

### Making edits to the blog.
I'm using Visual Studio Code on Windows to edit this blog. But its all possible from any text editor. Nearly all of the files required will be plain text. Visual Studio Code integrates with Git, which does add some complexity, but it will allow us to keep track of the changes we make. I'm a novice when it comes to Git, so I am sure there is a lot of nuance and features I am missing entirely however I'm a "learn as you go" type and find getting stuck in is the best. Once you've got [Visual Studio Code](https://code.visualstudio.com/) and [Git for Windows](https://git-scm.com/download/win) installed VS Code should recognise Git and be able to make use of it right away.

### Cloning the repository
Creating a clone of the repository on our local machine allows us to make changes locally, before uploading them to github. We are also able to install Jekyll locally so we can visualise changes as we make them, before changing the public website. On the github page for our "repo", we can get the URL for the repo. It appears to just be the URL for the page with ".git" appended. But we can see this under the green "Code" icon. 
When we first open VS Code, on the Welcome page there is an option to "clone respository". Copy the URL from github, and pick a local folder for the code to reside in. I keep all my gitrepos together in my documents.

Once this is complete we will now have a local copy of all the files needed for our blog, and we can begin to make some changes. A good place to start is the _config.yml file. This file contains details that are used to generate our blog, such as the site name and social media links. 
You may also have noticed if you loaded your blog in your browser that perhaps it does not work right. Initially my experience was that all the links were broken, and the page CSS did not load. This is because the theme we used contains a "baseurl" in the _config.yml. But our page is not hosted at vampyrbyte.github.io/blog but at the root of this site. Once we remove the "baseurl" config and upload the file, the blog will start to take shape.

The final step of making an edit is to upload the changed files to github. Visual Studio Code combined with Git will do this for us. At first this process will seem somewhat convoluted and might take some getting used to. The first step is to "Stage" our changed file, we can stage multiple files at a time. Once we have staged the file, we need to "Commit" the changes and provide a "message", the message can be anything, but will help us to identify what we did later if we have to look back. Up until this point, all of the changes have only been made to our local repository, and nothing has been uploaded to github. The final step is to "push" the changes to github. This is under the 3 dots in the source control menu. Once that is complete github will rebuild the blog and in just a few minutes you should see the changes made.

### Previewing the website locally.
While you are creating a blog post, or making any other changes, you will probably want to validate that you will get the expected result before making an update to your public page. To do this we can also install Jekyll locally on our machine, and ask it to "serve" us our local files for viewing in a browser.
There is a good guide on the [Jekyll site](https://jekyllrb.com/docs/installation/windows/) to getting it running on Windows. Once you have successfully installed Jekyll and can run `jekyll -v` successfully we can start to serve our website locally. If you are familar with the windows command line, you can navigate to your git repository folder where the blog is located. Or you can find the folder in Explorer, hold Shift and right click on the folder and select "Open in command window". Now we just need to run `jekyll serve` to create a local web server, running our page.

![jekyll serve](/assets/img/2021-03-06/jekyllserve.png)

Open the server address in your web browser to view your site. Now you can make changes locally without affecting your public page. 
If you are like me, on first attempt you might have got some errors. With this particular theme I got an error that the gem "jekyll-sitemap" could not be found. A quick search for this quickly led me to a [github page for the issue](https://github.com/jekyll/jekyll/issues/4972) and fortunatly the solution. Because I am running on Windows the solution was slightly different, but I had to run the following commands from the windows command line, adapted from the issue:
    gem install pygments.rb
    gem install bundler
    bundle install
Once these were complete, running `jekyll serve` again was successful, and I could view my blog in my web browser.
What is great is once this is running, it will automatically detect and update the page once we save any changes, so you can quickly save and refresh the page to check any changes.
While this is running, Jekyll creates a `.jekyll-cache` folder in our repository, and we don't need to upload these files to github, we could simply never stage and commit them, but they will continually show in VS Code unless we tell git to ignore them. To do that add `.jekyll-cache` to the `.gitignore` file. You can add any directory or file that you wish to be ignored there, simply one per line.

### Next Steps

The Next steps for me is to get a custom domain set up, and document how to setup a new blog post. I'll set up a custom e-mail to go with my new domain.

### Resources
- [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
- [Jekyll Resources](https://jekyllrb.com/resources/)
- [GitHub Pages Documentation](https://docs.github.com/en/github/working-with-github-pages)