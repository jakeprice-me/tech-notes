---
aliases:
  - kusto-tips-and-snippets
archive_links: 
category: azure
classification: public
date: 2022-10-19T14:00:41
date_modified: 2022-10-19T14:00:41
draft: false
id: 20221019140041
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - kusto
  - azure
  - query
  - log
  - metric
title: Kusto Tips & Snippets
type: tech-note
---

> KQL is case-sensitive for everything – table names, table column names, operators, functions, and so on.

```js
// Virtual Machine Percentage Free Disk Space
Perf 
| where ObjectName == "Logical Disk"
| where InstanceName == "/"
| where CounterName == "% Free Space"
| summarize arg_max(TimeGenerated, *) by Computer
| project TimeGenerated, Computer, InstanceName, round(CounterValue, 2)
```

```js
// Virtual Machine Percentage Free Disk Space
Perf 
| where ObjectName == "Logical Disk"
| where CounterName == "% Free Space"
| where InstanceName matches regex @'(^\/$)|(\/data)'
```

```js
// Virtual Machine Percentage Free Disk Space
Perf 
| where ObjectName == "Logical Disk"
| where CounterName == "% Free Space"
| where InstanceName matches regex @'(^\/$)|(\/data)'
| sort by TimeGenerated asc nulls first 
```

```js
// Virtual Machine Percentage Free Disk Space
Perf 
| where ObjectName == "Logical Disk"
| where CounterName == "% Free Space"
| where InstanceName matches regex @'(^\/$)|(\/data)'
| summarize arg_max(TimeGenerated, *) by Computer, InstanceName // arg_max over TimeGenerated returns the latest record
| project TimeGenerated, Computer, InstanceName, CounterValue
```

```js
Perf
| where ObjectName == "Logical Disk" and CounterName == "% Free Space"
| where InstanceName matches regex @'(^\/$)|(\/data)'
| extend ComputerDrive = strcat(Computer, ' - ', InstanceName)
| summarize Used_Space_Percent = max(CounterValue) by ComputerDrive, bin(TimeGenerated, 1h)
| render timechart 
```