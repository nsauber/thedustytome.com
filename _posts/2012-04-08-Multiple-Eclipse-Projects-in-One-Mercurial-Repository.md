---
layout: post
title:  "Multiple Eclipse Projects in One Mercurial Repository"
date:   2012-04-08 19:17:00
---

Eclipse is a tremendous IDE... except when it's not. One area I've found less than intuitive has been creating a single Mercurial repository to house multiple interdependent projects.

While exploring Android development, I've wanted to keep my application and test projects together in a single repository. It's (hopefully) obvious that you'd want to track changes to your application code and test code alongside each other so they're always in sync. But for some reason, adding these two separate projects to a single repository is not intuitive to do from inside Eclipse, at least while using the [MercurialEclipse](http://javaforge.com/project/HGE) plugin.

There is probably a better way to do this, but here's how I've gotten things working. It relies on a combination of MercurialEclipse and an external-from-Eclipse tool. I recommend the excellent [TortoiseHg](http://tortoisehg.bitbucket.org).

Finally, these steps were outlined pretty quickly and I haven't tested all scenarios. Your mileage may vary.

#### Creating a new repository and adding projects:
1. If needed, create a new workspace in Eclipse.
2. Create a new directory underneath your workspace to contain your repository, and init a new repository there.
3. Open the workspace in Eclipse.
4. Add one or more new projects. You can try unchecking "Use default location" and adding them under the repository root, but it still always adds them to my workspace root for me.
5. Close Eclipse.
6. Manually move the project folder inside the repository folder.
7. Commit the project's contents to your repository.
8. Open the workspace in Eclipse.
9. There will still be an entry in your Package Explorer for the project that you moved, which references the old project location. Delete it (right-click -> Delete). We'll re-add it momentarily.
10. File -> Import -> Mercurial -> Projects from Local Mercurial Repository
11. Browse to the root of your repository directory. Eclipse should detect the projects inside your repository directory, including any that might already be listed in your Package Explorer.
12. Check only the project(s) you just created, and click Finish.

#### Importing projects from an existing repository:
1. If you haven't done so yet, clone the repository to a directory inside your workspace using an external tool.
2. Open the workspace in Eclipse.
3. File -> Import -> Mercurial -> Projects from Local Mercurial Repository
4. Browse to the root of your repository directory. Eclipse should detect the projects inside your repository directory.
5. Select the project(s) you want, and click Finish.

##### Reference links:
* Here's an article explaining [how to add projects inside a "repository" folder inside the workspace](http://ekkescorner.wordpress.com/blog-series/git-mercurial/workflow-create-multi-project-repositories-hg/).
* And here's the [StackOverflow answer](http://stackoverflow.com/a/7867354/38657) that made the whole thing click.
