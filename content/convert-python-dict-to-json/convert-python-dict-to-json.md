---
aliases:
  - convert-python-dict-to-json
archive_links: 
category: python
classification: public
date: 2020-01-04T15:20:16
date_modified: 2020-01-04T15:20:16
draft: false
id: 20200104152016
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [python, dict, json]
title: Convert Python Dictionary to JSON
type: tech-note
---

``` python
import json

example_dictionary = {
    'query': 'Genesis 1:1',
    'canonical': 'Genesis 1:1',
    'parsed': [[1001001, 1001001]],
    'passage_meta': [{
        'canonical': 'Genesis 1:1',
        'chapter_start': [1001001, 1001031],
        'chapter_end': [1001001, 1001031],
        'prev_verse': None,
        'next_verse': 1001002,
        'prev_chapter': None,
        'next_chapter': [1002001, 1002025]
        }],
    'passages': ['The Creation of the World\n\n  In the beginning, God created the heavens and the earth. (ESV)']
    }

example_json = json.dumps(example_dictionary, sort_keys=True, indent=4)
print(example_json)
```

