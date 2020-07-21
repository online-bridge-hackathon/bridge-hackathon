# Developers

## toolsets

## environment

## guidance
- (proposal) we use a common Commit Message Format, e.g. based on [Angular's version](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit-message-format)
- [mastering markdown](https://guides.github.com/features/mastering-markdown)

### productivity
- set up git [aliases](http://githowto.com/aliases)
-
### Branch and Release Management

The latest development code lives in the `master` branch. It should be the
primary branch for the repository. The primary branch will be the default branch
checked out when user does `git clone`. Pull requests are merged directly to the
`master` branch.

#### Public Testing Servers

We plan to set up GitHub actions to deploy all merges to the testing server.
Users are invited to test the latest changes on the testing server.  Volunteers
become our quality assurance team. They help us detect bugs before changes reach
the production servers.

#### Deployment to the Production Servers

The component lead tags the testing image with a production tag when they think
the testing deployment has had enough testing. The lead then deploys the new
production image to the production servers.

A goal (not yet implemented) is to deploy pulls automatically to production
following a "continuous deployment" process. This process requires a
comprehensive test suite and automated production health monitoring to keep
production reliable without a manual testing step.

### Development Work in a Personal Fork Repository

#### Cloning the Primary Repository

You can clone the primary repository normally. This document shows example
commands for this repository.

`git clone https://github.com/online-bridge-hackathon/bridge-hackathon.git`

#### Creating a Personal Fork

Go to the component page in the GitHub website. Click the *Fork* button in the top right-hand corner of the page. A dialog box will appear, asking where you want to create your fork. Click on your GitHib username. Once the process is complete, you’ll be taken to your forked copy of the repository.

#### Adding the Personal Fork as a remote

Git supports multiple remote repositories for a local working tree. The `git remote` command can be used to manage remote repositories. In most cases,
`git remote add` is the only command required. `git remote` commands must be run from a working directory inside a local repository created by `git clone`.

`git remote add personal https://github.com/<username>/bridge-hackathon.git`

URL is an example based on the default GitHub naming for a fork. You get the
repository URL for your fork from its GitHub repository page.

More details:
* [Adding a remote](https://docs.github.com/en/github/using-git/adding-a-remote)
* [Working with Remotes](https://git-scm.com/book/en/Git-Basics-Working-with-Remotes)

#### Creating a Development branch

You can create a new local branch from the latest code in the `origin/master`
remote branch. Basing a new development branch on the latest code makes merging
your changes easier.

```
git fetch origin
git checkout origin/master -b my_cool_new_feature
```

The commands create a new local branch called `my_cool_new_feature` based on the
`origin/master` remote branch.

#### Make All Commits Working (git bisect)

All commits should pass unit tests. Bugs will happen, but the test suite reduces
chance for a broken commit.

Why should all commits pass unit tests?

Bisect functionality can help locate a regression bug. Using `git bisect`
command can quickly find the first commit causing the bug. Bisect command uses a
binary search like algorithm to find the first broken commit. The algorithm is
modified to work well with a complex merge tree from many merges to the `master`
branch.

#### Making a Pull Request

It's time to make a pull request when your cool new feature is working, it has
comprehensive tests, all old and new tests pass, and the code has been committed
to your local branch. Pull request requires a new branch in the `personal`
remote. `git push` uploads a local branch to a remote repository.

`git push --set-upstream personal`

The command pushes the `my_cool_new_feature` to `personal/my_cool_new_feature`.
The `--set-upstream` argument updates the remote tracking information for the
local branch. The update branch state makes subsequent `git push` select
`personal/my_cool_new_feature` without any additional arguments.

The GitHub adds a helpful link to the push command message. The link opens the
pull request creation web page.

#### Making changes based on review comments

If the review process spots any issues then `git rebase -i` can be a useful
command. The `-i` argument tells rebase to use the interactive mode.
Interactive mode allows the author to modify new commits based on review
comments.

`git rebase -i origin/master`

The rebase would use the tracking branch as a default base. We updated the
remote tracking branch to follow the `personal/my_cool_new_feature` remote
branch. The rebase requires a base from the `master` branch. The `origin/master`
remote branch is often the preferred base commit for the rebase operation.

If changes belong to the latest commit in the branch then changes can be
staged using `git add` and committed using  `git commit --amend`. The `--amend`
argument makes git modify the latest commit in the local branch.

See more details about modifying history from
[Git Tools - Rewriting History](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)

#### Clean up after your changes are merged into the master branch

After you merge your pull, GitHub will give you the option to delete your branch
from the GitHub repository. Usually you will want to do so. Then, to delete your
local branch and bring all the latest changes into your local repository:

```
git checkout master
git branch -D my_cool_new_feature
git pull --ff-only

```
