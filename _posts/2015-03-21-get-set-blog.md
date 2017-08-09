---
layout: post
title: "Get, Set, Blog. Using Jekyll."
tagline: "Blogging, the hacker's way"
description: "Blogging using jekyll"
category: tools
tags: [tools]
---
You might be familiar with the traditional blogging platforms like blogger, wordpress etc. Some of you might even be using these platforms for your blogs. In this post I am going to tell you how to get your blog up in a more elegant way using **jekyll**.


##Jekyll Introduction

Jekyll is a basically a static site generator. All it does is parse all of your site's code and place it into a subfolder named `_site`. Now, whenever a browser requests your blog, the server provides it with the `_site` content. 
Jekyll also supports text-to-html conversion (using Markdown by default), so there is no need to type html syntax for trivial things.
Jekyll by itself is not a blogging software. It is just a **parsing engine**. It's you who have create the layout and content of your blog.


##Prerequisites

In order to start blogging using jekyll, you need to have jekyll on your system (obviously). Jekyll can be downloaded as a ruby gem on most of the distributions. To install jekyll, type:

	$ gem install jekyll

Now, the next thing you need is a server where you will host your blog. Github provides you a platform for that. All you need to do is register on [github.com](https://www.github.com). Then create a new repository with title:

	$ username.github.com

Replace `username` with your github username. Now, you are ready for starting to blog. You can either build your blog from scratch (refer to [jekyll docs](http://jekyllrb.com/docs/home/)), or you can try this alternative -> using `jekyll bootstrap` for that purpose. This blog is also created using `jekyll bootstrap`. 


##Setting up your blog

`jekyll bootstrap` provides you with the jekyll required directory structure, a preinstalled theme, a Rakefile which makes creating new posts and pages very easy, some sample blog posts and a lot of other **liquid** code. This saves you from the trouble of learning **liquid** syntax and focus only on blog content. After you think you are proficient with jekyll, you can replace/modify those files with yours. With `jekyll bootstrap`, you can start bloggin right away. To use `jekyll bootstrap`, follow these steps:

Clone  the `jekyll bootstrap` repository by typing the following command:

	$ git clone https://github.com/plusjade/jekyll-bootstrap.git username.github.com

**cd** to *username.github.com* folder and change its remote origin url to point to your repository by typing the following command.

	$ git remote set-url origin https://github.com/username/username.github.com.git

Your blog is now up and ready. It would be live within an hour or two. To create a new post, just type in the following command:

	$ rake post title="My First Post"

You can check your blog locally too. Just type:
	
	$ jekyll serve

in the *username.github.com* directory. Then open your browser and goto **localhost:4000**.

After you are satisfied with your post, commit and push your changes to your repository on github server by typing:
	
	$ git add.
	$ git commit -m "commit message"
	$ git push origin master

Your changes will reflect globally after some time.

There are some sample post provided with the `jekyll bootstrap` package. You can get help from there, regarding how to write a post. Your blog can be highly customized. 
For guidance on installing themes in `jekyll bootstrap`, visit this [link](http://jekyllbootstrap.com/usage/jekyll-theming.html).
	

##Further reading
It is recommended that you should go through basic jekyll introduction from [jekyll docs](http://jekyllrb.com/docs/home/). You will get a better understanding of what is going on within your blog, and most of the syntax used. 

Visit this [jekyll quick start](http://jekyllbootstrap.com/usage/jekyll-quick-start.html) for more options with `jekyll bootstrap`.

You should also read the jekyll introduction page that will appear when you will run the server locally.
You can go through this [markdown syntax](http://daringfireball.net/projects/markdown/syntax#em) tutorial to get more familiar with it.

That's all from me now..
Happy Hacking :)


