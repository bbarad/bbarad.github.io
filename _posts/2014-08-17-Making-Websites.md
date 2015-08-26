---
title: Making Websites
layout: post
group: blog
updated: 2015-08-25 12:00:00
---

**Update**: 

I just finished the website for the [Frost Lab at UCSF](http://frostlab.org) and I am really happy with it. It uses a very similar structure under the hood to the [Fraser Lab](http://fraserlab.com), but thanks to a new [css framework](http://materializecss.com), it has a distinctive look while maintaining a lot of the simple visual styles that I prefer. 

I've also gotten to see a few other people make personal or lab websites using github pages based on the templates I've generated: check out [Neville Bethel's homepage](http://nevillebethel.com) and [Eli Zunder's lab page](http://zunderlab.github.io). If you want to try your hand, I'd recommend forking my code on github for [this page](https://github.com/bbarad/bbarad.github.io) or the [Fraser Lab](https://github.com/fraser-lab/fraser-lab.github.io).

**Original Piece**:

In the past few months, I have gone from having no experience whatsoever making websites to having made 2 static sites and a small in-progress webapp (which I hope to share soon!). It has been a tremendous learning experience for me, but something that I found difficult starting out was just figuring out what technologies to build from.

<!--break-->

I have only been programming for about 18 months, and in that time I have primarily gained experience working in Python. I have very little knowledge of web technology beyond the basics that I have cleaned from googling and reading through tutorials and online documentations. Because of this, all of the success I have found in websites so far has been from starting with a very well-developed frameworks and tinkering from there. Given that I am only interested in web development as a means of making the work I am doing more available, I think that I probably will not progress past this point, and honestly I am happy enough with the results that I have seen that I don't think that is a bad thing. I thought I would share my experiences with some of the tools that I have used both for building the static sites as well as the webapp that might be of interest to others in my position.

## The Static Sites

A static website is very simple: it serves predetermined pages at their URLS. It has no database operating in the background, and is not making dynamic calls to decide what information to display (for the most part!). In short, it is not an app in any way.

I have worked on two static webpages now: one was for the [Fraser Lab](http://fraserlab.com) (which I joined in June) and the other is this website. Both had slightly different requirements. Whereas my webpage is for the most part just a simple place to house some of my projects and ideas, the Fraser Lab page takes on the responsibilities of a full lab webpage: publication and member information, a news page, full contact information, and access to the lab's private wiki. 

Both, however, serve the common goals of serving as a simple public face for the Fraser lab and for me, respectively. Because of this, my priorities were _clarity_, _maintainability_ (this one is very important to me), and _accessibility_ across both desktop and mobile environments.  I wanted websites that would be easy to update by anyone and which would not get messy with the addition of new content. I also wanted to only have to work once, rather than making layouts for mobile and for desktop. These are for the most part solved problems, as it turns out.

### Github Pages and Jekyll

When I first started working on my static site, I tried out a [Pelican](http://http://blog.getpelican.com/) blog, but ultimately I was lured in by the incredible simplicity of [Github Pages](https://pages.github.com/) (and, by extension, [Jekyll](http://jekyllrb.com/)). For simplicity and maintainability, nothing I have seen beats github pages. It takes the form of a git repository which automatically translates the content to a complete webpage using jekyll as an engine. It really is that simple. Github takes care of the builds and the hosting and provides a public domain, though it is possible to provide your own. The downside is that I am confined to working with the tools that github has decided to make available, most notably jekyll. This is not a bad thing, as I have enjoyed working with Jekyll, but it limits the number of plugins that can be used for things like pagination.

Jekyll is a ruby tool for serving static sites, and for the most part I have enjoyed working with it. The liquid template language (for procedurally generating content) has some idiosyncracies, but overall I have enjoyed writing in markdown and keeping data in YAML format. I find that it is very easy to get started and easy to add to. 

###Bootstrap

Jekyll provides the tools to serve the content, but making the website look nice, both on desktop and mobile, requires CSS, which I worked as hard as I could to avoid. [Bootstrap](http://getbootstrap.com) is a set of CSS and Javascript files which provide a framework to build nicely styled webpages. It is, as far as I can tell, the most common such framework on the web, and that was a major reason that I decided to use it: the community for working with Bootstrap is enormous. Anything that I wanted to do, had been done by someone, and that meant that the amount of real learning required to work with the CSS was minimal. At the end of the day, it is not possible to get away with not writing any CSS at all, but it is possible to get extremely close.

## The Webapp

In addition to the static sites, I am developing a web implementation on the model analysis tool that I am working on in the Fraser Lab. I haven't completed the webapp yet, so my thoughts here are not final, but the tools I have used so far have been fantastic and I thought I would share.

### Flask
I am comfortable with python and invested in becoming more comfortable with it. [Flask](http://flask.pocoo.org/) is a very lightweight framework which uses Python to develop web applications. Again I worked with bootstrap for the styling, but for actually communicating data (in both directions) with a remote server I have found it to be a fantastic solution. I am able to use mostly unmodified the python I wrote originally for the project and easily exchange data with the remote client. I am still early on but I will update this post as I try more out.

### D3.js and NVD3.js

[D3.js](http://d3js.org) is a fantastic tool for plotting interactively on web browsers, but I have found it very challenging to work with directly. Thankfully, I found the [nvd3](http://nvd3.org) library of reusable charts for d3. They provide a simple way to get started with d3 charts, though unfortunately their flexibility is greatly limited by the selection of pre-rolled charts available. I am on the hunt for a better solution so if anyone knows of one I am open to recommendations.