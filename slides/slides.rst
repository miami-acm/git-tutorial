.. role:: raw-html(raw)
   :format: html

.. role:: bash(code)
   :language: bash

============
Git Tutorial
============

Kyle Rogers & Nate Mara

2014-10-22

=====
Intro
=====

Git is a free and open source version control tool.

======================
A Brief History of Git
======================

In 2002, the Linux source code began to be managed by BitKeeper
(proprietary software).

BitKeeper revoked license for Linux in 2005.

============
Requirements
============

	- Distributed
	- Performs efficiently
	- What goes in is what comes out

===========
Git is Born
===========

	I'm an egotistical bastard, and I name all my projects after
	myself. First Linux, now git.

	-- Linus Torvalds

Linus developed Git during a two week coding session. After two
months, version 1.0 was released.

Since 2005, has developed into one of the largest source code
management tools.

===========
Basic Terms
===========

----------
Repository
----------

A data structure, that contains, among other things a historical
record of changes in the repository.

------
Commit
------

A snapshot of your repository at a specific time. 

------
Branch
------

Set of commits, generally used for a single
purpose. Branches can be combined with :bash:`git merge`

==================
Basic Git Workflow
==================

	#. Create repository
	#. Clone repository to local system
	#. Make changes to files
	#. Commit changes to git repository
	#. Push commits to remote

======================
Picture of File System
======================

.. image:: images/stages.png

============
Git Commands
============

:bash:`git init`
	Create a new, empty repository in the current directory

:bash:`git add <file>`
	Add :bash:`<file>` to the staging area. Files in the staging area
	will be added to the next commit.

:bash:`git commit -m '<message>'`
	Commit files in the staging area. :bash:`<message>` should be a
	message that explains the changes made in the commit.

:bash:`git help <command>`
	Get help for the given command

=================
More Git Commands
=================

:bash:`git checkout <branch>`
	Switch to the branch identified by :bash:`<branch>`. To create a
	new branch with this command, add the :bash:`-b` flag.

:bash:`git checkout <file>`
	When a file on disk differs from the version stored in Git, use
	this to revert :bash:`<file>` to the state stored in Git.

:bash:`git status`
	View the current status of the repository. Shows:
		- current branch
		- modified files
		- and more!

================
First Time Setup
================

Before we do any work with Git, we have to set some settings:

	#. :bash:`git config --global user.name "My Name"`
	#. :bash:`git config --global user.email email@email.com`
	#. :bash:`git config --global core.editor SOME_EDITOR`
	#. :bash:`git config --global push.default simple`

===================
Your First Git Repo
===================

Let's create an empty Git repository at :bash:`~/git-repo/`

	#. :bash:`mkdir ~/git-repo`
	#. :bash:`cd ~/git-repo`
	#. :bash:`git init`
	#. Profit!

=====================
Your First Git Commit
=====================

Let's add a readme file to our Git repo:

	#. :bash:`YOUR_EDITOR README.md`
	#. :bash:`git add README.md`
	#. :bash:`git commit -m 'add readme file'`

===================
What Just Happened?
===================

Let's take a minute to look at what we just did:

	#. Edit a file
	#. Add that file to the staging area
	#. Commit changes in the staging area to the repository

On the next slides, we will look at each step more in depth with the
:bash:`git status` command:

===================
What Just Happened?
===================

---------
Edit File
---------

.. code-block:: bash

	$ vi README.md
	$ git status
	On branch master

	Initial commit

	Untracked files:
	  (use "git add <file>..." to include in what will be committed)

		README.md

	nothing added to commit but untracked files present (use "git add" to track)

===================
What Just Happened?
===================

------------------------
Add File To Staging Area
------------------------

.. code-block:: bash

	$ git add README.md
	$ git status
	On branch master

	Initial commit

	Changes to be committed:
	  (use "git rm --cached <file>..." to unstage)

		new file:   README.md

===================
What Just Happened?
===================

----------------------------
Commit Changes to Repository
----------------------------

.. code-block:: bash

	$ git commit -m 'add readme file'
	$ git status
	On branch master
	nothing to commit, working directory clean

===================
What Just Happened?
===================

---------------
Visual Overview
---------------

.. image:: images/file-lifecycle.png

===================
What Just Happened?
===================

-------------
Check the Log
-------------

.. code-block:: bash

	$ git log
	commit c9fd3e8dc41e0649fc3ba0e88bcc2f41a97d8144
	Author: rogerskw <rogerskw@miamioh.edu>
	Date:   Wed Oct 22 15:00:53 2014 -0400

    	asdf

If you have many commits, the `less` command will be used.

========================
Let's Try Something Else
========================

-------------------
Remote Repositories
-------------------

A *remote* is a copy of the repo in another location such as a server (like GitHub)

Save commits to a remote repository using

.. code-block:: bash
	
	$ git push origin master
	
Where 'origin' is the remote's name and 'master' is the current branch's name

========================
Let's Try Something Else
========================

--------
Branches
--------

What many beginner git repos look like:

.. image:: images/git-linear-branch.png

========================
Let's Try Something Else
========================

--------
Branches
--------

Taking full advantage of git branching

.. image:: images/git-branching.png


=========
Branching
=========
Create a new branch with

.. code-block:: bash
	
	$ git branch newbranchname
	
Switch to the branch with 

.. code-block:: bash

	$ git checkout newbranchname
	
Make some changes and commit them

=========
Branching
=========
After committing, switch back to the 'master' branch

.. code-block:: bash
	
	$ git checkout master

Look for your changes

--------------
What happened?
--------------

=========
Branching
=========

Merge your changes into the main development line

.. code-block:: bash

	$ git merge newbranchname
	
Now you should see your changes from your branch

=========
Branching
=========

Large projects will have **many** branches

.. image:: images/large-branching.png

================
Other Cool Stuff
================

--------
Stashing
--------

You can use git stash in order to save changes to a branch 

without actually committing

This can be useful if you made changes that aren't working, 

but need to go to another branch to do something else

================
Other Cool Stuff
================
-------
Tagging
-------

Tag commits in order to give them an easier ID

Makes it easier to revert back to or identify releases

================
Other Cool Stuff
================
-----
Blame
-----

Shows who exactly committed each line of code

Useful for identifying who introduced a bug

Also useful for determining how much each person actually contributed

================
Other Cool Stuff
================

-----
Reset
-----

Can be used to reset the repo to a previous commit

------
Bisect
------

Do a binary search on commits in order to determine when a bug was introduced


==========
Questions?
==========

