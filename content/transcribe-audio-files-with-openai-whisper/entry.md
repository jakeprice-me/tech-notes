---
aliases:
  - transcribe-audio-files-with-openai-whisper
category: machine-learning
classification: public
date: 2025-01-16T21:56:47
date_modified: 2025-01-16T21:56:47
draft: false
id: 20250116215647
image: 
links:
  - https://github.com/openai/whisper
local_archive_links: 
pinned: false
print: false
series: 
tags:
  - audio
  - machine-learning
  - openai
  - speech-recognition
  - transcription
  - whisper
title: Transcribe Audio Files with OpenAI Whisper
type: tech-note
---

I record a lot of voice notes as I'm out and about, it's often quicker then typing thoughts out, but when I get back to my laptop there will often be voice notes I want to transcribe into text. it's not just my own voice notes though, sometimes there will be something that really stands out in something I've listened to on YouTube or a Podcast that I want to clip and transcribe.

It's hard to overstate just how fantastic [OpenAI's Whisper](https://github.com/openai/whisper) is. It may be that I happen to have a nice clear voice, but I can transcribe everything in seconds on my HP EliteBook (with Intel onboard graphics only) and it's extremely accurate, requiring only a few edits to the output text.

Installation is easy:

```sh
pip install -U openai-whisper
```

Then once you've done that just feed `whisper` one or more audio files and specify a model. I never really have to use anything more than the `tiny` model, it generally transcribes everything I say spot-on, any issues I can quickly correct. It really is amazing.

```sh
# Single audio file:
whisper audio_2025-01-16_21-54-03.ogg --model tiny --output_format txt

# All audio files in a directory:
whisper * --model tiny --output_format txt
```

The above command will output the transcription on the console, but by specifying `--output_format` it'll also save it to a text file. If you don't specify that, it'll output the transcription in various formats that you may or may not need like `json`, `srt` etc.

It's absolutely excellent. There's no need to use any dodgy, paid online services, just use `whisper`.