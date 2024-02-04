---
aliases:
  - merge-multiple-pdfs-into-one-pdf
archive_links: 
category: miscellaneous
classification: public
date: 2024-02-04T15:06:06
date_modified: 2024-02-04T15:06:06
draft: false
id: 20240204150606
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - pdf
  - merge
  - poppler-utils
  - pdfunite
title: Merge Multiple PDF's into One PDF
type: tech-note
---

Merge PDF's into one PDF.

Install `poppler-utils`.

```sh
sudo dnf install poppler-utils
```

Then merge away.

```sh
pdfunite file1.pdf file2.pdf file3.pdf merged.pdf

# or

pdfunite * merged.pdf
```
