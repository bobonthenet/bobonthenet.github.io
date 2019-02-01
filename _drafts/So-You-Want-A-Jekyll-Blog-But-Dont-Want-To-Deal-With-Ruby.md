---
layout: post
title: Easy Jekyll Development with Docker
---

## What is Jekyll?
If for some reason you are reading this and you don't know what Jekyll is, it is a static site generator that is great for blogging. Even better, you can host your blog for free on Github using Github Pages. As a software engineer I deal with and have become a big fan of using markdown. I won't get into why as that could potentially be a whole 'nother blog post. Each blog entry in Jekyll is a separate markdown file. The blog entries and other pages are maintained in a neat folder structure, you can edit with whatever your favorite editor is (VSCode right now) and version controlled using git. When you are ready to publish you just push your repo up to Github. This is probably not for everyone but as a software engineer who uses this workflow for pretty much everything else I do, this is perfect!

## Just One Problem
Jekyll, however, has one problem for me. It runs on Ruby, which is fine but I just don't want to deal with it. I don't have any issue with Ruby, I just don't have any other need for it, I don't want to set up a ruby dev environment on my PC for this one application. Setting up a development environment can be cumbersom and takes up resources on your PC. So how can you work on your Jekyll blog locally and not have to worry about setting up Ruby?

## Docker to the Rescue!
I haven't been 100% honest with you up to this point. This blog post isn't really about Jekyll, or Ruby. It is about the awesomeness of Docker! There are a lot of great use cases for Docker, my favorite so far is creating self contained development environments that you can include with your project. Setting up this blog is not the first project I've gotten involved with that has required it's own distinct development environment setup where I used docker to facilitate that. It is the easiest though as you will soon see.

## Setting Up Your Blog and Dev Environment
There are plenty of tutorials on how to set up docker so I won't go into that in this one. Getting your blog going is very quick once you have docker going with only two main steps. First head over to https://github.com/barryclark/jekyll-now and read through the Quick Start instructions. Once you have completed that you will have a Jekyll blog. It takes about 2 minutes! Once you have that ready to go you'll probably want to get hacking away on your blog locally. To do this, cd to your project directory with your  blog in it and execute the following command.

```
docker run --rm --volume="C:\Users\rbedard\Documents\bobonthenet.github.io:/srv/jekyll" -p 4000:4000 -it jekyll/jekyll:3.8 jekyll serve 
```

Of course change the host volume directory to match the path of your jekyll project. Once the container downloads and starts running that's it! Navigate to localhost:4000 and take a look.

## So what did you just do and why? 
You are now running a docker container with a Ruby dev environment in it. Jekyll is run and hosted inside the container with port 4000 opened up using ``` -p 4000:000```. Any changes to the files in your project directory are also made to the files in the container because we used the ```--volume``` flag. The other 2 flags ```--rm``` removes the container after you exit, which you can do with ctrl-c, and ```-it``` is the interactive flag which takes you inside the container. Both of those flags are optional but I find it easier to work with the container when I can see what is going on in the terminal.

## Making things even easier
I'm terrible at remembering a bunch of commands with flags. I'm constantly having to look them up and just having to type that incredibly long docker run command is no fun, so I found a way around that. In my project root I included a dev.cmd file with just the command to get the docker container running in it. This way I just have to navigate to my project folder type ```./dev``` and I'm ready to get working on customizing my Jekyll blog.

## Conclusion