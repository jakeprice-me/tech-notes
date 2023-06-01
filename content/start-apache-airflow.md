---
alias: start-apache-airflow
category: airflow
classification: public
date: 2020-10-22 16:23:49
date_modified: 2020-10-22 16:23:49
id: 20201022162349
link: 
pinned: false
series: 
tags: [airflow, apache]
title: Start Airflow
type: tech-note
uuid: c843ef1a-c34d-43ad-9201-5d10607ca19c
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
