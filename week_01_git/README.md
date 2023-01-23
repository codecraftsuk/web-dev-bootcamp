

# 1. Introduction to GitHub and Git

# What is GitHub and Git

GitHub is a web-based platform that uses Git, a distributed version control system, to manage and store code. Git allows developers to track changes to their code and collaborate with others on the same codebase. GitHub provides a user-friendly interface for developers to access and manage their Git repositories, as well as additional features like bug tracking, project management, and code review. In short, Git is the tool that powers version control, and GitHub is a platform built on top of Git that adds collaboration features and more. The difference in the way that they are used is that Git is a command-line tool whereas GitHub has a user-interface (www.github.com) that makes it more user friendly.

## Version Control

Version control is vital for managing software development projects. Being able to track changes to code allows developers to:

- Centralise all code changes and additions to one code repository
- Allow for simple and effective collaboration within development teams
- Control the integration of new code into the codebase
- Track changes from the entire team over the full lifetime of the project
- Revert code back to previous versions
- Create code branches so that additions are made in isolation from stable code e.g. features are added in a test branch and then merged into the production branch that may be running the application
- Integrate with CI/CD automation tools such that code will be built and tested as it is generated and pushed to the repository automatically

## Repository

In Git, a repository (or "repo" for short) is a directory that contains all the files and metadata associated with a project. This includes both the current version of the project's files and the entire history of changes to those files. The repository is the fundamental unit in Git, as all version control operations, such as committing changes and branching, are performed on the repository. Each repository has a unique identifier, called a hash, that is generated based on the contents of the repository. A repository can be stored locally on a developer's machine or remotely on a server, such as GitHub. Developers can also clone a remote repository to create a local copy of it on their machine and make changes to it.

![image](images/repository.png)

## Branching

Branching in Git allows developers to work on multiple versions of a project at the same time. A branch is a pointer to a specific commit in the repository's history, and it allows developers to make changes to the codebase without affecting the main branch (usually called "master").

For example, when working on a new feature, a developer can create a new branch from the current state of the master branch and make changes to that branch without affecting the code on the master branch. Once the feature is complete, the developer can then merge the changes from the feature branch back into the master branch. This way, the master branch always contains the most stable and tested version of the code.

Git also allows multiple developers to work on the same branch simultaneously. In this case, Git will automatically try to merge the changes when one developer pushes their changes to the remote repository. If there are conflicts, the developers will have to resolve them manually.

Branching also enables developers to experiment with new ideas and to isolate the changes, if they don't work out, it can be discarded without affecting the main codebase.

![images](images/branching.png)

## Code Tracking

Code tracking allows development teams to keep track of all changes made to a project over time. This allows for greater organisation, as all additions to code are fully documented and attributed to the developer who made them.


# 2. Making a GitHub Account

1. Go to the GitHub website (https://github.com/)
2. Click on the "Sign up" button in the top right corner of the page.
3. Fill out the required fields (username, email, password) and click on the "Sign up for GitHub" button.
5. Verify your email address by clicking on the link sent to the email address you provided.

Once your email is verified, you can start creating repositories, contributing to other projects, and collaborating with others on GitHub.

# 3. Installing Git Bash

1. Go to the Git website (https://git-scm.com/) and download the version of Git Bash appropriate for your operating system by following the instructions on the page.
2. To check if Git has been succesfully downloaded, you can run the command **git version**.

If you are on Windows, you should download GitBash. On MacOS, downloading git should suffice as terminal can be used to access git.

For more instructions, check out the video on this topic and follow the step by step instructions set out.

# 4. Configuring Git

Before you can commit changes to the repository you need to have your username and email configured.

This can either be set in the scope of the repository you downloaded or set globally, so that it does not need to be configured for any other repository that you clone.

The information that you enter will get tied to the commit and this task doesn’t need to be repeated every time you want to make a commit. This can be done as follows:

```
git config --global user.name "Your Name"

git config --global user.email "your_email@example.com
```
where your email address is the email you used to create your github account.

Again, you need to do this only once if you pass the --global option, because then Git will always use that information for anything you do on that system. If you want to override this with a different name or email address for specific projects, you can run the command without the --global option when you're in that project.

5. Linking Git with GitHub

In order to push local changes on a repository (work done via Git Bash/Terminal) to its remote counterpart (corresponding GitHub repository), you would usually have to enter your GitHub credentials to ensure you are interacting with the correct repository.

Previous versions of Git required users to enter their username and password for every Git action performed which was not ideal.

To avoid having to enter credentials every time, Git is capable of using SSH keys instead of traditional password authentication when pushing or pulling to remote repositories. SSH keys are used to authenticate secure connections by identifying the user interacting with the Git remote repository.

Continue...
PAT
