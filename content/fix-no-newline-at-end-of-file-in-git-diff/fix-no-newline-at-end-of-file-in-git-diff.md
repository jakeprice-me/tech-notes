---
aliases:
  - fix-no-newline-at-end-of-file-in-git-diff
archive_links: 
category: git
classification: public
date: 2023-11-23T17:13:26
date_modified: 2023-11-23T17:13:26
draft: false
id: 20231123171326
image: 
links:
  - https://stackoverflow.com/questions/51957907/avoid-no-newline-at-end-of-file-in-git-diff
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - git
  - newline
  - diff
  - crlf
  - if
  - line-ending
  - noeol
title: Fix no newline at end of file in Git diff
type: tech-note
---

When you come across `\ No newline at end of file`, it's because the file you've edited had no proper line ending set (`LF` or `CRLF`), and you, having opened it with an editor that has proper line endings set, have added a line ending.

```sh
$ git diff
diff --git a/test.txt b/test.txt
index 6a8e276..54ff075 100644
--- a/test.txt
+++ b/test.txt
@@ -1 +1 @@
-This is the content of the file
\ No newline at end of file
+This is the content of the file
```

However, you'll often not want a change like this to show in a merge request because it distracts from the code and files that have genuinely been changed. So, I will usually set the file back to having no line ending, which is pretty simple to do.

In your editor, delete the last line of the file, then add it back, but use `echo -n`. The `-n` flag makes sure `echo` doesn't output a new line.

```sh
echo -n "<content-of-last-line>" >> file.txt
```

If you run `git diff` again you'll see the issue is resolved.

Alternatively if you use Vim, and notice `[noeol]` when you open the file, you can just `:set nofixendofline` and you won't have to faff about with the above!
