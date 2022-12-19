# Version control with Git

<a name="wig"></a>
## What is Git and Github?

Git is a free, distributed version control system for software projects that was released in its first version in 2005. 
The programme allows multiple developers to work on a project simultaneously, regardless of their location. Version 
control makes it easy to add changes to the project independently and from anywhere, to log and track these changes, 
and to access older versions of the project at a later date. Git is platform-independent and can therefore be used in 
almost any environment. 

GitHub, on the other hand, facilitates git collaboration. It is a platform that can hold code repositories in a 
cloud-based repository so that multiple developers can work on a single project and see each other's edits in real time:

It also contains functions for project organisation and project management. For example, you can assign tasks to 
individuals or groups, set permissions and roles for collaborators and use comment moderation to keep everyone up to 
date. In addition, the GitHub repositories are publicly accessible. Developers from around the world can interact with 
and contribute to each other's code to modify or improve it.

For research, the [Docs](https://docs.github.com/en "Github Docs") of Github or the 
[Docs](https://git-scm.com/doc "Git Docs") of Git can be used. For the workflow, an initial exposure to Git is extremely 
helpful, allowing the work processes to be understood concretely. are understood.

<a name="gconf"></a>
### Install Git

<a name="gfl"></a>
#### Git for Linux

Execute the following command in the terminal:
<pre><code>sudo apt-get install git</code></pre>

<a name="gfw"></a>
#### Git for Windows

1) Download Git for Windows from [here](https://git-scm.com/download/win "Download Git").

2) Run the installer and follow the wizard steps.

<a name="gfm"></a>
#### Git for MacOS

1) Download Git for Windows from [here](https://git-scm.com/download/mac "Download Git").

2) Run the installer and follow the wizard steps.

<a name="gitconf"></a>
### Git - Local configuration

Installation instructions for the respective operating system can be readily obtained from Google. One of the first 
steps in using Git in conjunction with Gibhub is to configure Git on your own computer.

Inside the terminal:

<pre><code>git config --global user.name "Pseudonym/Name"
git config --global user.mail "Mailadress"</code></pre>

Furthermore, extremely complex configurations are possible.

<a name="repo"></a>
### Create a new repository

The initialisation command of Git is necessary for this:

<pre><code>git init</code></pre>

Git then creates a new repository directory in the current directory. All files required by Git are stored in the 
subfolder /.git. In UNIX systems, the dot in front of the folder name indicates that this directory is hidden.

Git stores the corresponding versions of the programme we are working on in .git so that we can subsequently track how 
we have changed our programme.

Example: I want to create a repository called **program**.

I create a directory called **program**.

<pre><code>mkdir /home/user/program</code></pre>

I then change to the appropriate directory and create the appropriate repository using Git's initialisation command:

<pre><code>cd /home/user/program</code></pre>

<pre><code>git init</code></pre>

If you change to the appropriate /.git directory and run the ls command, you will get the following output:

<pre><code>branches  config  description  HEAD  

hooks  info  objects  refs
</code></pre>

The folder /.git contains various subfolders, which we won't be doing much with at the moment, as Git automatically 
manages all versions. 

<a name="change"></a>
### Working with git

The following will be about understanding how the different versions are managed within a project and what nutritional 
value git offers for one's own workflow. Many IDEAs facilitate working with Git in connection with Github. However, it 
is also necessary here to understand what is actually used how and above all why within the IDEA. 
Here, everyone is free to do version management relatively automatically or manually. 

In the following, we will first introduce version management with Git. It should be noted that we will work exclusively 
locally. This means that all changes and subsequent work will be done exclusively on our own computer and nothing will 
be put online.

<a name="gitadd"></a>
#### git add - Bridge between working directory and staging area

With a **commit**, the state of a project is saved at the corresponding time where the command was listed. Here, a 
commit corresponds to a version of the project, so to speak.

It is important to understand here that with a commit, the state of a project or a specific file in our **working directory** 
is transferred from the project to the so-called **staging area**. A commit is first prepared in the staging area with 
the following command:

