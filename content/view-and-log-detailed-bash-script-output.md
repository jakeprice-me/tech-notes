---
alias: view-and-log-detailed-bash-script-output
archive_link: []
category: bash
classification: public
date: 2019-11-22 17:30:25
date_modified: 2019-11-22 17:30:25
id: 20191122173025
link: 
local_archive: 
pinned: false
series: 
tags: [log, bash, script, stdout, stderr, debug, tee, background, process, run]
title: View and Log Detailed Bash Script Output
type: tech-note
uuid: bef8e458-5553-45e3-8be7-ccdfc3e5231f
---

Append `-xe` to `#!/bin/bash` in the script you wish to see detailed output for.

```sh
#!/bin/bash -xe
```

Then run it as below to see the debug output and stdout and stderr on the screen, _but_ also have it logged to a file.

``` sh
./script.sh 2>&1 | tee output.log
```