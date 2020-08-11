---
layout: post
title: "How to Set Up a Jekyll Website"
excerpt_separator: <!--more-->
categories: 
- How-to
---

If you want to set up a blog like this one for yourself, then read on for a step-by-step guide on how to get your blog going with Jekyll. 

**Note**: I am using Linux as my operating system, so some steps might vary if you're on a Mac or using Windows.

Here's the link for the [Jekyll](https://jekyllrb.com/) website; some steps will be taken directly from there.

## **Installing Ruby**

1. **Install Ruby Installer**: [latest version](https://rubyinstaller.org/downloads/)
2. When taken to the 'Installation Destination and Optional Tasks window', check the first two boxes

3. Once it's done installing, make sure the checkbox is checked

4. At the Ruby installer window, run all options in order: 
  - Click 1, then enter
  - When MSYS2 base installation is finished, uncheck the box because we are not running it right now
  - Click 2, then enter
  - Click 3, then enter
  - Exit out of window

6. Open up terminal and type: 
   - **ruby -v**: This tells you the current version of Ruby installed on your system
   - **gem -v**: This tells you the current version of Gems on your system

## **Installing Jekyll**

7. Continuing in the Terminal type: **gem install jekyll bundler** 
   - This installs Jekyll is installed on your system
   - run **jekyll -v** to make sure it is properly installed

8. Now we are going to create the site. Navigate to the folder location on your system for where you want your website to be stored. In this command, put the name that you want for the blog you're creating; for example `felicia_blog`. 
   - Type: **jekyll new <your blog name>**

9. Move into your blog directory: **cd <your blog name>**

10. Now we're going to start our website on our localhost: `localhost:4000`. The first Type **bundle exec jekyll serve**