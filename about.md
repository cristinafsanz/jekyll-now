---
layout: page
title: About
permalink: /about/
---

I'm Cristina Fernández Sanz, a Web Developer working in Madrid, Spain.

### Discovering the Front side

I began in the web world as a Backend Developer, but I fell in love with web design in 2013, so I started to learn about html, css, responsive design and javascript in order to jump to the bright side. Last year (March 2015) I started to work as a Frontend Developer, but I have much to learn yet. Because of that, I decided to create some personal projects in order to improve my skills.  


### Where do I put all my designs?

I heard about Github pages to host websites for free and since I work with git and Github already, I decided to try it.  

The Github users can have both a personal website (called User pages) and websites related to specific Github projects (called Project pages). I chose the last option, because I want to have a website for each project and another one to collect them.


### Github Pages: Project pages

When you use Project pages, you have to create a branch 'gh-pages' in your repository and push your web code there. If your repository is called 'project-name' and your user is 'username', you will have your website in http://username.github.io/project-name. 

It requires to be a public repository on Github.


### Jekyll

Github pages also comes with a static site generator called Jekyll. If you add folders and files following specific naming conventions, when you commit to GitHub, Jekyll will build your website. 

Jekyll is commonly used to create blogs without using databases to store the website content, but it is also very useful to avoid repeated code in your website, as you can use templates or includes that Jekyll will convert.


### Creating my portfolio

To start working with Jekyll I decided to follow the following tutorial, <a href="http://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/">Build A Blog With Jekyll And GitHub Pages</a>, whose author suggested to fork his repository (jekyll-now) and start from there. I think it is a good advise to start understanding how Jekyll works. After doing 1 or 2 Jekyll blogs, you can start your Jekyll blog from scratch, with this tutorial <a href="http://jmcglone.com/guides/github-pages">Creating and Hosting a Personal Site on GitHub</a> for example.

It is very easy to work with Jekyll. You can clone the repository and work locally. You can see the results in http://localhost:4000/project-name if you run 'jekyll serve', so you don't have to push to Github until you tested before.


### Blog like a developer

Apart from showing my designs, I decided to create a blog in my website to share ideas and information about my personal projects (code, design, useful tutorial, ...). This way, I learn about Jekyll blogs and contribute to the community at the same time.

If you want to write a blog and you are a developer, this is your way to do it, you can clone the project, adding new files, commit and push them like a developer. Even you can edit the files with vi in your console, the sky's the limit :)

Although with the tutorials that I told you before you won't have any problem of building a Jekyll blog, I'm going to summarize the things that you can have with Jekyll. You can research more about them if you are interested.

To work with Jekyll, you have to add some information about the project in a _config file, like the name or the baseurl with the repository name. 
You can create your templates inside the _layouts directory and use them in the final html or md using the Front-matter (plain text at the top of the file). You can use liquid tags in the templates to inject the content that is not common in the final page. A good example is having the header, nav and footer in a template and use it in all the pages.

You can use html or md files to put your code, because Jekyll will convert them to html at the end. The idea is to be able to write code quickly, and with Markdown you are closer to plain text. For example, for blogs with only a title and paragraphs this is very useful. And you can use html if you need it.

The posts will be stored as text files and have to be in the _posts file, and you can use a template for them also (in _layouts file). Each post has to follow this convention: YYYY-MM-DD-title-of-your-post.md.

You can use includes in the _includes folder to have little templates used in the layouts.

You can have comments using DISQUS.

And these are only the basic things, you can add the sharing buttons for social networks, you can set up a custom domain, create blogging pagination, etc.


### And Jekyll for non developers?

Currently I am going to do a Jekyll blog for a friend. I will check Prose.io for her to edit the blogs. The idea is to add her as a user in the project in Github and use this edit tool to add/edit the blogs. I will write about the results here, I hope it goes well! 


### Notes for developers

- Jekyll is a static site generator written in Ruby.  

- Liquid is a Ruby library for rendering safe templates which cannot affect the security of the server they are rendered on.

- You don't need to know Ruby in order to use Jekyll, only learn liquid to do things beyond the basics. But to do plugins, you have to write them in Ruby.


### Alternatives

- Surge, a static web publishing for Front-End Developers. It can be a good alternative to Github pages when it is not convenient to put the code in a public Github repository. You can use git with Bitbucket to use version control system for the blog source.
