---
layout: post
title: "How to Setup Your Website to Use the Hydeout Theme"
excerpt_separator: <!--more-->
permalink: setup-hydeout-theme
categories: 
- How-to
tags:
- Jekyll
- Hydeout
---

In the last post title "How to Set Up a Jekyll Website", I walked you through how to set up a website or blog. In this post, I will show you how to setup your blog or website to use the Hydeout theme. It is the theme that is used for my own personal blog. It's simple, clean and looks great. There are several steps that are needed to make this work and I can't guarantee that it will work for everyone. It has worked for me. 

**Note**: I'm not an expert on setting up Jekyll sites and I'm not sure why some problems may occur. That said, sometimes you may need to run `bundle exec jekyll serve` instead of `jekyll serve` to get the site running properly.

<!--more-->

Go to the [Hydeout](https://github.com/fongandrew/hydeout) theme Github repository. Where it says usage, it is mentioned that you need to add the Jekyll theme Hydeout Ruby Gem to your Gemfile.

1. Add: `gem "jekyll-theme-hydeout" to the Gemfile
2. Type: `bundle install` in the terminal
3. Since we are planning to host our website using Github pages, we need to add this to our `_config.yml` file: `remote_theme: fongandrew/hydeout`
4. In your `_config.yml` file, you should see a line that says `theme: minima`. Change `minima` to `hydeout`
5. Locate the `index.md` or `index.markdown` file (they're the same thing)
  - Add this to top of the file: 

```
---
layout: index
title: Home
---
```

Now when you restart the server and go to your webpage, it should load your website with the Hydeout theme. You can now go to the site's file and modify them to change how you want it to look. 

I hope this article was helpful! If you have any questions you can leave a comment and I'll respond as best I can.