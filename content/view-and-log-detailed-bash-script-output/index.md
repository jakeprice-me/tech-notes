---
aliases:
  - view-and-log-detailed-bash-script-output
category: bash
classification: public
date: 2019-11-22T17:30:25
date_modified: 2019-11-22T17:30:25
draft: false
id: 20191122173025
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [log, bash, scripting, stdout, stderr, debug, tee, background, process, run]
title: View and Log Detailed Bash Script Output
type: tech-note
---

Append `-xe` to `#!/bin/bash` in the script you wish to see detailed output for.

```sh
#!/bin/bash -xe
```

Then run it as below to see the debug output and stdout and stderr on the screen, _but_ also have it logged to a file.

``` sh
./script.sh 2>&1 | tee output.log
```

