---
layout: default
title: "How to Set Up a Jekyll Website"
excerpt_separator: <!--more-->
permalink: setup-jekyll-blog
categories: 
- How-to
---

If you want to set up a blog like this one for yourself, then read on for a step-by-step guide on how to get your blog going with Jekyll. 

**Note**: I am using Linux as my operating system, so some steps might vary if you're on a Mac or using Windows. Here's the link for the [Jekyll](https://jekyllrb.com/) website; some steps will be taken directly from there.

<!--more-->

## Creating a Profile on Github

You can skip this step if you already have a Github account. Github pages is where your blog files will be kept. 

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

- Now we are going to create our blog! Navigate to the folder location on your system for where you want your website to be stored. In this command, put the name that you want for the blog you're creating; for example `felicia_blog`. 
   - Type: `jekyll new <your blog name>`

- Move into your blog directory: `cd <your blog name>`

- Now we're going to start our website on our localhost: `localhost:4000`. The first time you need to run this command, but after this first time you only need to type `jekyll serve`.
  - Type `bundle exec jekyll serve`

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
    - `Gemfile.lock`: 
    - `index.md`

## Hosting your Jekyll Website on Github Pages

# First install Git

# Have Github account

