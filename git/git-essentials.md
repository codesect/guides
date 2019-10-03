# Git Essentials

`git` is one of the most popular version control systems for tracking changes in source code during development.

Real-life projects have multiple developers working in parallel so a version control system is needed to ensure they can work without interfering with each other, and without fear of losing any changes made by other developers.

## Install Git on Your Computer

Digital Ocean has a nice tutorial on how to install `git`: https://www.digitalocean.com/community/tutorials/how-to-contribute-to-open-source-getting-started-with-git

## Tools

There are different ways to use `git`; the original command line tool and many GUIs, like [GitKraken](https://www.gitkraken.com), [SourceTree](https://www.sourcetreeapp.com/), [Tower](https://www.git-tower.com), etc.

If you're not familiar with the terminal or console, you can also use editors like [VSCode](https://code.visualstudio.com/) which has integrated source control and [includes Git support](https://code.visualstudio.com/docs/editor/versioncontrol) in-the-box.

## Clone Your Team's Repo

Once you're added to your team's repo, you can create a clone or copy of it. On the repo's main page there is a green `Clone or download` button. Once you click the button, you'll be able to copy the URL by clicking the clipboard button next to the URL.

Head over to your terminal/console and type:

```bash
git clone <URL you copied above>
```

<p align="center">
  <img src="images/git-clone.gif?raw=true" alt="" />
</p>

Now that you have a copy of the code, you can create a new branch on which you can work with the code.

## Work on Branches

Your default branch is named `master`. You should never push anything to it directly to keep it clean.

Having different branches will help you manage the workflow, isolate your code, and control what features make it back to the master branch.

Whenever you create a branch, it's important that you create your new branch off of the `master` branch.

To create a new local branch and switch to it, type:

```bash
git checkout -b <your new branch name>
```

Tip: Don't forget to add a descriptive name to your new branch.

<p align="center">
  <img src="images/git-checkout-b.gif?raw=true" alt="" />
</p>

## Make Your Changes

Once you have made the necessary changes and/or added new features, you need to add the changed and new files to the staging area, preparing them to be included in the next commit.

To add every changes, type:

```bash
git add .
```

It's time to make a "snapshot" and record the changes that you made to the repository. Commits can be thought of as milestones along the timeline of a `git` project.

To make a commit, type:

```bash
git commit -m '<Your commit message>'
```

Tip: Keep your commit message short and clear.

<p align="center">
  <img src="images/git-commit.gif?raw=true" alt="" />
</p>

## Push Changes

To push changes from your local repository to the remote repository, type:

```bash
git push origin <your new branch name>
```

<p align="center">
  <img src="images/git-push.gif?raw=true" alt="" />
</p>

## Create a Pull Request

Once you pushed the changes, it's possible to make a pull request to the original repository by visiting the repo's GitHub page and clicking on the green `Compare and pull request` button:

<p align="center">
  <img src="images/git-pull-request.gif?raw=true" alt="" />
</p>
