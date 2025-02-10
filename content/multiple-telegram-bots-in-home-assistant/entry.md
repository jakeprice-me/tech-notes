---
aliases:
  - multiple-telegram-bots-in-home-assistant
category: home-assistant
classification: public
date: 2024-10-31T20:34:57
date_modified: 2024-10-31T20:34:57
draft: false
id: 20241031203457
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - bot
  - home-assistant
  - notification
  - telegram
title: Multiple Telegram Bots in Home Assistant
type: tech-note
---

Frustratingly, it's not obviously possible to setup two individual Telegram bots and use them in Home Assistant.

In my scenario, I have an automation that sends a notification and photo when somebody comes to my front door. I want my wife to also get these notifications via Telegram.

The way to do this is to share and have the second user start a conversation with your Home Assistant Telegram bot, and then add that second user's Chat ID to the `allowed_chat_ids` in Home Assistant's `configuration.yml`. 

```yaml
telegram_bot:
  - platform: polling
    api_key: <bot-api-key>
    allowed_chat_ids:
      - <chat-id-1> # jake
      - <chat-id-2> # abbi
```

You must also add both Chat ID's to `target`, in your `telegram_bot.send_message` action, to avoid the message only being sent to the first Chat ID defined above.

> Target: An array of pre-authorised chat_ids to send the notification to. If not present, first allowed chat_id is the default.

```yaml
action:
  - data:
      message: Test Message
      target:
        - <chat-id-1>
        - <chat-id-2>
    action: telegram_bot.send_message
    enabled: true
```

This works fine. My initial concern was that she would get all the many Home Assistant notifications I send to this bot, but because you can define the `target` in the automation, you can easily only include the second user in some notifications triggered by automations.