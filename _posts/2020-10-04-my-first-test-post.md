---
layout: single
title: "Welcome to my blog. Made in Jekyll!"
date: 2020-10-04
---

# Welcome

**Hello world**, this is my first Jekyll post.
I hope you like it!

## Installation

1. [Jekyll](https://jekyllrb.com/docs/)
2. [Minimal Mistakes](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/)

I first installed Jekyll! I used the official documentation to do this. But as it started to turn out I figured I wanted to use a theme. After looking for a theme that suited me I found out that it's alot easier to just fork it via Github and host it in on github pages for free!

Since I'm looking for a cheap/free option that doesn't require me to learn alot of new stuff this was the perfect option.

## Edit files

Editing I did mainly in the \_config.yml file. This file takes care of the most important things such as links, a bio, and so on.

## Creating a blogpost

To create a blogpost you just create a .md file in the \_posts folder and that's it. (ofcourse respecting the format:YEAR-MONTH-DAY-title.MARKUP -> 2011-12-31-new-years-eve-is-awesome.md)

All you have to do is add some markdown for the layout and title and you're ready to go. Jekyll has a very easy way of working and since I didn't really bother with a CMS I can just write down notes in markdown and later on convert all my notes to a full blog post.

This probably isn't the best way of working since a CMS is better for blogging. But I do have to admit this way is way cooler than the occasional CMS like WordPress.

[Creating a post by Jekyll](https://jekyllrb.com/docs/posts/)

## Creating a page

Since I'm planning on using this website as a form of portfolio I wanted to have an about page.

To create a page there's multiple options. You can do it via html & md. My theme has everything already set up so all I had to do was make a .md file in the \_pages map. Because the .html was already set-up I just had to provide some content and edit a few little things in the \_site\about map.

[Creating a page by Jekyll](https://jekyllrb.com/docs/pages/)

## Editing in a decent environment.

To work in a decent environment is a necessity. I don't want to be bothered to push everytime I want to see a change.
Luckily you can do this via jekyll serve. But since this theme uses a gemfile it's required for me to run a command over bundle. To do this I use the command: "bundle exec jekyll serve"

## Useful links

- [Typora](https://typora.io/)

Typora is a very handy markdown editor. I use this instead of word or the basic notepad.

- [Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

Sure markdown is easy but I don't know every little thing out of the top of my head. So this came in quite handy aswel.
