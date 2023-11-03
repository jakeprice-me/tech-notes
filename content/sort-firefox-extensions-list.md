---
alias: sort-firefox-extensions-list
archive_links: []
category: firefox
classification: public
date: 2023-06-16 16:49:30
date_modified: 2023-06-16 16:49:30
id: 20230616164930
link: https://raw.githubusercontent.com/icpantsparti2/browser-bits/main/javascript/firefox-v109-change-order-under-extensions-button.js
local_archive: 
pinned: false
series: 
tags: [firefox, extensions]
title: Sort Firefox Extensions List
type: tech-note
uuid: 87f926bc-5b0b-4cf9-8f1a-191828c87baa
---

Follow the below steps to sort your extension list (jigsaw icon) in Firefox until they have a way to sort it automatically (thanks to [this script](https://raw.githubusercontent.com/icpantsparti2/browser-bits/main/javascript/firefox-v109-change-order-under-extensions-button.js)).

1. Open `about:addons`
2. Open the web console
3. Copy and paste the below code into the console and run it.

```js
javascript:AddonManager.getAddonsByTypes(["extension"]).then(addons=>{var order=[];addons.sort((a,b)=>{return a.name.localeCompare(b.name);}).forEach(addon=>{if(!(addon.isBuiltin||addon.isSystem)){order.push(`"${addon.id.toLowerCase().replace(/[{}@.]/g,"_")}-browser-action"`);}});var oVal=Services.prefs.getStringPref("browser.uiCustomization.state");var nVal=oVal.replace(/(^.*,"unified-extensions-area":\[)[^\]]*(\],.*$)/,"$1"+order.join(",")+"$2");Services.prefs.setStringPref("browser.uiCustomization.state",nVal);console.log(`// old\n// Services.prefs.setStringPref("browser.uiCustomization.state", "${oVal.replace(/(["\\])/g,'\\$1')}");\n\n// new\nServices.prefs.setStringPref("browser.uiCustomization.state", "${nVal.replace(/(["\\])/g,'\\$1')}");\n`);console.log(`// about:config pref "browser.uiCustomization.state" changed, old/new values are shown above, ** please restart Firefox to apply **`);});
```
