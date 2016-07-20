# Github-ZenHub-Tutorial
A tutorial on how to use Github and ZenHub in a team environment.

# A Brief Overview

### What is Github?
**Github** is a popular website for hosting both open source and private git repositories. 

### Alright, so what is Git?
Git is what is known as a Version Control System (VCS for short). Similar to SVN, Git keeps a local copy of your source code for a project on every developer's machine, and a master copy on a server somewhere (in this case, Github).

### And what is ZenHub?
**ZenHub** is a Google Chrome plugin that supercharges Github with project management features using the built in issues systems.

### Issues system? Project management features?
**Issues** are project related tasks that must be completed or addressed. An issue can be something like a bug report, or the specification for a small portion of an application. These issues can then be assigned to a developer to handle them.

ZenHub adds **Project Management** features to your project's repository using the existing issues system. We will get into these features later on in the [Project Management with Zenhub]() section.

Alright, now that we have a few explanations, let's look at using Github within a multi-developer team.

# How to Use Git(hub) in a Team

Git is a complex VCS with many different operations, terms, and pitfalls that many developers that are new to the system must learn. Here we are going to go through some of those items in order to gain a better understanding of Git and it's powerful capabilities within a team environment.

First, a few definitions (Okay, more than just a few):

**Repository** - The actual storage space of the source code.

**Commit** - A commit is a confirmation of all past changes made to tracked files within the local version of the repository.

**Push** - Pushes all currently pending commits up to the server.

**Branch** - A Branch is an exact copy of the current code base, segmented into a separate part of the repository for isolated work. This might be used when creating a new feature for the project.

**Pull Request** - A Pull Request is created when a developer wishes to merge his working branch with another.

**Merge Conflict** - Occurs when a pull request contains one or more conflicting changes to files in it's commit history.

Remember these, as they will be important in the coming sections.

## Multiple people are collaborating in my repository! Help!
