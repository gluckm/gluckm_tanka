---
title: Making a website with blogdown
author: Mathew Gluck
date: '2021-05-02'
draft: true
slug: []
categories: []
tags: []
meta_img: images/image.png
description: Directions for making a website with blogdown
---
I want to record my thoughts on how I got my website up and running with blogdown, GitHub and Netlify. I followed the tutorial [Up & running with blogdown in 2021](https://alison.rbind.io/post/new-year-new-blogdown/#step-2-create-project) by Alison Hill. This is a very good tutorial, and it is my one of my go-to references for times when I forget how to do some blogdown-related task. At the time of my first time reading of Alison's tutorial, I was deficieint in some git-related prerequisit material. I had to take a short side quest to learn the basics of git before I could fully take advantage of the tutorial. 

My general impression is that everyone encounters their own obstacles when setting up a website with blogdown. This post is an effort to document my experience and record notes for myself for the unavoidable situtation where I forget something. 


# Prerequisites

You have to have
* R and R studio
* a GitHub account and a basic understanding of git
* a Netlify account

# Make a repository 

Go to your GitHub account and make a repository. Since we will eventually host the site with Netlify, you can name the repository whatever you like. Set to public (not sure if this is necessary). Initialize the repository with only a `README` (not with a `.gitignore`, not with a license). We will handle the `.gitignore` later. 

Once your repository is made, go to it's main page, select the `Code` button and copy the url (be sure in HTTPS mode) to the clipboard for later use. 

# Make new project in RStudio via clone
Open RStudio select `File> New Project> Verson Control > Git`.
Paste the url from the previous step in the appropriate place. 
Be intentional about where you create this new project on your workstation. 
Select **Create Project**

# Create Site
In the console, put `library(blogdown)`. If prompted to do so, install the library. 
Now in the console put `newsite(theme = "nanxstats/hugo_tanka")`. I use the `hugo_takna` theme, as the academic starter theme suggested in Alison's blog is a bit too cluttered for my purposes. You will get a short list of messages. Read it. Of particular note is that the messages will tell you how to serve the site locally  (by using `blogdown::serve_site()` in the console) and how to stop the server (by using `blogdown::stop_server()` in the console). At this point you should see a preview of your site in the viewer. You can pull the preview out of the Viewer tab and into a full-sized browser tab by selecting the window-with-arrow icon (next to broom icon). 

# Create Content

To create a new blog-style post whose title is "Fancy Post Title", in the console type
```
blogdown::new_post(title = "Fancy Post Title", 
                     ext = '.Rmarkdown', 
                     subdir = "blog")
```
The subdir entry is relative to the `content/` directory and the name varies by theme (for example in the academic starter theme, it is called post). Since this will be a typical workflow for creating new posts, now is a good time to adjust these settings in your `.Rprofile` (inside the project directory). For the first time, type 
```
blogdown::config_Rprofile() 
```
into the console. (this creates the file if it doesn't yet exist, otherwise it opens it for editing). To edit `.Rprofile` afterword, you have the option to select it directly from your Files tab in RStudio GUI. 

**RESTART R AFTER EDITING .Rprofile** by selecting from the RStudio top-menu `Session > Restart R`. 

At this point, under `/content/blog/` you should see a directory whose name is of the form `YYYY-MM-DD-post-title`. The contents of this directory are a single `index.Rmarkdown` file. Open this file in RStudio and make some changes. Then knit this file to markdown (`Cmd+Shift+K` on Mac, or select the knit button in the top panel of the file editor). This creats a file called `index.markdown` in the same directory as the `index.Rmarkdown` file. 

# Add/commit/push files to GitHub
Remember when we created the project in the first place? We made it a version control with git. RStudio has a git GUI, so you really can get away without knowing much git at all here. Before we do any of this, we need to take advangate of blogdown's check functions. There are a bunch of them including, for example `blogdown::check_gitignore()` and `blogdown::check_content()`. These allow you to double check that everything will run smoothly when building/updating your website. The function `blogdown::check_site()` performs all of the relevant checks (`config.toml`, `.gitignore`, Hugo, `netlify.toml`, content files) at once. After running `blogdown::check_site()` in the console and fixing all of the `[TO DO]`'s (you may leave some undone, e.g. publish a particular post at a future date, leave posts in draft mode), add/ commit/ push the project files (all the files in the project directory) to GitHub using the Git tab in RStudio. 

When I checked .gitignore the items I could safely ignore were `.DS_Store` and `Thumbs.db`. The directories I could safely ignore were `/public/` and `/resources/`. I also recieved a `[TODO]` that said I should ignore `.gitignore`. I added these five items to my `.gitignore` file, each on their own lines. So my `.gitignore` file looks like: 

    .Rproj.user
    .Rhistory
    .RData
    .Ruserdata
    .DS_Store
    Thumbs.db
    /public/
    /resources/


Shold we also do a `blogdown::check_netlify()`? 
**Need to go through this in more detail**

# Build Site on Netlify
Go to Netlify, sign up for accoutn if applicable. Log in and select `New site from Git > Continuous Deployment: GitHub`. Netlify will allow you to select from your GitHub repositories. Select the one you've been workign with for this project and leave all settings as they are. Select Deploy Site. You will get a Site deploy in progress message. In a minute or so, site will be deployed. Click the link to the site and enjoy. If you want to change the randomly-assigned subdomain name, then do it. 












