---
title: Making A GitHub Pages Site
description: Jekyll makes building static websites easy
layout: post
thumbnail: assets/images/jekyll-tutorial.png
category: blog
---
Building a website can seem like a daunting task - There are dozens of frameworks, languages, and hosting sites to choose from, and each one has its own advantages and disadvantages. When creating this site I chose to use the static content generator Jekyll and hosting platform GitHub pages, as jekyll and pages integrate very well together.

# Installation
**Linux**\
Now that you've decided to make your website with Jekyll, you'll have to install it! On linux, this is fairly straightforward. The first step in installing jekyll is installing dependencies. These vary by distribution, so find and run the command for your distro [here](https://jekyllrb.com/docs/installation/other-linux/). After that, all you need to do is install jekyll using `gem install jekyll bundler`.
\
**MacOS**\
The steps for installing jekyll on a mac are similar to linux installation. The first thing you need to do is install ruby using homebrew. [This guide](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/) has an in-depth explaination on how to do that. Once you've installed ruby you just need to run `gem install jekyll` to finish the installation process and `jekyll -v` to make sure jekyll is working.
\
**Windows**\
Because there are several different ways to install jekyll on windows I'm not going to cover it here. If you're using windows I would recommend checking out [jekyll's official page](https://jekyllrb.com/docs/installation/windows/), which has some great installation instructions.

# Hello World
**Getting Started**\
Now that you've installed jekyll you can get started with building your first site! To get started, make a folder called `hello-world`. This will be the folder you build your site in. Inside of that folder you should make three files & a folder named `_layouts`:

```
| _config.yml       // Jekyll configuration
| _layouts
| | default.html    // 'default' layout
| index.md          // Content to be converted to HTML
```

Each file plays an important role in your new jekyll project.
* The `_config.yml` file will contain configuration info for jekyll, like URL and date formatting.
* The `_layouts` folder contains layouts, which are similar to the [views](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) in an MVC framework like rails.
* `default.html` is a view. Views are used to display markdown files, along with additional HTML.
* The final file you made, `index.md`, is a [markdown file](https://learnxinyminutes.com/docs/markdown/). Markdown files are processed by jekyll into plain HTML files, and they're what makes jekyll so much easier than plain html.

**Adding Content**\
Now you've made the files needed for your site, but they are empty and don't do anything. To finish your site, you need to add a few lines of code to each one as follows:

{% raw %}
```
name: Hello World //_config.yml
```
```
<!-- _layouts/default.html -->
<!DOCTYPE html>
<html>
    <body>
        {{ content }}
    </body>
</html>
```
```
---
title: My page
layout: default
---

# {{ page.title }}

This text goes into your index.md file. **Hello world!**
```
{% endraw %}

**Testing**\
If you try to open your new files in a browser, you'll notice that they don't do anything. This is because jekyll needs to compile and serve your website for it to work. To do that, use the `jekyll serve` command and open `localhost:4000` in your browser. If all goes well you should see the text **Hello world!** on your screen.

# 'Dynamic' Content
**Liquid**\
For the most part creating a website with jekyll is similar to making a static site. However, it differs in a few key ways. One way jekyll makes developing your site easier is its templating language, *liquid*. Liquid can be used to call part of other files, such as page.title in your hello world site. Liquid can also be used to call other things, like page thumbnails, titles, and virtually anything else you want to be 'dynamic'.
**Layouts**\
Another advantage of using jekyll over static sites is jekyll's *layouts* feature. When you made your hello world site you used a layout to display your `index.md` page. Layouts can be called in the front matter of a .md file, which is the area at the top of all jekyll .md files surrounded by dashes. Using layouts helps to reduce code repetition, as changing a single `article-layout.html` file is easier and less repetitive than changing the layout of every article on an entire website.

# Hosting
Now that you've made your site, how do you put it online? The easiest and cheapest way to do that is to use [GitHub pages](https://pages.github.com/). To host your site you're going to need to make a [GitHub account](github.com/). Once you've done that, make an empty repo with the same name as your website folder and push your site files into it. Finally, you need to go your repo's settings tab on github and scoll down until you see 'GitHub pages'. Then all you need to do is select your repository's main branch and you're done!

# Notes
This tutorial described how you can make a github pages site for a repository, but the steps for making a website for your account are similar. [GitHub's website](https://pages.github.com/) has additional information on making a personal site.

If you see anything wrong or missing, just create an issue on this site's [GitHub repo](https://github.com/owen-laney/owen-laney.github.io).

# Additional Resources
[Installation](https://jekyllrb.com/docs/installation/)\
[Official Guide](https://jekyllrb.com/tutorials/convert-site-to-jekyll/)
