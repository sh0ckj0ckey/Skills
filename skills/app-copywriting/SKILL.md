---
name: app-copywriting
description: Provides guidance for creating, refining, and translating public copy in both Chinese and English for personal apps, especially GitHub open source pages and Microsoft Store listings. Use when the user provides app features, project notes, rough descriptions, draft copy, or existing text and needs polished Chinese and English GitHub repository descriptions, README project introductions, Microsoft Store short descriptions, full descriptions, feature lists, or similar app publishing text. Do not use for code implementation, technical architecture, legal policy writing, or unrelated marketing campaigns.
---

# App Copywriting

## Core Principles

- Create, refine, and translate public copy in both Chinese and English for personal apps.
- Keep the Chinese and English versions aligned in meaning, tone, and product positioning.
- Adapt the writing style to the target channel instead of translating sentence by sentence.
- Preserve the user's intended app identity, audience, formal level, and the distinctive features or characteristics the user highlights.
- Prefer clear, natural, polished writing over inflated marketing language.
- Do not invent major features, claims, platform support, pricing, or technical details that were not provided.
- If important information is missing, ask briefly or make conservative assumptions and state them.

## Input Handling

- The user may provide app features, project notes, rough descriptions, existing copy, screenshots, keywords, or repository context.
- First identify the app name in Chinese and English when both are provided.
- Separate the app's positioning from its feature list.
- Identify whether the source text is playful, neutral, professional, technical, or conversational.
- If the user provides existing copy, analyze its tone before rewriting or translating it.
- Keep a calm and concise tone when the product is a practical utility or developer tool.
- When the user gives draft text, improve it instead of replacing its intent.

## Channel Rules

- GitHub repository descriptions should be short, calm, and definition style.
- README text may be warmer and more expressive than GitHub text.
- Microsoft Store short descriptions should be concise and utility focused.
- Microsoft Store full descriptions may be a little more expressive, but should still remain clear and accessible.

## Tone by App Type

- For lightweight creative apps, keep the tone playful, gentle, and approachable.
- For practical utilities, start from the user's pain point and keep the wording clear.
- For developer tools, keep the wording precise and technical without becoming heavy.
- For personal apps, avoid corporate sounding marketing language.
- Avoid exaggerated claims such as "ultimate", "best", or "revolutionary" unless the user explicitly wants that style.

## GitHub Style

- Repository descriptions should use this personal format: emoji, one space, then a concise definition style sentence.
- Pick an emoji that matches the app's identity, domain, or feel.
- Keep the wording compact and professional.
- Prefer this shape:
  ```
  🌻 A clean sketchpad with shape recognition, background tracing, sketch export, and more.
  ```
  ```
  ✒ Tintenklecks Gallery is the demo app for Tintenklecks UI, built with Electron and Vue 3.
  ```
- For GitHub text, technical details are welcome when they help define the project clearly.
- Repository descriptions should be formal and professional, and may include technical details when they help define the project clearly.
- README overviews should be clearer and more descriptive than repository descriptions.
- README files should always place English before Chinese.
- In README content, the English and Chinese versions should be aligned in meaning, but not necessarily translated word for word.

## Microsoft Store Style

- Short descriptions should usually be one short sentence.
- Short descriptions should focus on what the app is and what it helps the user do.
- Full descriptions should be natural, readable, and friendly to general users.
- If the user's Chinese draft is light, rhetorical, or self aware, keep that feeling in the English version.
- Keep humor modest and readable.
- Avoid making a lightweight app sound like a large enterprise product.
- Avoid making a technical tool sound like a generic advertisement.
- Mention technical implementation details only when they help users understand the value.

## Writing Rules

- Write both Chinese and English unless the user asks for only one language.
- Use the official app names provided by the user.
- Use the English app name in English text and the Chinese app name in Chinese text.
- Do not translate mechanically when it makes the result unnatural.
- When translating into English, make sure the result is simple, easy to understand, natural, idiomatic, and grammatically correct.
- Keep Chinese natural, polished, and close to the user's intent.
- Keep English idiomatic, concise, and easy to read.
- For README files, always put English first and Chinese second.
- For store text, keep the two languages separate and polished to their own audiences.

## Example: Summer

User input:
```
I developed a UWP drawing app based on NativeAOT. It emphasizes fast startup, so users can start drawing immediately after opening it. It is not aimed at professional drawing workflows. It is more like a replacement for the sketch feature once found in Windows Ink Workspace, focused on quick sketches, convenience, and drafts. It also supports shape recognition, background tracing, and exporting work. The Chinese name is 暇墨 and the English name is Summer.
```