For single file:

<pre><code>git add [FILE]</code></pre>

For entire folders:

<pre><code>git add [FOLDER]</code></pre>

After we have marked the corresponding files/folders with the command in the staging area, we could execute a commit 
directly. First, however, an important note:

Assuming we would continue to write our programme in our working directory after committing to the staging area, the 
changes we have made would not be adopted by the version stored in the staging area. For this, we would have to execute 
the git add command again.

Here it can be helpful to imagine several working levels:

![alt text](https://github.com/tmwProjects/MSAT/blob/master/Pictures/gitstations.jpg)

<a name="gitcommit"></a>
#### git commit - Bridge between staging area and repository

Since we have stored the current version of our programme in the staging area, we should switch to storing the current 
version in our repository from our staging area. This can be done by using the following command in the terminal:

<pre><code>git commit -m "message"</code></pre>

This command creates a new commit from all the staged changes. When committing, it is necessary to store a commit message. 
For a better overview, it is helpful to store in the commit message what was specifically changed. Short and concise is 
the appropriate home remedy for the first line. This is followed by an empty line and then a small, more concrete description.

For this purpose, the parameter -m is used in connection with the message in the inverted commas. If a commit was carried 
out, a concrete **commit ID** is attributed to this commit. This is important when it comes to the work history of the 
repository.

It is worth noting that one atomic change per commit should be used to maintain the clarity of the repository. 

Here are two examples: 

- One commit per bug
- One commit per feature

If the commit command was used without the **-m** parameter, Git will prompt you to put a message in a text file. If 
this doesn't happen, for example because you don't leave a message, the commit command will be aborted.

**Tip**: If a programming project is growing and other programmers from all over the world may be working on your project, 
it would be advisable to leave all commit messages in English.

The **following** parameter is useful if you have committed something and later find out that what you committed doesn't really work. 
Then the original commit gets a new commit ID. This way, you don't have to do another commit.

To change a commit, use the following command in the terminal:

<pre><code>git commit --amend</code></pre>

This will ensure that the latest changes from your **working directory** are included in the **staging area**.

**Important**: This rewrites the log from the repository. More precisely, the last commit is overwritten. Ideally, you 
should only use this command locally on your computer.

This becomes important when several people are working on a repository. Confusion can arise because not all people 
working on the repository have the same version on their computer.

<a name="gitlog"></a>
#### git log - History of the commits

This command allows you to display the individual changes to your repository. An individual commit is clearly identified 
by its SHA I hash. These hashes are created on the basis of the corresponding commit so that no two commits can have the 
same checksums. 

To do this, use the following command in the terminal:

<pre><code>git log</code></pre>

The order of the commit history is such that the oldest change is shown at the bottom and the most recent at the top. 
You are shown the individual commits, including the corresponding checksums, author's name, time and, last but not least, 
your commit message. It is important to note here that the most recent commit is referred to as **HEAD**.

Example:

```
commit 0fc55f28f09d4590c20422608bb58e7c8c3c307f (HEAD -> master, origin/master, origin/HEAD)
Author: jbloggs <jane.bloggs@protonmail.com>
Date:   Tue Jul 13 16:33:54 2021 +0200

Changes

commit 0d3407f361bfa326848843f89f65677b668f89e8
Author: jbloggs <jane.bloggs@protonmail.com
Date:   Tue Jul 13 16:28:53 2021 +0200

Changes

commit f759673ab7192fc2c22e7a2af723ea7f0b2adccf
Author: jbloggs <jane.bloggs@protonmail.com>
Date:   Tue Jul 13 16:25:23 2021 +0200

Changes

commit f3a0ab4bd479ebd110e6a13e62462857143050c5
Author: jbloggs <jane.bloggs@protonmail.com>
Date:   Tue Jul 13 15:28:19 2021 +0200
```

If we look at the history of the repository, we see a history with different hash values. The last commit is referred 
to here as HEAD. HEAD here means the most recent commit checked out. 

Example:

```
0fc55f2 (HEAD -> master, origin/master, origin/HEAD) Changes
0d3407f Changes
f759623 Changes
f3a0db4 Changes
82b182b Update README.md
d02ccb6 Add files via upload
0df2ffe Create README.md
32e5dca Initial commit
```

We see here a series of commits with corresponding abbreviations of the hash values and the **HEAD** commit. If we look at 
the commits from top to bottom, the second commit (calculated from **HEAD**) is correspondingly the second to last commit. 
This can be identified not only with its checksum, but also as **HEAD~1**. This is the parent of the **HEAD** commit. 
The third commit is then **HEAD~2**, the fourth commit is **HEAD~3**, etc.

These names can also be used instead of the hash values of the individual commits. This makes it a little more 
convenient to work with.

Example:

<pre><code>git diff f759623 HEAD</code></pre>

or 

<pre><code>git diff HEAD~1 HEAD</code></pre>

Another important parameter for the command is **-p**. This displays significantly more information for the commits, such 
as which lines within the code specifically added or removed. If the commit needs to be displayed in less detail, the 
following parameter can be used:

<pre><code>git log --oneline</code></pre>

Example:

```
0fc55f2 (HEAD -> master, origin/master, origin/HEAD) Changes
0d3407f Changes
f759623 Changes
f3a0db4 Changes
82b182b Update README.md
d02ccb6 Add files via upload
0df2ffe Create README.md
32e5dca Initial commit
```
For more information on the parameters use:

<pre><code>git log -h
git log --help</code></pre>

<a name="gitdiff"></a>
#### git diff - Show differences

This command is useful if you are working within your working directory, but you are not sure which changes have already 
been applied to your staging area. With the following command, you can see the relative changes between the working 
directory and the staging area:

<pre><code>git diff</code></pre>

To see the relative changes between the staging area and the repository, use the **--cached** parameter.

Example:

<pre><code>git diff --cached</code></pre>

If you want to see specific differences between two individual commits, you need the commit IDs of the two commits and 
the following command:

<pre><code>git diff [hash1] [hash2]</code></pre>

Example:

<pre><code>git diff 0d3407f f3a0db4</code></pre>

```
git diff 0d3407f f3a0db4

diff --git a/Program/program.py b/Program/program.py
index 12b063f..4a669d8 100755
--- a/Program/program.py
+++ b/Program/program.py
@@ -1,7 +1,5 @@
 #!/usr/bin/env python
```

The variables **a** and **b** in front of the individual versions do **not** refer to concrete folders or directories, 
but to the corresponding versions that we put into relation.

The following output:

<pre><code>@@ -1,7 +1,5 @@</code></pre>

means that in the first file the **first line** has been deleted and a total of **seven lines** are output, therefore 
**-1.7**. Subsequently, with the second file, one is added to the **first line** and a total of **five lines** are output, 
therefore +1.5

**Important**: If the command **git diff --cached** does not produce any output, it is probably because no concrete 
changes were made in the staging area.

It is quite possible that the comparison will show you changes that may not be correct. This is probably because git 
assumes what changes need to be made to get from hash1 to hash2. Therefore, it is important to store the hash values 
from old to young.

**Note**: Whoever commits **first** should also be named **first**. 

In the simple case that we look at the changes of commits in relation to a single file, then it becomes quite clear. 
However, it is often the case that within a project there are several files that are changed within one commit. Then, 
of course, you will see a lot of changes. In order to be able to differentiate this somewhat, use the following important 
parameter to view the changes of a specific file:

<pre><code>git diff [hash1] [hash2] -- [dataname]</code></pre>

Example:

<pre><code>git diff 0d3407f f3a0db4 -- program.py</code></pre>

Note: The **-- [dataname]** parameter can be used with all the git commands presented, such as git log. It is also possible 
to view changes to specific file formats or filenames. A proxy can be used for this.

Example: 

<pre><code>git log -- *.py</code></pre>

or 

<pre><code>git log -- program.*</code></pre>

<a name="gitreset"></a>
#### Git reset - revert changes

Here we can remove **all** changes from the **staging-area**.  The prerequisite for this command is that changes are 
stored in the staging area at all.For this we use the following command:

<pre><code>git reset</code></pre>

If it is a question of removing **specific** changes, such as from a specific file, then the following command can be 
used in conjunction with the corresponding file parameter in the terminal:

<pre><code>git reset [filename]</code></pre>

But not only all changes marked for a commit can be undone, but also changes that refer specifically to a commit. The 
following command is responsible for this:

<pre><code>git reset [commit hash]</code></pre>

Here, all changes in the workind directory remain, but all commits **after** the commit with the specified commit hash 
are deleted. This means that all changes that have already been committed to the repository with the corresponding 
commits are returned to the working directory after the above command.

![alt text](https://github.com/tmwProjects/MSAT/blob/master/Pictures/gitreset.jpg)

Another important parameter, but one that should be used with caution, is the **--hard** parameter. Here, all commits 
are also deleted after the corresponding commit hash. The difference to the previous command is that **all** changes 
are **discarded**. To do this, use the following command in the terminal:

<pre><code>git reset --hard [commit hash]</code></pre>

**Important**: When working with the git reset command, you must be careful, because this command can cause significant 
data loss. Do not use this command when working with remote repositories, such as Github. These repositories are often 
shared with other people and this command automatically changes the git history. If in doubt, always tend to **not** use 
the command.

The parameter **--hard** can also be used in other ways. Assuming there are correct changes in your repository and you 
want to continue working on your programme based on this current repository. If you are working in your working directory 
and unfortunately find that your changes have led you astray, you can use the following command to overwrite your current 
working directory with the current repository (MASTER):

<pre><code>git reset --hard</code></pre>

But here too, make sure you know what data is in your working directory before you execute the command. This can lead 
to immense data loss.

<a name="check"></a>
#### Git checkout - Jump to a commit

The **git checkout** command restores the state of a given commit. Then the current working directory is in the state 
it was in at the specified commit hash. You can view files, compile the project, run tests and even edit files without 
fear of losing the current project state. None of your actions and changes are saved in the repository.

Type the following command in the terminal:

<pre><code>git checkout [hash]</code></pre>

**Important**: Git tries to make local changes here, which can lead to conflicts. Only use this command if your working 
directory is empty or has no changes.

With the git checkout command, we can check out a previous commit and return the repository to the status. Checking out 
a particular commit puts the repository into a state with the HEAD detached. In the detached state, all newly made 
commits are orphaned as soon as you return to an established branch. Orphaned commits are deleted by Git during the next 
purge. The purge occurs at configured intervals and removes orphaned commits permanently. To prevent orphaned commits 
from falling victim to garbage collection, we need to make sure that we are in a branch.

Once you have finished working on a particular commit, you can jump back to the original version of your project with 
the following command:

<pre><code>git checkout master</code></pre>

<a name="name1"></a>
#### Git stash - cache changes

In case you want to see the status of your project from a few weeks ago, but you still have changes in your current 
working directory and/or staging area, you can use the command to display the status from that point in time without 
losing the current changes. You can use the following command to cache your current changes:

<pre><code>git stash</code></pre>

In short, git stash allows you to cache the current changes in your working directory and staging area.

Workflow example:

1) You save the current state in the stash.
2) Look at the past commit.
3) Switch back to the current state.
4) Read the old state from the stash.

