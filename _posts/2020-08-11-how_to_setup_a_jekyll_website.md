---
layout: post
title: "How to Set Up a Jekyll Website"
excerpt_separator: <!--more-->
permalink: setup-jekyll-blog
categories: 
- How-to
tags:
- Jekyll
- Github
---

If you want to set up a blog like this one for yourself, then read on for a step-by-step guide on how to get your blog going with Jekyll. 

**Note**: I am using Linux as my operating system, so some steps might vary if you're on a Mac or using Windows. Here's the link for the [Jekyll](https://jekyllrb.com/) website; some steps will be taken directly from there.

<!--more-->

## **Installing Ruby**

- **Install Ruby Installer**: [latest version](https://rubyinstaller.org/downloads/)

- When taken to the `Installation Destination and Optional Tasks window`, check the first two boxes

- Once it's done installing, make sure the checkbox is checked

- At the Ruby installer window, run all options in order: 
  - Click 1, then enter
  - When MSYS2 base installation is finished, uncheck the box because we are not running it right now
  - Click 2, then enter
  - Click 3, then enter
  - Exit out of window

- Open up your terminal and type: 
   - `ruby -v`: This tells you the current version of Ruby installed on your system
   - `gem -v`: This tells you the current version of Gems on your system

## **Installing Jekyll**

- Type: `gem install jekyll bundler` 
   - This installs Jekyll on your system
   - run `jekyll -v` to make sure it is properly installed

- Now we are going to create our blog! Navigate to the folder location on your system for where you want your website to be stored. In this command, put the name that you want for the blog you're creating. For example: `felicia_blog`. 
   - Type: `jekyll new <your blog name>`
   - Example: `jekyll new felicia_blog`

- Move into your blog directory.
   - Type: `cd <your blog name>`
   - Example: `cd felicia_blog`

- Now we're going to start our website on localhost by navigating to: `localhost:4000`. To actually start up the website for the first time, you need to type `bundle exec jekyll serve`. Once it's running, you'll see in the terminal `Server address: http://127.0.0.1:4000/` or something similar. Hit `ctrl` + click and it should take you to the basic jekyll website at that location. After that, you only need to type `jekyll serve` to start up the website.

## What's Included in the Basic Jekyll Blog

- When you first create a jekyll blog, you'll see default folders and files that already come with jekyll. You can modify any of these files to customize your blog.
  - Underneath the highest-level folder (this will be your main blog folder, for example `felicia_blog`), you'll see several subfolders:
    - `_posts`: this will be where you will keep your blog posts
    - `_site`: this will where the final, finished output of your entire website will be kept. This folder will be continuosly updated as you work on your website. It is recommended not to mess with anything in this folder.
    - `.sass-cache`
  - Underneath the folders you should see several files: 
    - `_config.yml`: These are the settings for your website. You can configure these settings to change how it runs.
    - `.gitignore`
    - `404.html`
    - `about.md`: This is our about page for our website.
    - `Gemfile`: This file specifies various gem dependencies for your website. 
    - `Gemfile.lock`: This file is created after you run `bundle install` if you make a change to the Gemfile.
    - `index.md`

## Creating our local and remote repositories

Before we create our repository and push our files, we need to initialize our local repository. In the terminal where our files are located, type `git init`. This initializes the local repo and allows us to push our files to our remote repo that will be our website on Github.

### Install Git

Go to the [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) website to find instructions on how to install Git onto your system.

### Have a Github account

Go to the [Github](https://github.com/) website to create a github account.

### Creating a remote repository

Now we have to create the remote repository on Github to where we are going push our code to. On the `Repositories` tab, you'll see a green button that says `new`. Click on that to create the repo. Where it says `Repository name *`, type the name that you want for your website. Below that you can create a description and make it either public or private. Create the repository. Now that the remote repo is set up to receive our files, we need to commit those files and connect the remote and local repos to each other. You should see a little clipboard icon with a url inside of a box. Click the clipboard to copy the address, as this will be used in the terminal in the next step.

1. Type: `git remote add origin <url address of your newly created website>`
  - Example: `https://github.com/<your username>/felicia_blog.git`
2. Type: `git add .`
3. Type: `git commit -m 'Adding files'`
  - After the `-m`, you can add any message you want that briefly explains what you are doing
4. Type: `git branch -M main`
5. Finally, type: `git push -u origin main`

Now if you go back to your Github repository page and refresh, you should see all the files now in your remote repository. 

## Hosting your Jekyll Website on Github Pages

On the `settings` tab on your remote repository, scroll down to where it says `Github Pages`. Where it says source, choose the source where your website will be built from. I chose `main` for mine. Click `save`. Underneath that you can choose a theme for your blog or website. Once it is saved and you refresh the page, you will see a green message that says your website will be hosted at the url given to you. If you click on it, it should take you to your website.

Congrats! You have now created a blog using Jekyll!