---
layout: post
title:  "Github Cheetsheet"
date:   2014-05-16 
categories: github
---


As I am new to github, I decided to put a list together of the most common comannds used. This was taken from the github git <a href="https://github.com/github/training-materials/blob/master/downloads/github-git-cheat-sheet.pdf?raw=true">cheatsheet</a>: 



Working with snapshots and the Git staging area

{% highlight ruby %}
git status
show modified files in working directory, staged for your next commit
git add [file]
add a file as it looks now to your next commit (stage)
git reset [file]
unstage a file while retaining the changes in working directory
git diff
diff of what is changed but not staged
git diff --staged
diff of what is staged but not yet committed
git commit -m “[descriptive message]”
commit your staged content as a new commit snapshot
{% endhighlight %}


BRANCH & MERGE
{% highlight ruby %}
Isolating work in branches, changing context, and integrating changes
git branch
list your branches. a * will appear next to the currently active branch
git branch [branch-name]
create a new branch at the current commit
git checkout
switch to another branch and check it out into your working directory
git merge [branch]
merge the specified branch’s history into the current one
git log
show all commits in the current branch’s history
{% endhighlight %}

