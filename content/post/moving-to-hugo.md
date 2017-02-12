+++
date = "2017-02-01T13:12:26+02:00"
title = "Moving to Hugo"
Description = ""
draft = true
+++

![hugo-logo](https://gohugo.io/img/hugo-logo.png)

As I said in my [previous post](/post/fresh-start), I moved from my selfhosted [Ghost](http://ghost.org/) to [Hugo](https://gohugo.io/) website engine for my blog. And you may wonder why?
Why do you moved from that fancy modern growing Ghost?
Why do you choos "dark hourse" Hugo engine?
Why do you wanted to move at all?
How did you setup you blogging process?

You'll find answers on these questions in this post. So lets start from the begining.

## Bye, bye Ghost

Don't get me wrong. Ghost is realy good blog platform. It fits very good for private blogs and for companies. 
I even recommend Ghost to everyone who asked me about blogging platforms. So why not continue to use it? I want a static website solution. Yeah, I know about that Ghost static scripts that will generate static htmls from you Ghost blog. But you need to support those scripts with new versions of Ghost. Talking about new versions that's also one of the points to move for me. I had quite old versions (0.6) and update process could be painful. 
New updates appeared quite often for now and maintaine it with each new engine update is not comfortable. I want to blog but not to update platform each month.

## Hello Hugo

I used to use Octopress before and know all the pros and cons of static generated blogs. The one thing that anoid me with Octopress was Ruby. You have to manage it's different versions and that was a head ache for me. But the process of generating websites was fine for me. Aspecially it generates colpletely static web pages. That's what I was looking for. So I looked for different alternativs to Octopress but without Ruby. 
After trying out some static websites generators, I ended up with Hugo. Hugo is a really fast static site generator written in _go_. It's also very simple. I'll not write about it's features here. You can read about them on their web site - [https://gohugo.io/](https://gohugo.io/). What I'll tell is that how I setted it up and adopted my blogging process with it.

## Hugo + GitHub Pages = <3

As my new blog is completely static than I decided that GitHub Pages is the best place for it. Besides, they were created right for such things. Personal account and projects pages. That's all what they about.  GitHub has very informative setup guide. You can create project that is called your blogs name or you can create pages for your GitHub account name. The last one is the best choice for your personal pages. And other good thing for these pages is custom domaine support. So I've set my tulusha.com domain with it. Without custom domain my blog is placed on [https://alokard.github.io](https://alokard.github.io). As I said all details about the setup of GitHub pages you can easily find on their information site - [https://pages.github.com](https://pages.github.com).

The process of deployment of your Hugo blog to GitHub pages is just like pushing code to GitHub (of course if you do so;]). 
At first you checkout your created repository for your GitHub page. Open terminal and run next command:
```
git clone git@github.com:<username>/<username>.github.io.git
```

Than you need to copy generated after command `hugo` static site. It's placed in `public` folder:
```
cp -r public/* <username>.github.io/
```

And finaly you need to push your changes to GitHub:
```
cd <username>.github.io
$ git add --all
$ git commit -m 'Initial commit'
$ git push
```

Cool! Now we have our blog running on [<username>.github.io](/). And also it's under version control system and we can roll our change back and fourth if we want to.

In the same way you can keep your blog source under version control system too. You can place it in the same repository as published website by putting it in separate brunch.

## A bit of automation

OK. Now we have our static blog running. But for now we need to deploy every new version by hands if we want to write a new post. It's a bit anoying. Let's automate it!

We need Continues Integration (CI) service for automated deployment of our new blog. For open source blogs I suggest to use [Travis](https://travis-ci.org) or [CircleCI](https://circleci.com). I worked with Travis before so for my new blog deployment I decided to try CircleCI. I hered a lot about this CI service and here is good oportunity to try it in action.



