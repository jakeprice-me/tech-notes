---
alias: privacy-redirect-bookmarklet
category: javascript
classification: public
date: 2023-05-10 21:25:40
date_modified: 2023-05-10 21:25:40
id: 20230510212540
link: 
link_archive: 
pinned: false
series: 
tags: [bookmarklet, javascript, chrome, firefox, nitter, twitter, reddit, libreddit]
title: Privacy Redirect Bookmarklet
type: tech-note
uuid: 35ff9113-634a-424d-bb83-1ad22b8f064b
---

A bookmarklet that can be used to open the current Twitter or Reddit page in my self-hosted [Nitter](https://github.com/zedeus/nitter) or [Libreddit](https://github.com/libreddit/libreddit) instances.

I use Firefox on Desktop, so use [Privacy Redirect](https://addons.mozilla.org/en-US/firefox/addon/privacy-redirect/), but I use Chromium based browsers on Android (Brave), so I needed a quick and simple solution.

Simply bookmark any page in Brave/Chromium/Chrome then edit the bookmark's name to something like "Open in Nitter" and paste the below javascript into the URL field (obviously making sure to replace `<URL-GOES-HERE>` with a real URL.

```javascript
javascript:(function(){window.location.href="<URL-GOES-HERE>" + window.location.pathname + window.location.search + window.location.hash;})()
```

To use the bookmarklet, whilst on a Twitter or Reddit page click the address bar and type to find the bookmarklet, and then click it. It should open the page in Nitter or Libreddit. It won't work if you click the bookmark from the Bookmarks manager (don't know why).