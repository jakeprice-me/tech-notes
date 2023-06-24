---
alias: reconnection-issue-sonoff-snzb-02-zigbee2mqtt
category: smart-home
classification: public
date: 2022-10-07 16:24:37
date_modified: 2023-06-24 18:34:51
id: 20221007162437
link: https://www.zigbee2mqtt.io/devices/SNZB-02.html
pinned: false
series: 
tags: [sonoff, zigbee, mqtt, temperature, sensor, home-assistant, temperature, power]
title: Reconnection Issue with Sonoff SNZB-02 in Zigbee2MQTT
type: tech-note
uuid: d19e79e6-486e-4bba-8b83-304941b8d405
---

## Lost Connection Issue

If connection is lost, and a sensor stops reporting, the simplest way to fix is as follows:

1. Force remove the device from Zigbee2MQTT.
2. Restart Zigbee2MQTT
3. Re-pair the device

> [!tip]
> This seems to pretty consistently work, step 2 is particularly important if you have issues with the battery status not registering, which also tends to mean the sensor values aren't being published.

## Post Battery Replacement Issue

I had an issue with a SONOFF SNZB-02 temperature & humidity sensor, after replacing the battery I couldn't get it to reconnect to Zigbee2MQTT without the power column showing a question mark for the battery status. As a result it wasn't exposing any results. 

There was nothing in the log file either.

What eventually did the trick I think was restarting Zigbee2MQTT from Settings > Restart Zigbee2MQTT in the Zigbee2MQTT dashboard on Home Assistant. It then paired and finally published the battery status - although it doesn't seem like the battery is reporting correctly - initially it showed around 20%, and after clicking the reconfigure button it now shows around 62%, but that's still lower than expected for a new battery - unless it's been pulling power more than usual because of whatever issue was going on?

If you're really having no luck with it, remove the battery for a few minutes and then follow the above.