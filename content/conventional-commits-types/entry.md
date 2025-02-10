---
aliases:
  - conventional-commits-types
category: git
classification: public
date: 2023-07-04T15:11:26
date_modified: 2023-07-04T15:11:26
draft: false
id: 20230704151126
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - conventional-commits
  - git
  - type
title: Conventional Commits Types
type: tech-note
---

I _hate_ [Conventional Commits](https://www.conventionalcommits.org). It actively makes me want to avoid committing regularly so I don't have to think of a commit "type" that fits within the philosophy.

I suppose that will change if I use it more... but regardless, the below breakdown from a ChatGPT message helped a lot. I don't understand why the Conventional Commits website is so vague on details on what it's types mean, because it's not immediately obvious (some like `style` and `chore` can feel to me at least, like they could both be used, and that just introduces ambiguity which just adds to the above frustrations).

- feat: The commit introduces a new feature to the codebase or application.
- fix: The commit addresses a bug or issue in the codebase, resolving it.
- docs: The commit involves documentation changes, such as updating README files or adding inline comments.
- style: The commit makes cosmetic changes to the codebase, like formatting, whitespace, or code style improvements. These changes do not affect the code's functionality.
- refactor: The commit involves code refactoring, i.e., restructuring or optimizing existing code without adding new features or fixing bugs.
- test: The commit adds or modifies tests or test-related code, ensuring the codebase's integrity and quality.
- chore: The commit includes changes to build processes, development tools, or other miscellaneous tasks not directly related to code functionality.
- perf: The commit improves the performance of the codebase or optimizes certain operations.