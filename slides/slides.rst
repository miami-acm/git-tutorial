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
