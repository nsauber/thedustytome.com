---
layout: post
title:  "Creating a Front-End Build Template, Part 1"
date:   2015-01-24 16:09:00
#tags: Programming, JavaScript, Automated Build 
redirect_from: "/20150/02/24/Creating-A-Front-End-Build-Template-Part-1/"
---

For a long time I've avoided getting into any "serious" front-end development work... by which I mean, of course, JavaScript (_shudder_). I started hacking on HTML in my teens, but once I got into "real" programming, and especially once I started programming professionally and learned that "proper" development required things like a build script and Continuous Integration server, working in JavaScript always felt like going back to the wild west. No type safety, no unit tests, and endless browser incompatibilities... Why would you spend any more time in that lawless frontier than necessary?!

Well things have come a long way in the last few years. Front-end frameworks like [Backbone.js], [Angular.js], and [Ember.js] have taken much of the pain out of writing client-side JavaScript. And JS is thriving on the server and desktop, mostly thanks to [Node.js] and the tooling built on top of it.

So this is where I've decided to finally join the party (or at least get a taste of all the fun everyone's having). I'll be starting with a simple sample project and, over several posts, incrementally building up a full front-end build script that:

* generates CSS using a pre-processor,
* consolidates and minifies JavaScript and CSS so downloads are fewer and smaller,
* runs static analysis to check the JavaScript for common problems, and
* executes JavaScript unit tests.

I'll be updating [this GitHub repository][GitHubRepo] as I go, so feel free to follow along both here and on GitHub. I'm learning as I go, so there will doubtless be mistakes or offenses to accepted style along the way. Feedback is welcome, but please be gracious. ;-)

### Setting up a sample application

So before we get into creating an actual build, let's start with a simple sample project. Instead of writing one just for this, let's borrow one that already exists. [Angular's site][Angular.js] has a simple "Todo List" example that will work perfectly (currently on their main page, below the header "Add Some Control"). In the [GitHub repo][GitHubRepo] for this post, you'll see I've added three files to the root of the repo which were copied directly from Angular... `index.html`, `todo.js`, and `todo.css`. If you clone the repo and open `index.html` in a local browser, you should have a functional, though minimally styled, JavaScript application.

OK that covers things for Part 1. Next time we'll install a few tools and write a minimal build script.

[Backbone.js]: http://backbonejs.org/
[Angular.js]: https://angularjs.org/
[Ember.js]: http://emberjs.com/
[Node.js]: http://nodejs.org/
[GitHubRepo]: https://github.com/nsauber/FrontEndBuildTemplate

