---
aliases:
  - get-telegram-bot-chat-id
category: telegram
classification: public
date: 2022-08-11T21:20:57
date_modified: 2022-08-11T21:20:57
draft: false
id: 20220811212057
image: 
links: 
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - api
  - bot
  - chat-id
  - telegram
title: Get Telegram Bot Chat ID
type: tech-note
---

Send a message to your Telegram Bot first using the Bot token, then you can retrieve the Chat ID. 

```sh
curl --silent --request GET https://api.telegram.org/bot<bot_api_token>/getUpdates | jq '.result[]|.message.chat.id'
```