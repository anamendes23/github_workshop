# GitHub Workhop

This workshop has the goal to help beginnings to practice most used Git commands using Git Bash.

## Disclaimer

These workshop practices Git commands that I used often at my job, they do not cover all the Git commands.
I wrote the workshop based on my own preferences. There could be a better way to do this and I'd appreciate any feedback to improve this workshop.
The intent is to help fellow first-time interns to have more confidence using Git at work.
Hope this helps! 😄

## Contents

- [Getting Started](#getting-started)
  - [Download Git Bash](#download-git-bash)
    - [Windows](#windows)
    - [Linux or MacOS](#linux-or-macos)
  - [Configure Git](#configure-git)
  - [Workshop Setup](#workshop-setup)
  - [Start the Workshop](#start-the-workshop)

***
## Getting Started

Before starting the workshop, follow the next steps to set up the development environment.

### Download Git Bash

#### Windows

If using Windows, it will be easier to use Git Bash - [download here](https://git-scm.com/downloads).

#### Linux or MacOS

If using either Linux or MacOS, then use the built-in shell. Make sure Git is already installed, otherwise here are some [instructions](https://phoenixnap.com/kb/install-git-on-mac#:~:text=%20Option%201%3A%20Install%20Git%20on%20Mac%20with,and%20double-click%20to%20open%20the%20Git...%20More%20).

### Configure Git

Before being able to collaborate, Git needs to know the user information (name and email). It is possible to have different configurations for different git repositories, but for now let's use the global configuration.

Open the terminal (shell or Git Bash) and run this command to add user name:\
`git config --global user.name <your_github_username>`

Then run this command to add user email:\
`git config --global user.email <your_email@mail.com>"`

## Workshop Setup

Clone the workshop repository. If cloning a different repositoriy, change the url below.\
`git clone https://github.com/anamendes23/github_workhop.git`

Make a copy of `Template.md` and rename it. Now let's push the changes to GitHub with the following commands:\
`git status # shows current branch changes`

You should see the new file path in green (new file added).
Since we want to stage all files, we can use the shortcut:\
`git add .`

Or we can add specific files one at a time:\
`git add <file path> # here it's helpful to use tab to autofill the path`

With files staged, we can now make a commit:\
`git commit -m "Copied workshop Template file to MyFile.md"`

The `-m` flag is used to add a commit message inline. If you use:\
`git commit`

Then your default editor will open so you can add a message. The most used terminal editors are Vim and Emacs. Here I'll add some Vim commands:
In Vim, press `i` to start editing. Use arrows to navigate lines.

Type your commit message on the first line. When done, press `Escape` and `:qw` to save your changes and close the editor.

Now you have a local commit, we have to send the changes to the remote repository (in GitHub). To do so, use the command:\
`git push origin <branch name> # for now, <brach name> should be main`

## Start the Workshop

Now that you've made a copy, you can use your file to work through the workshop steps.
It will be more fun to do this with a friend, but you can also easily learn the commands by yourself.
