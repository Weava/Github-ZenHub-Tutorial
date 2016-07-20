# Github-ZenHub-Tutorial
A guide on how to use Github and ZenHub in a team environment.

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

## I'm new to this whole Git thing... How do I use it?

The simplest form of using Git is just to store your source code on a server. To create a local git repository, and push your files to the server, it only requires you to enter the following commands into your terminal or command prompt.

```
// Initializes a new git repository if one doesn't already exist
git init 

// Adds all files not mentioned in the gitignore to the local repository
git add * 

// Commits all changes to the repo with your own message
git commit -m "<my-commit-message>" 

// Adds a remote connection with git named origin to your git server.
git remote add origin "<url-to-my-server-copy>" 

// Pushes all pending commits to the server's master branch.
git push origin master 
```

When in a team environment, where an existing repository is already up, you will perform a clone, like so:

```
// Clones the server copy of the repo to your machine
git clone <repo-url-here>
```

This will copy all files and branches from the server onto your personal machine.

You can now start writing code with your team :)

## Multiple people are collaborating on my project! Help!

Don't worry, this is exactly what branches and pull requests are for!

#### Branches

When a developer on a team sets out to add new functionality to an application, they should create a new branch off the working directory of the project. This will allow them to add their functionality on a separate working set from any other developer, cutting down on time spent making sure they don't have to settle conflicts that arise in edited files. 

How does one create a branch? After using `git pull` to retrieve the newest changes from the working branch, go ahead and do the following:

```
// Retrieve latest changes in my current branch from the server.
git pull origin <current-branch>

// Checkout a new branch in your local repository.
git checkout -b "<branch-name-here>" 

// Push the new branch up to the server.
git push origin "<same-branch-as-before>" 
```

This new branch should be an immediate copy of the branch you checked out from at this point.

#### Pull Requests

So you've made the changes you need to get the new feature working in your new branch, and you want to add this feature back to the master branch. This will be done with a **Pull Request**.

Pull Request's create a request to merge your current branch back into the original working branch, or any other branch you wish to merge with. This will also notify the team that you are ready to start merging your code.

If there are any conflicting changes in any of the files, these will be solved by you and any other team members during a **Merge Conflict**. Merge conflicts allow you to compare the changes, and choose what to keep, throw away, or mix and match to make sure no important changes are removed.

That's just the high level of how these things work. As you use Git more in a team, you will gain much more experience with all of these different aspects of the VCS.

For now, let's look at some good tips to abide by when working with a team.

## Github Etiquette, and You

#### A Proper Branching Structure
All repositories in a team should contain, at minimum, two branches: `master` and `dev`.

The `master` branch should contain a stable version of the application with the latest working featuresets after a fair amount of testing. 

The `dev` branch should contain a generally tentaively stable version of the application that eventually all team members will be merging into with all of their feature branches.

On top of that, each developer should be working within their own branches on features that they have been assigned. Once the feature is completed, they will more than likely merge into `dev` although, they may want to merge with another branch in some situations.

For a better look at how the `dev` branch should operate, check out the [Dev branch's readme](https://github.com/Weava/Github-ZenHub-Tutorial/tree/dev) in this project. You can also check out more information on how a feature branch might work at the `new-feature` branch's [readme](https://github.com/Weava/Github-ZenHub-Tutorial/tree/new-feature).

#### Don't Step on My Toes, Man!
Teams should make a concerted effor to make sure they are not editing the same files at once. This comes down to how you structure the code within your application, as well as how you dole out pieces of the application for developers to work on.

Just remember that merge conflicts take time to resolve, and you should try to minimize conflicts as much as possible by only editing files that you know others will not be touching.

#### Teamwork Makes the Dream Work
When handling Pull Requests and Merge Conflicts, make sure to have a team member come by and review the changes made. This can serve as an impromptu code review, which can be a great learning tool. Also, when you pair up on pull requests, you minimize the chance of mistakes being made, leading to less headaches later on down the line.

#### What Did You Do On This Commit?
Make EVERY commit message mean something. You should be able to tell, at a glance, what a commit was all about, just in case you need to roll back later, or a teammate needs to know the changes made at a specifc time. These also allow you to have a nice timeline of features and code you added in previous iterations of the project.

Your commits should tell a story about how the project has come together up to this point.

These are just a few tips to keep in mind when working with others, among many. It is important to establish ground rules with your team to minimize any difficulties that arise from different vision for how the repository should work later on down the line.

Now that we have an idea about how to use Git in a team environment, let's look at how we can use ZenHub to keep track of our project's issues.

## Project Management with ZenHub
