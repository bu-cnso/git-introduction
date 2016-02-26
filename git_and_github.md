# git and GitHub

If GitHub is your first exposure to git, it's very easy to conflate the two.

## What is git?

Among other things, `git` is:

* The type of repository that contains a `.git` folder
* A set of tools for manipulating repositories and transfering data between
  repositories
* The protocols used to transfer data

The authors of `git` describe it as "plumbing", and interfaces as "porcelains".
It was originally hoped that people would write nicer interfaces, but it turned
out that by the time people got their heads around the details of how it
worked, most then thought the command-line tools made sense.

That said, a number of interfaces do exist, including integration with many
IDEs (even
[Matlab](https://www.mathworks.com/help/simulink/ug/branch-and-merge-files.html)).

## What is GitHub

GitHub is:

* A host for repositories
* An access-control manager (SSH keys -> Users -> Capabilities)
* A web-based porcelain
  * Forks = fancy `git clone`
  * Pull requests = fancy `git merge`
  * Pull request reversion = `git revert`
  * In-browser editing, direct uploads = `git add`, `git commit`
  * Integration = git hooks
  * Releases = `git tag`
* A collection of social networks based around projects

The GitHub [desktop client](https://desktop.github.com/) is another example of
a porcelain, integrated with GitHub.

## Alternatives to GitHub

GitHub isn't unique! Getting to know competing software/services will help
solidify the difference between the parts that are git, and the parts that
are GitHub.

* [BitBucket](https://bitbucket.org) - Similar to GitHub, built for
  [Mercurial](https://www.mercurial-scm.org/), but expanded to support git
  repositories
* [GitLab](https://about.gitlab.com) - Self-hosted, similar to GitHub in use,
  good for maintaining private infrastructure
* [gitolite](http://gitolite.com/gitolite/) - Self-hosted, minimal
  interface, more flexible, [can
  work](https://blog.effigies.us/synchronization-with-git-annex-and-gitolite/)
  with [git-annex](https://git-annex.branchable.com)

A [comprehensive list](https://git.wiki.kernel.org/index.php/GitHosting) is
maintained on the [git wiki](https://git.wiki.kernel.org).
