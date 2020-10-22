---
aliases:
  - start-apache-airflow
archive_links: 
category: airflow
classification: public
date: 2020-10-22T16:23:49
date_modified: 2020-10-22T16:23:49
draft: false
id: 20201022162349
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags: [airflow, apache]
title: Start Airflow
type: tech-note
---

```sh
# Initialise the database:
airflow initdb

# Start Airflow Web Server:
nohup airflow webserver --port 8080 >> airflow_webserver.log 2>&1 &

# Start Airflow Scheduler:
nohup airflow scheduler >> airflow_scheduler.log 2>&1 &
```

It's helpful to know how to kill Airflow as well, and for some strange reason there is not `airflow stop` command, so you have to `kill` it in a ridiculous way:

```sh
# Kill Airflow Scheduler - https://stackoverflow.com/questions/44710056/how-to-stop-kill-airflow-scheduler-started-in-daemon-mode
kill $(ps -ef | grep "airflow scheduler" | awk '{print $2}')
```