Output:
```
Saved working directory and index state
"WIP on master: 016c048 Create index file".
HEAD is now at 016c048 Create index file
(To restore them type "git stash apply")
```

Following this, you can use the previously introduced **git status** command to see that your current working directory 
is cleaned up:

```
# On branch master
nothing to commit, working directory clean
```
The last saved stash always has the smallest room on the list, as if you were always adding another package to a stack. 
With the following command you can look at all cached stashes:

<pre><code>git stash list</code></pre>

Output:
```
stash@{0}: WIP on master: 016c048 Create file
stash@{1}: WIP on master: a1370d1 Revert
stash@{2}: WIP on master: 1cd6015 Change numbers
```

With the parameter **pop**, you can always restore the last saved stash. What is meant is that with the command

<pre><code>git stash pop</code></pre>

**stash@{0}** is restored first, followed by **stash@{1}** and then **stash@{2}**.

You also have the option of using the already introduced command **git diff** to compare the current stash with what is 
in your current working directory. With the stash command and the previously introduced commands, you have creative ways 
to jump between versions and changes without having to worry about losing recent changes. 


<a name="name1"></a>
#### Git revert - Undo changes (Other way)

Here I would like to introduce a command that also reverts changes, but in a slightly different way. Here, a new commit 
is created that reverts the corresponding changes. You have the option of changing a commit afterwards, as described 
above. This was done, for example, with the command **git commit --amend**, but this only worked as long as the 
repository was local. Here Git offers you the option of making a new commit that undoes all the changes made to an 
existing one.

