<p align="center">
  <img src="https://raw.githubusercontent.com/grimoire-hie/.github/main/profile/assets/grimoire_mascot.png" width="200" alt="GriMoire mascot" />
</p>

<h1 align="center">GriMoire</h1>

<p align="center">
  <strong>A visual AI assistant that lives inside SharePoint and acts across Microsoft 365</strong>
</p>

<p align="center">
  <a href="https://www.youtube.com/watch?v=i0feytPdMog"><img src="https://img.shields.io/badge/Demo-YouTube-red?logo=youtube" alt="Demo Video" /></a>
  <a href="https://github.com/SharePoint/sharepoint-hackathon/issues/160"><img src="https://img.shields.io/badge/SharePoint_Hackathon_2026-Submission_%23160-0078D4?logo=microsoftsharepoint&logoColor=white" alt="Hackathon Submission" /></a>
  <img src="https://img.shields.io/badge/SPFx-1.22-blue?logo=microsoftsharepoint" alt="SPFx 1.22" />
</p>

---

> *"This is not AI beside the UI. This is AI grounded in the UI."*

## What it does

GriMoire is a SharePoint Framework web part that turns Microsoft 365 from a set of separate tools into **one grounded interaction surface**. You talk or type in natural language, and GriMoire searches, summarizes, creates, and acts — without leaving SharePoint. The Hybrid Interaction Engine keeps the model aware of every visual block on screen, so context flows from UI to brain to action.

**One flow, zero app-switching:**

`"Find the budget documents"` &rarr; search results appear &rarr; `"Summarize the top one"` &rarr; recap card renders &rarr; `"Email it to the finance team"` &rarr; compose form pre-filled &rarr; sent.

## See it in action

**Search, focus, summarize** — find documents across SharePoint, drill into one, get a structured recap.

<video src="https://github.com/grimoire-hie/.github/raw/main/profile/assets/grimoire_focus_web.mp4" controls width="100%"></video>

**Compound workflow** — search, summarize, and email in a single conversation.

<video src="https://github.com/grimoire-hie/.github/raw/main/profile/assets/grimoire_compound.mp4" controls width="100%"></video>

**Create a SharePoint list** — list and columns, voice-driven, end to end.

<video src="https://github.com/grimoire-hie/.github/raw/main/profile/assets/grimoire_list_creation_web.mp4" controls width="100%"></video>

**Schedule a meeting** — calendar event with Teams link, created from natural language.

<video src="https://github.com/grimoire-hie/.github/raw/main/profile/assets/grimoire_calendar_web.mp4" controls width="100%"></video>

## Capabilities

**Reflexive UI awareness** — The Hybrid Interaction Engine maintains a running model of what the user sees. Interactions with blocks feed back into the conversation as structured events.

**Intent-based tri-source search** — Copilot Search (semantic), Copilot Retrieval (RAG), and SharePoint Search, fused via Reciprocal Rank Fusion into one ranked result set.

**100 tools across 8 MCP servers** — SharePoint, OneDrive, Outlook, Teams, Calendar, Word, User Profile, and Copilot. Actions that used to require 4 apps collapse into one sentence.

**Voice and text, same brain** — WebRTC voice (Azure OpenAI Realtime API) or HTTP streaming text. Both paths share the same tool dispatch and context. Switch mid-conversation.

**16 interactive block types** — Search results, document libraries, file previews, user cards, charts, forms, and more. Not just text — structured, actionable UI.

**Animated SVG avatar** — 7 expressions, 7 character visages, real-time lip sync, personality-driven reactions. The assistant has a face.

## By the numbers

| | |
|---|---|
| **100** tools | across **8** Agents 365 MCP servers |
| **16** block types | search results, libraries, forms, charts, permissions |
| **14** form presets | email, calendar, Teams, list CRUD, all pre-wired |
| **3** search sources | fused via Reciprocal Rank Fusion |
| **7** expressions | **7** visages, **5** voices, **4** personalities |
| **5** languages | with automatic detection and sticky switching |
| **84** test suites | covering critical paths |

## Technology stack

| Layer | Technology |
|-------|-----------|
| **Framework** | SharePoint Framework (SPFx) 1.22 |
| **UI** | React 17, Fluent UI v8, Zustand |
| **Voice** | WebRTC + Azure OpenAI Realtime API |
| **Text** | HTTP SSE streaming chat completions |
| **Search** | Copilot Search + Copilot Retrieval + SharePoint Search, RRF fusion |
| **M365 integration** | Agents 365 Tools — 8 MCP servers, 100 tools |
| **Avatar** | SVG facial-group renderer, Web Audio lip sync |
| **Backend** | Azure Functions v4 (Node.js, managed identity) |
| **Auth** | Delegated via SPFx AadHttpClient + managed identity for LLM |

<details>
<summary><strong>Architecture at a glance</strong></summary>
<br/>

```
User (voice or text)
  |
  +-- WebRTC --> Azure OpenAI Realtime ----+
  +-- HTTP SSE --> Chat Completions -------+
                                           |
                                           v
                            handleFunctionCall (shared)
                              |       |       |        |
                              v       v       v        v
                        Copilot   Copilot     SP     Agents 365
                         Search   Retrieval  Search    Tools
                              |       |       |        |
                              +-------+-------+        |
                                      |                |
                                 RRF Fusion            |
                                      |                |
                                      +--------+-------+
                                               |
                                               v
                                 UI Block -> Store -> ActionPanel
                                               |
                                        HIE -> Context -> LLM
                                               |
                                        Avatar Expression
```

</details>

---

<p align="center">
  <a href="https://www.credly.com/badges/7196e0a7-99ac-43f3-a637-13cb35b04a03/public_url"><img src="https://img.shields.io/badge/Credly-SharePoint_Hackathon_2026-FF6B00?logo=credly&logoColor=white" alt="Credly Badge" /></a>
</p>

<p align="center">
  Built by
  <a href="https://www.linkedin.com/in/nello-d-andrea/">Nello D'Andrea</a> and
  <a href="https://www.linkedin.com/in/nicole-beck-dekkara/">Nicole Beck Dekkara</a>
</p>
