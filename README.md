# Databricks Git Practice

This is a personal, hands-on learning repository for Git, GitHub, and the Git workflow used around Databricks projects. The `src` directory is organized by topic and contains screenshots, small practice files, and one simple HTML page. The material is intended for learning and revision rather than as a production application.

## What This Repository Covers

- Creating and configuring a local Git repository.
- Staging, committing, and reviewing changes.
- Branching, merging, and handling conflicts.
- Cloning repositories and working with remotes.
- Temporarily storing work with stash.
- Inspecting history with log and locating changes with bisect.
- Marking versions with tags and moving selected commits with cherry-pick.
- Protecting local environment values with `.gitignore`.
- Understanding a practical Git workflow from edit to push.

## Repository Map

```text
Databricks/
├── README.md                 Project guide and file descriptions
├── fix.txt                   Short local practice note
├── .gitignore                Excludes the .env file
└── src/
	├── basic-commandas/      Basic command examples
	├── cherry-pick/           Cherry-pick practice
	├── Databricks-Link/      HTML demo and related screenshot
	├── Git-workflow/         End-to-end workflow screenshots
	├── git tag/              Tagging examples
	├── git-Config/           Configuration example
	├── git-add/              Staging example
	├── git-bisect/           Bisect example
	├── git-branch/           Branch example
	├── git-clone/            Clone example
	├── git-init/             Repository initialization example
	├── git-log/              History example
	├── git-stashing/         Stash examples
	├── gitignore/            Ignore-rule examples
	└── merge-conflict/       Conflict-resolution example
```

## Complete File Guide

The files below are the current contents of `src`. Image files are visual records of commands or results; they do not need to be executed.

| Topic | Files | Explanation |
| --- | --- | --- |
| Basic commands | `branch.png`, `git-add..png` | Visual examples of branch and staging commands. |
| Cherry-pick | `cherry-pic.png`, `image.png` | Practice material for selecting and applying one commit. |
| Databricks link | `index.html`, `Databricks_link_Github..png` | A browser-openable HTML page and its related visual reference. |
| Git workflow | `image.png`, `Work-flow.png` | Screenshots showing the general edit, stage, commit, and share cycle. |
| Tags | `git-tag.png`, `image.png`, `tag.png` | Examples of creating or inspecting Git tags. |
| Configuration | `image.png` | Screenshot related to Git configuration settings. |
| Git add | `git-add..png` | Screenshot showing a file being added to staging. |
| Git bisect | `bisect.png`, `image.png` | Visual notes for finding a problematic commit. |
| Git branch | `branch.png`, `image.png` | Examples of branch operations. |
| Git clone | `image.png` | Screenshot showing repository cloning. |
| Git init | `git init.png` | Screenshot showing repository initialization. |
| Git log | `image.png` | Screenshot showing commit history. |
| Git stashing | `git-stashing.png`, `image.png`, `status.png` | Examples of saving work temporarily and checking status. |
| Gitignore | `.gitignore.png`, `commit .gitignore .png` | Visual examples of ignore rules and committing the ignore file. |
| Merge conflict | `dummy.text`, `image.png` | A practice text file and visual conflict-resolution material. |

## Getting Started

### Requirements

- [Git](https://git-scm.com/downloads)
- A code editor such as [Visual Studio Code](https://code.visualstudio.com/)
- A GitHub account for remote repository practice

Verify Git and set your identity once:

```bash
git --version
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### Clone the Repository

```bash
git clone https://github.com/avinash4tripathi/git-practice.git
cd git-practice
```

Open the `src` folders in VS Code to review the screenshots. Open [`src/Databricks-Link/index.html`](src/Databricks-Link/index.html) in a browser to view the HTML file.

## Practice Workflow

Use a small test repository while practicing each topic:

```bash
mkdir git-learning-test
cd git-learning-test
git init
git status
git add .
git commit -m "Start practice"
```

For normal project work, the common sequence is:

```bash
git status
git add path/to/file
git diff --staged
git commit -m "Describe the change"
git pull --rebase origin main
git push origin main
```

### Branches and Stash

Use a branch for independent work and stash unfinished edits when you need to switch tasks:

```bash
git switch -c feature/example
git stash push -m "Work in progress"
git switch main
git switch feature/example
git stash pop
```

### Conflicts, Tags, and Cherry-pick

When a merge conflict occurs, inspect the files reported by `git status`, choose the correct final content, remove conflict markers, and complete the merge:

```bash
git add resolved-file
git commit -m "Resolve merge conflict"
```

Tags identify important snapshots, while cherry-pick applies one existing commit to the current branch:

```bash
git tag v1.0.0
git push origin v1.0.0
git cherry-pick <commit-id>
```

## Learning Sequence

1. Start with `git-init`, `git-Config`, and `git-add`.
2. Continue with `basic-commandas`, `git-log`, and `git-branch`.
3. Practice `git-stashing` and `gitignore`.
4. Explore `git-clone` and `Git-workflow`.
5. Finish with tags, cherry-pick, bisect, and merge conflicts.

After each topic, repeat the operation in a disposable test repository and inspect the result with `git status` and `git log --oneline`.

## Notes

Local environment files such as `.env` are excluded from version control. Never commit passwords, API keys, access tokens, or other credentials. If a secret is accidentally pushed, revoke or rotate it immediately.