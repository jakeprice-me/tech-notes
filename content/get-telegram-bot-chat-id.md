---
alias: get-telegram-bot-chat-id
category: telegram
classification: public
date: 2022-08-11 21:20:57
date_modified: 2022-08-11 21:20:57
id: 20220811212057
link: 
pinned: false
series: 
tags: [telegram, bot, chat-id, api]
title: Get Telegram Bot Chat ID
type: tech-note
uuid: 590e0154-50be-4da6-bc5b-58f19f5cf4eb
---

Send a message to your Telegram Bot first using the Bot token, then you can retrieve the Chat ID. 

```sh
curl --silent --request GET https://api.telegram.org/bot<bot_api_token>/getUpdates | jq '.result[]|.message.chat.id'
```