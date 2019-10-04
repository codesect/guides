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

This will create a new folder with all the content.

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

> Tip: Don't forget to add a descriptive name to your new branch. For example, if you're working on a new hero section, you can name it `feature/hero-section`, or if you're fixing links on the header, your new branch name can be `fix/header-nav`.

<p align="center">
  <img src="images/git-checkout-b.gif?raw=true" alt="" />
</p>

## Make Your Changes

Once you have made the necessary changes and/or added new features, you need to add the changed and new files to the staging area, preparing them to be included in your next commit.

To add every changes, type:

```bash
git add .
```

It's time to make a "snapshot" and record the changes that you made to the repository. Commits can be thought of as milestones along the timeline of a `git` project.

To make a commit, type:

```bash
git commit -m '<Your commit message>'
```

> Tip: Keep your commit message short and clear. It should be no longer than 60-70 characters.

<p align="center">
  <img src="images/git-commit.gif?raw=true" alt="" />
</p>

## Push Changes and Avoid Conflicts

It's time to push your changes. But don't forget, you're working in teams. There is a chance that the `master` branch has been updated by someone else while you made your changes. You need to update your branch from the `master` branch.

```bash
# switch to the master branch
git checkout master
# git pull fetches the new commits from GitHub
# and merges these into your local master branch
git pull
# switch back to the branch you worked on
git checkout <your branch name>
# merge new commits from master
git merge master
```

To push changes from your local repository to the remote repository, type:

```bash
git push origin <your branch name>
```

<p align="center">
  <img src="images/git-push.gif?raw=true" alt="" />
</p>

## How to solve a Merge Conflict

Merge conflicts occur when competing changes are made to the same line of a file, or when one person edits a file and another person deletes the same file.

To resolve a merge conflict caused by competing line changes, you need to choose which changes you want to incorporate and make a new commit.

The merge conflict error will be shown to you when you try to merge two branches and the aforementioned competing changes exist.

You can solve the conflict like this:

1. Navigate to the repository with the conflict in your terminal.

2. Check which files are affected with the git status command.

```bash
$ git status
> # On branch branch-b
> # You have unmerged paths.
> #   (fix conflicts and run "git commit")
> #
> # Unmerged paths:
> #   (use "git add ..." to mark resolution)
> #
> # both modified:      styleguide.md
> #
> no changes added to commit (use "git add" and/or "git commit -a")
```

3. Open the conflicted file in a text editor.

4. To see the beginning of the merge conflict in your file, search the file for the conflict marker <<<<<<<. When you open the file in your text editor, you'll see the changes from the HEAD or base branch after the line <<<<<<< HEAD. Next, you'll see =======, which divides your changes from the changes in the other branch, followed by >>>>>>> BRANCH-NAME. In this example, one person wrote "open an issue" in the base or HEAD branch and another person wrote "ask your question in IRC" in the compare branch or branch-a.

```bash
If you have questions, please
<<<<<<< HEAD
open an issue
=======
ask your question in IRC.
>>>>>>> branch-a
```

5. Decide if you want to keep only your branch's changes, keep only the other branch's changes, or make a brand new change, which may incorporate changes from both branches. Delete the conflict markers <<<<<<<, =======, >>>>>>> and make the changes you want in the final merge.

6. Add and commit your changes.

Now you can push your changes to your remote repository.

## Create a Pull Request

Once you pushed your working branch, you need to make a pull request against `master`. by visiting the repo's GitHub page and clicking on the green `Compare and pull request` button:

<p align="center">
  <img src="images/git-pull-request.gif?raw=true" alt="" />
</p>

Time to celebrate 🎉 You did it! Now, you need to wait for one of your teammates to review your code and merge your pull request.

Happy coding! 💪
