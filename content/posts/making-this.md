---
title: "Making This"
date: 2020-12-17T20:47:59+03:00
draft: false
toc: false
images:
tags: 
  - untagged
---

Making something like this is as simple as it looks. There were a few things I wrestled with, mainly GitHub submodules, but I ended up getting through. I'll explain them further down, both for your sake and my own. I know I'll forget it all in a week.

*Note*: It has been exactly 8 weeks since I wrote that note above. I still have not completed this post. I remember absolutely nothing from when I first made it.

# Step 1
I'm hosting this on [Github Pages](https://pages.github.com/). For this, I need to create a repository called *alisalemwala.github.io*. Everything is automatically hosted from there. Keep it all lowercase, otherwise it won't work. Everything before *.github.io* should be your GitHub username in lowercase, no more, no less.

# Step 2
I'm on a Mac, so I have those stupid *.DS_STORE* files everywhere. Need to create a *.gitignore* file to ignore them. `Commit`

# Step 3
I need to create the actual Hugo project now. Run this anywhere:
```bash
hugo new site demo
```
There's now a new *demo* folder with empty hugo configurations. Copy the contents of this to the *alisalemwala.github.io* folder. That's an empty website. `Commit`

# Step 4
I need to connect submodules. I don't remember why. I need to read about it again and add it here. I do know that it's to add the theme somehow. For **Hermit**:
```
git submodule add https://github.com/Track3/hermit.git themes/hermit
```
There should be a *themes* folder, with another *hermit* folder inside it. That's the submodule. `Commit`

# Step 5
I need to specify which directory the files are published from. This is where Hugo autogenerates the files to display. The *docs* folder. So go to *config.toml* and add these in new lines:
```
baseURL = "https://alisalemwala.github.io/"
publishDir = "docs"
```
This should finalise your basic configuration. To test this, run:
```
hugo server
```
Visit whichever port on localhost where this is deployed (1313 for me) and click around to see if everything is okay. Now build:
```
hugo -D
```
Everything is built! `Commit` and if you wait for the GitHub pipeline to finish, you should be able to visit your version of https://alisalemwala.github.io/ and see the same things you saw on localhost.

# Step 6
I've got another step in my notes which says to copy everything from the *exampleSite* folder inside the *hugo* theme file and re-run `hugo -D`. I don't know why I did any of this. I also added a note that submodules halted my progress a lot. I remember using a workaroud for them in the beginning, just to see the site working at least. Based on the commit history, it seems I got them working later, but I can't be sure. I need to see if this is actually a step, or just some confused notes.

# Step 7
I need to add a post. Run:
```
hugo new posts/making-this.md
```
THe post is created. Edit the contents in Markdown to get the content you want. In the header, change the `draft` property to `false`. Run `hugo -D` to create the requisite files. `Commit`