<pre><code>git revert [Commit Hash]</code></pre>

Instead of removing the commit from the project history, it determines how to reverse changes caused by the commit. A 
new commit is then added with the corresponding reversed content. This prevents Git's history from being truncated, 
which is important for the integrity of your commit history and for reliable collaboration.

When the command is executed, a commit is created as described, which must also contain a corresponding commit message. 
In this particular case, this commit message is generated automatically. This makes sense in so far as it may not even 
be marked in the repository history that this is a revert.

![alt text](https://github.com/tmwProjects/MSAT/blob/master/Pictures/gitrevert.jpg)

You should use this undo command when you want to reverse a commit from your project history. This can be useful, for 
example, if it turns out that a bug was introduced into the project by a very specific commit. Instead of manually 
navigating to the code in question, fixing it and committing a new snapshot, you can use git revert to do the whole 
process automatically.

A revert has two important advantages over a reset. First, the project history remains unaffected: The process has no 
effect on commits that have already been published in a shared repository. Second, you can apply git revert to individual 
commits at any point in the history. git reset, on the other hand, only works retroactively from the current commit.

The advantage of using revert is that a new commit is created to undo certain changes. This way, no commits are deleted 
from the commit history or orphaned. git revert is the safer option compared to git reset in terms of losing code. 

<a name="name1"></a>
#### Git blame

With this command you can display changes to a file. It shows line by line in which commit it was last changed.

<pre><code>git blame [filename]</code></pre>

To make working in the terminal more comfortable and to keep an overview, you can also use the following command to 
highlight the same commits in colour:

<pre><code>git blame --colour-lines [filename]</code></pre>

Example:

```
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   1) #!/usr/bin/env python
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   2) 
f759623a (G. Raymond  2021-07-13 16:25:23 +0200   3) 
f759623a (G. Raymond  2021-07-13 16:25:23 +0200   4) 
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   5) import secrets
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   6) import string
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   7) import time
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   8) import numpy
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200   9) from pyfiglet import Figlet
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  10) import argparse
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  11) import sys
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  12) 
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  13) #start = time.time()
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  14) 
f759623a (G. Raymond  2021-07-13 16:25:23 +0200  15) 
f759623a (G. Raymond  2021-07-13 16:25:23 +0200  16) 
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  17) chars_full = string.digits + string.ascii_letters + string.punctuation
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  18) chars_digits = string.digits
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  19) chars_ascii = string.ascii_letters
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  20) chars_punctuation = string.punctuation
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  21) chars_ascii_digits = string.ascii_letters + string.digits
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  22) chars_ascii_punctuation = string.ascii_letters + string.punctuation
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  23) chars_digits_punctuation = string.digits + string.punctuation
^32e5dca (Joe Blow    2021-07-04 09:38:59 +0200  24) 
0d3407f3 (John Smith  2021-07-13 16:28:53 +0200  25) 
0d3407f3 (John Smith  2021-07-13 16:28:53 +0200  26) 

```

This can be helpful when working with several people and you want to make sure that if there is a bug, for example, 
that you write to the right person about it.

For more detailed handling of the **git blame** command, use the following command in the terminal:

<pre><code>git blame --help</code></pre>


<a name="name1"></a>
#### .gitignore-Data

With the so-called gitignore you can have files ignored. The file .gitignore contains a list of paths that are ignored 
by git. Here, changes to this data will have no effect on the commands **git diff**, **git add**, etc.

**Important**: The .gitignore file should always be committed so that certain files, folders, etc. are not included in 
the shared repository in the first place. This can also be very important when working together in a larger team.

Create a file called .gitignore inside your working directory as follows:

<pre><code>nano .gitignore</code></pre>

Example of the content of a .gitignore file:

```
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# C extensions
*.so

# Distribution / packaging
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
share/python-wheels/
*.egg-info/
.installed.cfg
*.egg
MANIFEST

# PyInstaller
#  Usually these files are written by a python script from a template
#  before PyInstaller builds the exe, so as to inject date/other infos into it.
*.manifest
*.spec

# Installer logs
pip-log.txt
pip-delete-this-directory.txt

# Unit test / coverage reports
htmlcov/
.tox/
.nox/
.coverage
.coverage.*
.cache
nosetests.xml
coverage.xml
*.cover
*.py,cover
.hypothesis/
.pytest_cache/
cover/

# Translations
*.mo
*.pot

# Django stuff:
*.log
local_settings.py
db.sqlite3
db.sqlite3-journal

# Flask stuff:
instance/
.webassets-cache

# Scrapy stuff:
.scrapy

# Sphinx documentation
docs/_build/

# PyBuilder
.pybuilder/
target/

# Jupyter Notebook
.ipynb_checkpoints

# IPython
profile_default/
ipython_config.py

# pyenv
#   For a library or package, you might want to ignore these files since the code is
#   intended to run in multiple environments; otherwise, check them in:
# .python-version

# pipenv
#   According to pypa/pipenv#598, it is recommended to include Pipfile.lock in version control.
#   However, in case of collaboration, if having platform-specific dependencies or dependencies
#   having no cross-platform support, pipenv may install dependencies that don't work, or not
#   install all needed dependencies.
#Pipfile.lock

# poetry
#   Similar to Pipfile.lock, it is generally recommended to include poetry.lock in version control.
#   This is especially recommended for binary packages to ensure reproducibility, and is more
#   commonly ignored for libraries.
#   https://python-poetry.org/docs/basic-usage/#commit-your-poetrylock-file-to-version-control
#poetry.lock

# PEP 582; used by e.g. github.com/David-OConnor/pyflow
__pypackages__/

# Celery stuff
celerybeat-schedule
celerybeat.pid

# SageMath parsed files
*.sage.py

# Environments
.env
.venv
env/
venv/
ENV/
env.bak/
venv.bak/

# Spyder project settings
.spyderproject
.spyproject

# Rope project settings
.ropeproject

# mkdocs documentation
/site

# mypy
.mypy_cache/
.dmypy.json
dmypy.json

# Pyre type checker
.pyre/

# pytype static type analyzer
.pytype/

# Cython debug symbols
cython_debug/

# PyCharm
#  JetBrains specific template is maintainted in a separate JetBrains.gitignore that can
#  be found at https://github.com/github/gitignore/blob/main/Global/JetBrains.gitignore
#  and can be added to the global gitignore or merged into this file.  For a more nuclear
#  option (not recommended) you can uncomment the following to ignore the entire idea folder.
#.idea/
```

This is an example from the repository directly from Github. There are some concrete examples for all common programming 
languages that can be used freely. For research or direct use, you can find the corresponding .gitignore files 
[here](https://github.com/github/gitignore ".gitignore").

test
