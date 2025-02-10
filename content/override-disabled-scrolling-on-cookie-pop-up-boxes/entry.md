---
aliases:
  - override-disabled-scrolling-on-cookie-pop-up-boxes
category: css
classification: public
date: 2024-06-05T11:00:34
date_modified: 2024-06-05T11:00:34
draft: false
id: 20240605110034
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - cookie
  - css
  - modal
  - override
  - pop-up
title: Override Disabled Scrolling on Cookie Pop-up Boxes
type: tech-note
---

I save lots of web-pages using [SingleFile](https://github.com/gildas-lormeau/SingleFile) so I always have a copy, but some pages retain a pop-up cookie or other kind of pop-up. You can remove these easily enough from the saved HTML, but sometimes you still can't scroll.

I insert the below CSS snippet into the saved HTML (anywhere within the `<head></head>` tags) and this usually overrides the stupid lack of scrolling.

```css
<style>
	body {
	    overflow: auto !important;
	}
</style>
```