Existing store copy:
```
欢迎使用暇墨，在这里，你可以恣意挥洒墨水，充分释放你的想象，绘制一幅惊人的杰作！好吧，这可能有些难度，毕竟这个软件目前的功能比较简单。但是它至少能够让你记下灵感瞬间，或者梳理思考过程，或者...画个简单的草图。
```

Reasoning:
- The app is a lightweight creative tool.
- The store copy should keep a light and playful tone.
- The short store description should be calm and feature oriented.
- The GitHub description should be more professional and definition style.
- The README may reuse the lighter tone, with English first and Chinese second.

Microsoft Store short description:
```
A clean sketchpad with shape recognition, background tracing, sketch export, and more.
```

GitHub repository description:
```
🌻 A clean sketchpad with shape recognition, background tracing, sketch export, and more.
```

README overview:
```
## Overview

Welcome to Summer, where you can splash your ink as much as you want and fully unleash your imagination to draw an amazing masterpiece! Okay, that might be a bit difficult, after all, this software is rather simple at the moment. But it will at least allow you to jot down moments of inspiration, or comb through your thought process, or... draw a simple sketch.

欢迎使用暇墨，在这里，你可以恣意挥洒墨水，充分释放你的想象，绘制一幅惊人的杰作！好吧，这可能有些难度，毕竟这个软件目前的功能比较简单。但是它至少能够让你记下灵感瞬间，或者梳理思考过程，或者...画个简单的草图。
```

## Example: Conscripts

User input:
```
Conscripts is a script file aggregation and management app. Users can add BAT and PS1 scripts into it. The app copies the script files into its own directory and lets users assign icons, names, card colors, categories, and more. This makes it easier to launch scripts from within the app instead of searching through many identical file icons. It also supports Windows JumpList, so right clicking its Start Menu or taskbar icon can quickly launch a script.
```

Chinese store draft:
```
您是否是一位脚本文件的使用者？无论是批处理文件还是 PowerShell 脚本，不管多复杂的操作，只要轻轻双击，就可以等待脚本自动把所有工作都完成，这一切都是那么的美好。
只是，当脚本文件越来越多时，每次想要运行脚本，就要从众多图标一样的文件中，找到想要运行的脚本文件，这让人心烦，这不够优雅。如果您也有这种烦恼，那欢迎来体验一下 Conscripts，它是脚本文件的启动中心，将所有的脚本文件藏在幕后，取而代之的，是丰富的图标，和多彩的卡片。
```

Reasoning:
- This is a practical utility.
- The store copy should start from the user's pain point.
- The short description should be concise and utility focused.
- The GitHub description should be short, calm, and definition style.
- The README should keep English first and Chinese second.

Microsoft Store short description:
```
Keeps BAT and PS1 scripts organized in one place.
```

Microsoft Store full description:
```
Are you a frequent user of script files? Whether it's batch files or PowerShell scripts, no matter how complex the operation, a simple double click is all it takes to let the script handle everything automatically. It's all so effortless.
But as your collection of script files grows, finding the right one among a sea of identical icons can become frustrating and far from elegant. If this sounds familiar, then welcome to Conscripts, your centralized script launcher. It keeps all your script files hidden behind the scenes, replacing them with rich icons and vibrant cards for a more refined experience.
```

GitHub repository description:
```
🚀 A centralized launcher for managing and running BAT and PS1 scripts.
```

README overview:
```
## Overview

Are you a frequent user of script files? Whether it's batch files or PowerShell scripts, no matter how complex the operation, a simple double click is all it takes to let the script handle everything automatically. It's all so effortless.

But as your collection of script files grows, finding the right one among a sea of identical icons can become frustrating and far from elegant. If this sounds familiar, then welcome to Conscripts, your centralized script launcher. It keeps all your script files hidden behind the scenes, replacing them with rich icons and vibrant cards for a more refined experience.

您是否是一位脚本文件的使用者？无论是批处理文件还是 PowerShell 脚本，不管多复杂的操作，只要轻轻双击，就可以等待脚本自动把所有工作都完成，这一切都是那么的美好。

只是，当脚本文件越来越多时，每次想要运行脚本，就要从众多图标一样的文件中，找到想要运行的脚本文件，这让人心烦，这不够优雅。如果您也有这种烦恼，那欢迎来体验一下 Conscripts，它是脚本文件的启动中心，将所有的脚本文件藏在幕后，取而代之的，是丰富的图标，和多彩的卡片。
```

## Final Guidance

- Use the user's examples as tone anchors.
- Infer channel specific tone from the provided draft copy.
- Prefer one strong representative example over many weak ones.
- Keep GitHub descriptions short and defining.
- Keep README text bilingual with English first and Chinese second.
- Keep Store descriptions user friendly and channel appropriate.
- Do not let technical detail overwhelm the purpose of the copy.