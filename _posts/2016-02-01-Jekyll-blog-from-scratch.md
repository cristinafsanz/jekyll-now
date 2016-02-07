---
layout: post
title: Jekyll blog from scratch
permalink: /blog/
---

Now that I have tried different jekyll themes, it is time to start one from scratch. I will use a very useful tutorial: <a href="http://jmcglone.com/guides/github-pages" target="_blank">Creating and Hosting a Personal Site on GitHub</a> , that explains very well all the steps to do. The only thing that is different in my case is that I use Project Pages instead of User Pages, so I will specify here the differences. 

As I use project pages to be able to have all my projects in my Github account, I have to create a new repository:

Steps in GitHub:

- Enter a project name: project-name

- Make the repository public

- Initialize with a README

- Click create repository

Steps in the computer:

- In the terminal, create a new directory and make a clone of the repository to do the changes in local.

	git clone https://github.com/username/projectName.git

- Add the gh-pages branch in the new repository once inside the directory of the project (the branch name gh-pages is a special branch that Github uses to get files to build and publish from).

	git checkout -b gh-pages

- Add the index.html 

- Create a _config.yml file that tells Jekyll some basics about my project. In this example, I'm telling Jekyll the name of my site and what version of Markdown we'd like to use. Moreover, I add the url for sitemap.xml and baseurl to specify the repository as I use Project pages.

        name: My project name

        markdown: kramdown

        url: http://username.github.io/project-name/

        baseurl: "/project-name"

- See the result executing 'jekyll serve' and open a browser in http://localhost:4000/project-name

- After doing changes, do the Commit and push to Github

	git add index.html

	git add _config.yml

	git commit -m "Add first code"

	git push origin gh-pages

- The Github pages site can be seen in:
	http://username.github.io/project-name

Usually the first time the GitHub Pages site is created it takes 5-10 minutes to go live.

<h2>Setting up Jekyll:</h2>

In order for Jekyll to work with my site, I need to follow Jekyll's directory structure.

- Create a .gitignore file to ignore the _site directory that Jekyll automatically generates each time I commit.

- Make a _layouts directory, and create file inside it called default.html. This is the main layout that will contain repeated elements like `<head>` and `<footer>`. So let's move those elements from index.html into default.html.

- Use the liquid tags {{ page.title }} in the title and {{ content }} inside the container section to inject content into the final web page.

- In the index.html, add the Front-matter at the top
	layout: default

	title: Index title

This Front-matter will be processed by Jekyll. Every time I commit a file that specifies layout: default at the top, Jekyll will magically generate the full HTML document by replacing {{ content }} in_layouts/default.html with the contents of the committed file.

- Add a main.css inside a folder css and link it in the default page to use it in all the pages:

`<link rel="stylesheet" type="text/css" href="{{ "{{site.baseurl" }}}}/css/main.css" />`

It is necessary to use {{ "{{ site.baseurl " }}}} when I use project pages, if I don't add it, it will try to find the css in http://username.github.io/css/main.css instead of http://username.github.io/project-name/css/main.css.


<h2>Setting up a Blog</h2>

- Create a new layout for the blog posts called post.html and a folder to store each individual post called _posts/.

- The post.html can use the default layout and adds a couple new liquid tags to print the title of the post and date.

- Make a _posts/ directory where we'll store the blog posts. Inside that folder will be the first post. It must follow the convention YYYY-MM-DD-title-of-my-post.md. This file name gets translated into the permalink for the blog post.

- In the Front-matter of the post I can add the layout, the title and the date:
	layout: post
	
	title: "My first post"

	date: 2016-02-01

- The .md extension stands for Markdown, and the Markdown syntax used inside the file gets converted to HTML by Jekyll. Markdown is a markup language with a syntax closer to plain text so that the user can write their HTML content quickly. HTML can be also used inside the Markdown files if it is needed a syntax more precise.

After commiting the first post, it can be seen in:
	http://username.github.io/project-name/YYYY/MM/DD/name-of-the-post

- As the reader won't always know the exact URLs of the posts, I can create a page on the site that lists each post's title and hyperlink. It can be created on the homepage or create a blog subpage that collects all of the posts.

- Create a blog directory and create a file named index.html inside it. To list each post, I'll use a foreach loop to create an unordered list of the blog posts.

- It can be seen in:
	http://username.github.io/project-name/blog/


<h2>Customizing the Blog</h2>

- Include the blog directory in the URL of the post with a permalink in _config.yml.
	permalink: /blog/:year/:month/:day/:title


<h2>Next steps:</h2>

- Create _includes. They're a lot like _layouts, only smaller snippets of markup and can be injected into the _layouts and pages.

- Create a DISQUS _include and call it in the post.html layout.

- Set up a custom domain instead of github.io.

- Create a sitemap.xml file for better SEO. You can have one automatically generated by GitHub Pages.

- Create a development branch to fix a bug or add a new feature and merge once it is done. This way, the master branch is clean.

- Look for inspiration checking out other jekyll blogs.




