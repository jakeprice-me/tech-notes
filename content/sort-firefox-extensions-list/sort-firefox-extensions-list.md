---
aliases:
  - sort-firefox-extensions-list
category: firefox
classification: public
date: 2023-06-16T16:49:30
date_modified: 2024-09-23T16:52:18
draft: false
id: 20230616164930
image: 
links:
  - https://raw.githubusercontent.com/icpantsparti2/browser-bits/main/javascript/firefox-v109-change-order-under-extensions-button.js
  - https://github.com/icpantsparti2/browser-bits
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - firefox
  - extensions
  - javascript
  - addon
title: Sort Firefox Extensions List
type: tech-note
---

Follow the below steps to sort your extension list (jigsaw icon) in Firefox until they have a way to sort it automatically (thanks to [this script](https://raw.githubusercontent.com/icpantsparti2/browser-bits/main/javascript/firefox-v109-change-order-under-extensions-button.js)).

1. Open `about:addons`
2. Open the web console
3. Copy and paste the below code into the console and run it.

```js
javascript:AddonManager.getAddonsByTypes(["extension"]).then(addons=>{var order=[];addons.sort((a,b)=>{return a.name.localeCompare(b.name);}).forEach(addon=>{if(!(addon.isBuiltin||addon.isSystem)){order.push(`"${addon.id.toLowerCase().replace(/[{}@.]/g,"_")}-browser-action"`);}});var oVal=Services.prefs.getStringPref("browser.uiCustomization.state");var nVal=oVal.replace(/(^.*,"unified-extensions-area":\[)[^\]]*(\],.*$)/,"$1"+order.join(",")+"$2");Services.prefs.setStringPref("browser.uiCustomization.state",nVal);console.log(`// old\n// Services.prefs.setStringPref("browser.uiCustomization.state", "${oVal.replace(/(["\\])/g,'\\$1')}");\n\n// new\nServices.prefs.setStringPref("browser.uiCustomization.state", "${nVal.replace(/(["\\])/g,'\\$1')}");\n`);console.log(`// about:config pref "browser.uiCustomization.state" changed, old/new values are shown above, ** please restart Firefox to apply **`);});
```
