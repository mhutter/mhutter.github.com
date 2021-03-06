---
layout: post
title: Working with Git Submodules
#excerpt: Write me!
tags: [git]
---
I often struggle when working with Git Submodules, so here’s a quick primer with all the important information you need!

## Adding Submodules to your project

    git submodule add repo_url [directory]
    git commit -m 'added xyz as a dependency'

`git submodule add` works like `git clone`, so the directory name can be ommited. The changes will automatically be added to the index, so you can commit them right away!

## Cloning a repository with Submodules

    git clone repo_url --recursive

This will first clone the repo, and then initialize and update (read on) all submodules.

If you forget the `--recursive` flag when cloning, or when pulling in commits that add a Submodule, you have to do two steps: initialize, update:

    git submodule init
    git submodule update

This will create the required directories and then pull in the other repos.

### Update Submodules

Easy:

{% highlight bash %}
git submodule update --remote
git add submodule_dir
git commit ...
{% endhighlight %}

That’s it!

For more in-depth information on Git Submodules, read the [official documentation](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
