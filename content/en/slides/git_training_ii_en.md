---
title: Fluent Git
author: Binjian Xin
date: "2023-09-18T00:00:00+08:00"
draft: false
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

# Fluent Git

Binjian Xin | 2023-09-18

---

Table of Contents

- [Common Scenarios](#common-scenarios)
- [Hash Value, Four Types of Objects](#hash-value-four-types-of-objects)
- [Tools and Operations in Typical Scenarios](#tools-and-operations-in-typical-scenarios)

---
## Common Scenarios {#common-scenarios}

{{< figure src="/ox-hugo/git.png" >}}

---
### An Example of Submodule {#an-example-of-submodule}

---
#### Porcelain Commands {#porcelain-commands-submodule}

- Consult the manual:

  ```bash
          git submodule foreach --recursive 'git log'
  ```

- Debugged:

  ```bash
          git submodule foreach --recursive 'git log --oneline'
  ```

- More functions:
  ```bash
          git submodule foreach --recursive 'git log --oneline HEAD...HEAD~5'
  ```

---
#### Plumbing Commands {#plumbing-commands-submodule}

- Stack overflow:

```bash
        git submodule foreach --recursive '
        REV1=HEAD;
        REV2=HEAD~10;
        SHA1=$(cd $toplevel && git ls-tree $REV1 $sm_path | \
            grep -E -o "[0-9a-f]{40}");
        SHA2=$(cd $toplevel && git ls-tree $REV2 $sm_path | \
            grep -E -o "[0-9a-f]{40}");
        git log --oneline $SHA1...$SHA2'
```

- Debug:

```bash
        git submodule foreach --recursive '
        SHA1=$(cd $toplevel && cd $sm_path && git log | \
            grep -E -o "[0-9a-f]{40}" | head -1);
        SHA2=$(cd $toplevel && cd $sm_path && git log | \
            grep -E -o "[0-9a-f]{40}" | head -10 | tail -n1);
        git log --oneline $SHA1...$SHA2'
```

{{< speaker_note >}}

Git submodule is a not-so-useful feature! Look at opencv, ros

- git submodule update -&gt; no branch
- Submodule tracking branch needs to be configured
- Pushing order with main repo (has the responsibility to set the branch and version it tracks, and it's static, unless configured in main repo)

Without knowing the internals, like learning chemistry without knowledge of atomic physics.
Learning deeper is smart, not learning wider! Learning wider is memorization, computers can better!
No magic! Magic is when you don't understand! Magic is accompanied with fear! Important to have an image (einstein) -&gt; git-sim as a tool

{{< /speaker_note >}}

---

#### Types of Porcelain Commands {#types-of-porcelain-commands}

- Git commandline
- Git lens
- Gitkraken
- Emacs magit

---

## Hash Value, Four Types of Objects {#hash-value-four-types-of-objects}

---

### Hash (Dark Matter in the Computer World) {#hash-dark-matter}

- Efficient
  - Fast hash function calculation, index ~O(1) (array O(N))
  - Very low probability of collision, worst case O(N)
- sha-1(20byte, 40hex, 160 bits, 8 bits for directory)
  - Higher security -> sha256(32bit), sha512(64bit) 
  - $2^{160}\approx 3\times 10^{38}$(Total number of atoms in the universe $\approx 10^{80}$)
- Wide application of hash tables
  - Programming language data structures: Python dict(json),set
  - Databases: Mongodb object
  - Cloud storage: Object Storage System

{{< speaker_note >}}

Hash values are the dark matter of computer technology
- Efficient
  - Hash function calculation, a few hundred milliseconds per million calculations
  - Index ~O(1) (array O(N))
  - Very low probability of hash collision, worst case O(N)
- sha-1 (20byte, 40hex, 160 bits, 8 bits for directory)
  - Security -&gt; sha256(32bit), sha512(64bit), ipv6 is 4.2 billion times more
  - ipv6 128bit \\(2^{128}\\) 79x10<sup>27</sup> (Total number of atoms in the universe wiki \\(\approx10^{80}\\), number of atoms in the human body \\(\approx7\*10^{27}\\), number of stars \\(\approx200\times10^{21}\\))
- Wide application of hash tables
  - Programming language data structures: Python dict (json) and set, (excluding list and tuple)
  - Databases: Mongodb object
  - Cloud storage: Object Storage System
{{< /speaker_note >}}

---

### Four Objects {#four-objects}

- Tree (spatial/topological relationship)
- Blob file
- Commit (time order)
- Annotated tag
- Tree object, file object instance: HEAD,
  - git cat-file -p HEAD
  - git ls-tree -r HEAD
  - A file object inside HEAD

---

### Power of Abstraction {#power-of-abstraction}

- Content-addressable file system/database
- All objects are equal, no priority

---

### Version Selection Git Revisions {#version-selection-git-revisions}

- Applied to cherry-pick, reset, log, merge
- Specific single version
  - head^^/head^2
  - head@{2}
  - head~~/head~2

---

#### Version Range {#version-range}

- master..experiment (from master to experiment): D, C
- master A ^experiment (from experiment to master or feature): F, E
- master...experiment (from master to experiment or vice versa): F,E,D,C
- @: HEAD

{{< figure src="/ox-hugo/double-dot.png" >}}

---

#### Version Relationship Syntax {#version-relationship-syntax}

{{< figure src="/ox-hugo/loeliger.png" caption="<span class=\"figure-number\">Figure 1: </span>Multi-branch Version History" >}}

---
| A   |      | A^0     |        |       |
| --- | ---- | ------- | ------ | ----- |
| B   | A^   | A^1     | A~1    |       |
| C   |      | A^2     |        |       |
| D   | A^^  | A^1^1   | A~2    | B^1   |
| E   | B^2  | A^^2    |        |       |
| F   | B^3  | A^^3    |        |       |
| G   | A^^^ | A^1^1^1 | A~3    | D^1   |
| H   | D^2  | B^^2    | A^^^2  | A~2^2 |
| I   | F^   | B^3^    | A^^3^  |       |
| J   | F^2  | B^3^2   | A^^3^2 |       |

---

#### Range Selection Syntax 1 {#range-selection-syntax-1}

{{< figure src="/ox-hugo/loeliger.png" caption="<span class=\"figure-number\">Figure 2: </span>Multi-branch Version History" >}}

---
Version range syntax

| Input   | Decomposition | Result        |
| ------ | ---- | ----------- |
| D      |      | G H D       |
| D F    |      | G H I J D F |
| ^G D   |      | H D         |
| ^D B   |      | E I J F B   |
| ^D B C |      | E I J F B C |
| C      |      | I J F C     |
| B..C   | ^B C | C           |

---

#### Range Selection Syntax 2 {#range-selection-syntax-2}

{{< figure src="/ox-hugo/loeliger.png" caption="<span class=\"figure-number\">Figure 3: </span>Multi-branch Version History" title="Sutskever 2015" width="400pix" >}}

---
| B...C       | B ^F C       | G H D E B C |
| ----------- | ------------ | ----------- |
| B^- (merge) | B^..B        |             |
|             | ^B^1 B       | E I J F B   |
| C^@         | C^1, F       | I J F       |
| C^!         | C ^C^@, C ^F | C           |
| F^! D       | F ^I ^J D    | G H D F     |

---

## Tools and Operations in Typical Scenarios {#tools-and-operations-in-typical-scenarios}

---

### Simulated Scenarios and Countermeasures (Undo Button) {#simulated-scenarios-undo-button}

- Create a feature branch in an existing code repository
- Add changes (git add)
- Commit changes (git commit)
- Undo the most recent commit change (git commit, immediately regret)
- Undo a long string of changes (undo after multiple commits on a branch, reset)
- Undo the remote repository (undo after git push to everyone)
- Change the entire branch (git rebase)
- Commit changes on the wrong branch (push the relevant changes to the correct branch, cherrypick)
- Brainstorm!

---

### Conventional Application Commands {#conventional-application-commands}

- git branch (off, out): Add changes
- git commit -a: Undo recent changes, git push -f option.
- git reset
  - soft, **mixed**, hard
    If hard is cleaner, why is mixed the default option?
  - hard is very dangerous (detached/isolated commit, no undo button!)
  - soft, mixed are more conservative, defensive rollback
- git remote
  - Can it correspond to multiple remote repositories? For example, ros's github repository and company intranet have special configurations

---

### Complex Commands {#complex-commands}

- git rebase
  - git push --force (no undo button!)
  - git merge

---

### Git Reflog Perspective {#git-reflog-perspective}

- Head branch history (head &amp; branches)

