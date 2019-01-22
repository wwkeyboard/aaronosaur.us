---
title: "Git Log Files"
date: 2019-01-22T12:18:31-06:00
draft: false
---

Often I'm curious about what's changed in a git repository. `git log`
is a good start, but it's focused around the commits themselves. This
requires everyone to write great commit messages. Luckily the git cli
interface can easily give me more information.

`git log` can take a directory argument, which will filter the commits
to only the given directory. This is very helpful for a monorepo. The
next step is to list out the changed files in each commit. `git log
--stat` accomplishes this, but can be overwhelming if there is a very
large commit in the history. `git log --shortstat` shows the number of
files and lines changed, without listing them.

The `--shortstat` will sometimes let you find the commit you are
looking for, but you may want more information about the files that
were changed. In this case `git show --name-only <the sha of the
commit>` will list the commit and the files that are changed within
it. This is often what I'm looking for to get an overview of what the
commit is about.
