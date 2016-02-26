# Personal Projects

Let's suppose that you're working on code for your lab, and your primary goals
are to track changes and be able to work on multiple computers without too much
pain.

Github is merely auxilliary to this mode of working, providing a nice interface
for looking at your repository history. You could just as well use
[gitolite](http://gitolite.com/gitolite/) or
[Gitlab](https://about.gitlab.com/), if you're comfortable or want to become
comfortable with some system administration.

## Preparation

Let's assume we've been working for a while, and want to start managing our
project with git.

```ShellSession
$ ls
freesurfer.py  images.py  params.py  util.py
```

Begin with:

```ShellSession
$ git init
Initialized empty Git repository in /data/$USER/Projects/fmri_python/.git/
$ git add params.py util.py
$ git commit -m 'Add environment and generic utility functions'
[master (root-commit) d9b8520] Add environment and generic utility functions
 2 file changed, 69 insertions(+), 0 deletions(-)
 create mode 100644 params.py
 create mode 100644 util.py
$ git add images.py
$ git commit -m 'Basic operations on image files'
[master  34591e4] Basic operations on image files
 1 file changed, 80 insertions(+), 0 deletions(-)
 create mode 100644 images.py
$ git add freesurfer.py
$ git commit -m 'Functions to work with FreeSurfer datasets'
[master  cf6bc4b] Functions to work with FreeSurfer datasets
 1 file changed, 131 insertions(+), 0 deletions(-)
 create mode 100644 freesurfer.py
```

## Aside: Dealing with `v1 ... vN` files

A pretty common precursor to version control is to simply copy working versions
of scripts before making any changes, and your directory can start to fill up
with files labeled with the date, or simply a sequential version number.

Let's suppose we have `script.m` already in the repository, and two old
versions hanging around:

```ShellSession
$ ls
script.m  script_v1.m  script_v2.m
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        script_v1.m
        script_v2.m

nothing added to commit but untracked files present (use "git add" to track)
```

Create a new branch called `old_versions`, add the old versions to it, and
return to `master`.

```ShellSession
$ git checkout -b old_versions
Switched to a new branch 'old_versions'
$ git add script_v1.m script_v2.m
$ git commit -m 'Track old versions'
[old_versions 8315c28] Track old versions
 2 file changed, 67 insertions(+), 0 deletions(-)
 create mode 100644 script_v1.m
 create mode 100644 script_v2.m
$ git push -u origin old_versions
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 264 bytes | 0 bytes/s, done.
Total 2 (delta 0), reused 0 (delta 0)
To git@github.com:$USER/matlab_project.git
 * [new branch]      old_versions -> old_versions
 Branch old_versions set up to track remote branch old_versions from origin.
$ git checkout master
Switched to branch 'master'
```

You'll see the old versions are gone, but we can bring them back as needed:

```ShellSession
$ ls
script.m
$ git checkout old_versions
Switched to branch 'master'
$ ls
script.m  script_v1.m  script_v2.m
```
