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
