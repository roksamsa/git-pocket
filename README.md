
# Git Pocket Guide

Git pocket guide for busy people

**Definition:** Git is a distributed revision control system.

**Purpose:** Keep track of software revisions and files changes.

Git must be installed in local computer to generate revisions, then revisions are saved to a remote [distributed](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows) repository. This repository can be a private server, or an online service like github. Team developers will push (and pull) revisions to (and from) that remote.

Hosted services:

- [github.com](https://github.com) Good for open source projects with comminity collaboration
- [beanstalkapp.com](http://beanstalkapp.com/) Good for private projects with built-in deploy system
- [bitbucket.org](https://bitbucket.org/) Good for free private projects

## TOC (table of contents)

**Use “$” symbol to search thru the document**

- [$setup](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#setup)
- [$gibberish](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#gibberish)
- [$getting-started](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#getting-started)
- [$clone](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#clone)
- [$commit](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#commit)
- [$push](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#push)
- [$remote](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#remote)
- [$fetch-pull](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#fetch-pull)
- [$branch](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#branch)
- [$status](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#status)
- [$diff](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#diff)
- [$tag](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#tag)
- [$update](https://github.com/heyallan/git-pocket/blob/gh-pages/README.md#update)

## $setup

Set Up Git guide: https://help.github.com/articles/set-up-git/

## $gibberish 

| Keyword | Description |
|-------|-------------|
| `Working directory` | Actual files on current directory |
| `Index` \| `Staging area` | Snapshot of changes set aside to be commited |
| `SHA-1`             | Unique identifier repesenting history information |
| `blob`              | Represents a file  |
| `tree`              | Represents a directory of files |
| `Commit`            | Represents a tree as recorded in a point in time  |
| `HEAD`              | Represents the latest commit in current branch  |
| `Tag`               | Represents a specific commit used for marking important points in hisotry |


## $getting-started

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git config`  | `--global user.name "Cooper Black"`    | Set global user name |
| `git config`  | `--global user.email "cooperblack@email.com"`    | Set global user email |
| `git config`  | `--list`    | Display configuration |
| `git init`    |             | Make current directory a git repository |
| `git remote`  | `add origin <url>`| Set remote origin |

Reference: https://git-scm.com/docs/git-config

## $clone

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git clone`   | `<giturl>`  | Clone remote repository into current directory |
| `git clone`   | `--recursive <giturl>`  | Clone remote repository with submodules |
| `git submodule` | `update --remote` | Update submodules |

Reference: https://git-scm.com/docs/git-clone

## $commit

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git add`         | `<file> | <path>`   |  Add files to staging area  |
| `git commit`      | `-m "<title>" -m "<body>"`  |  Commit with message (includes "added" files only) |
| `git rm`          | `<file> | <path>`   |  Remove files from the working tree and from the index |
|                   | `-f`                |  Force deletion of files from disk |

Reference: https://git-scm.com/docs/git-commit

## $push

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git push`    | `--d origin <branchname>` | `--delete` remote branch |
| `git push`    | `-u origin --all`| Push all branches to remote |
| `git push`    | `-u origin --tags`| Push all tags to remote |

Reference: https://git-scm.com/docs/git-push

## $remote

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git remote`     | `-v`     | List remote connections (or `git branch -r`) |
| `git remote add`     | `<name> <url>`     | Create namespace connected to remote repo |
| `git remote rename`     | `<oldname> <newname>`     | Rename connection |
| `git remote rm`     | `<name>`     | Remove connection |

- Remote connections are more like named bookmarks rather than direct links to other repos
- `git clone` automatically creates a remote connection often called `origin`
- Reference: https://git-scm.com/docs/git-remote

## $fetch-pull
| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git fetch`     | `<remote>`     | Fetch all branches from remote (without merge) |
| `git fetch`     | `<remote> <branch>`     | Fetch specific branch |
| `git merge`     | `<remote>/<branch>`     | Merge fetched remote |
| `git pull`      | `<remote>`     | Fetch and merge in one command |

Reference: https://git-scm.com/docs/git-fetch, https://git-scm.com/docs/git-pull


## $branch

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git branch`        |                   | List branches |
| `git branch`        | `<branchname>`    | Create new branch |
| `git checkout`      | `<sha-1>`         | Switch to branch, or commit |
| `git branch`        | `-m <branchname> <newname>` | Rename branch |
| `git merge`         | `<branchname>`    | Merge changes from `<branchname>` to current branch |
| `git branch`        | `-d <branchname>` | `--delete` branch |
| `git push`          | `<remote> <branch>`     | Push the specified <branch> to <remote> |
| `git push`          | `<remote> --all`     | Push all branches to <remote> |

Reference: https://git-scm.com/docs/git-branch

## $status

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git status`  | `-s`        | Show the working tree status, with `--short` format |
| `git log`     | `--oneline` | Show commit logs, with `--oneline` format |
| `git ls-files`|             | Show information about files in the index and the working tree |

Reference: https://git-scm.com/docs/git-status

## $diff

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git diff`  |             | Compare **`working directory`** and **`index`** |
|             | `–-cached`  | Compare **`index`** and **`latest commit`** |
|             | `HEAD`      | Compare **`latest commit`** and **`working directory`** |
|             | `--stat`    | Optional short format |
|             | `<sha-1> <sha-1>` | 2 points in time to compare |
|             | `<dir> | <file>` | Compare whole directory or limit to file |

Reference: https://git-scm.com/docs/git-diff

**Examples:**

```shell
## compare changes made to README.md between working tree (default) and latest commit (HEAD)
$ git diff --stat HEAD ./path/README.md

## compare changes made to README.md between 2 specific points in time (e.g. 2 commits)
$ git diff --stat a649900 24bdd58 ./path/README.md
```

## $tag

| Command     | Options     | Description |
|-------------|-------------|---------------------------------------------------------|
| `git tag`           |                   | List tags |
| `git tag`           | `<v1.0.0>`        | Create tag, from latest commit, lightweight |
| `git tag`           | `-a <v1.0.0> -m "<msg>"` | Create tag, with `--annotate`, from latest commit |
| `git tag`           | `-a <v1.0.0> -m "<msg>" <SHA-1>` | Create tag, with `--annotate`, from specific commit |
| `git tag`           | `-d  <v1.1.0>`    | `--delete` tag |
| `git show`          | `<v1.0.0>`        | Show tag data and message |
| `git checkout`      | `<v1.0.0>`        | Switch to specific point tag (not editable) |
| `git push`          | `<remote> --tags`     | Push all tags to `<remote>` |
| `git push`          | `<remote> <tag>`     |  Push specific tag to `<remote>`  |

Reference: https://git-scm.com/docs/git-tag

## $update

How to update git: https://github.com/heyallan/git-update
