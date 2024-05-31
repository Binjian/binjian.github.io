---
title: Git Basics
author: Binjian Xin
date: "2023-04-20T00:00:00+08:00"
draft: false
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

# Git Basics

Binjian Xin | 2023-01-12

---
Table of Contents

- [Git short introduction](#git-short-introduction)
- [Inside Git](#inside-git)
- [Under the hood](#under-the-hood)
- [More advanced](#more-advanced)

---
## Git short introduction {#git-short-introduction}

- 'Git' not 'Jit'
- days of diff and patch, bitkeeper
- linus torwald
- very similar to blockchain Merkle Tree (hash tree)
  [why is git not a blockchain](https://stackoverflow.com/questions/46192377/why-is-git-not-considered-a-block-chain)


---
## Inside Git {#inside-git}

- SHA is not a security feature, security is a by-product
- objects:
  blob, tree
- references:
  name for raw SHA-1 value; refs
- porcelan vs plumbing:
  git cat-file -t -p
- features:
  local, fast, efficient, distributed, snapshot not patches, changes
- HEAD/Detached?

---
### Workflow {#workflow}

- edit -&gt; stage(add) -&gt; review -&gt; commit
- git-flow
  - [git flow cheetsheet](https://danielkummer.github.io/git-flow-cheatsheet/index.zh_CN.html)

---
### submodule {#submodule}

- just update, track the new changes of the submodules (no change)
- manually : git fetch
- automatically: git submodule update --remote
  - set specific branch .gitmodules submodule.submudle_name.branch stable
  - -f: tracked; no -f locally, not tracked.
  - git config status.submodulesummary 1

---
### Cooperative submodule {#cooperative-submodule}

- git submodule update --remote --rebase/--merge
- caveats: has to commit locally.
- publishing submodule changes: git push --recurse-submodules=check/on-demand
- caveats:
  - accidental revert: git submodule update --remote to update .gitmodule; and commit in parent projects.
  - cannot merge: no submodule merge

---
## Under the hood {#under-the-hood}

- index/stage, repository, working tree, remote;
- plumbing:
  - git hash-object -w;
  - git cat-file -p/-t;
  - git update-index --add --cacheinfo
- file modes: 100644/100755/120000
- git write-tree

---
### objects {#objects}

- Git is content-addressable filesystem
  - tree objects
  - blob
  - [commit objects](https://git-scm.com/book/en/v2/Git-Internals-Git-Objects)
  - tag

---
### commit {#commit}

- Git commit: is a snapshot
  - Commit often!
    - history of your logic units of change
    - a story of history of the repository
- metadta: contents, messages of author, timestamp,
- change history, --amend

---
### reference {#reference}

- branch, HEAD, detached
  - branch: reference to the head of a line of work--&gt;git update-ref refs/heads/master
  - HEAD: symbolic reference (pointer to a reference); or SHA-1 value of a git object
  - detatched HEAD: cannot commit (checkout a commit/tag/remote branch)
    - to save : git checkout -b foo/ git branch foo/ git tag foo

---
### advanced reference {#advanced-reference}

- git reflog -2 HEAD/ HEAD^^
- git symbolic-ref
- master^^
- tags： branch reference; never moves

---
### remote {#remote}

- git remote add origin git@gitlab.work:ai/ref.git
- git push
- merge
- rebase
- stashing
- log

---
### misc {#misc}

- commit amend
- rename
- gitignore
- submodule,

---
## More advanced {#more-advanced}

- git revert
- git revision specification for
  - git log
  - git reset
  - git chery-pick
- git rebase
- A beautiful magit
