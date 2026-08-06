<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:00F0FF,50:B026FF,100:FF2E97&height=200&section=header&text=Aryan%20Singh&fontSize=64&fontColor=ffffff&fontAlignY=36&desc=backend%20%C2%B7%20data%20pipelines%20%C2%B7%20applied%20ML&descSize=18&descAlignY=58&animation=fadeIn" alt="Aryan Singh" />

<div align="center">

<a href="https://github.com/aryansingh3">
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=2800&pause=900&color=00F0FF&center=true&vCenter=true&width=640&lines=I+build+the+pipelines+behind+live-event+ticket+markets.;15M%2B+API+requests+served+%C2%B7+200%2B+daily+users.;Distributed+scrapers.+Change+streams.+Price+forecasts." alt="Typing SVG" />
</a>

<sub>B.Tech Computer Science, NSUT Delhi '24 · Noida, India</sub>

<br><br>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Aryan_Singh-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aryan-singh-192622237/)
[![Email](https://img.shields.io/badge/Email-aryansinghnse%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aryansinghnse@gmail.com)

[![HuggingFace](https://img.shields.io/badge/HuggingFace-aryan10022001-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/aryan10022001)
[![Kaggle](https://img.shields.io/badge/Kaggle-rrrrarrr-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/rrrrarrr)
![Profile views](https://komarev.com/ghpvc/?username=aryansingh3&style=for-the-badge&color=B026FF&label=PROFILE+VIEWS)

</div>

---

## `~` About

I work on **data infrastructure for live-event ticketing** — the systems that scrape, reconcile, and forecast a market where prices move by the minute and the source data is hostile, inconsistent, and rate-limited.

Day to day that means distributed scrapers behind rotating proxy pools, MongoDB change-stream daemons that keep denormalized fields honest, vector search for entity resolution across marketplaces, and gradient-boosted models that turn all of it into a price call.

> Most of my work ships in private and organization repositories, so the sections below describe the systems rather than link to them.

---

## `🚀` Ticketmetric — Production Platform

<div align="center">

![Requests served](https://img.shields.io/badge/API_requests_served-15M%2B-00F0FF?style=for-the-badge&labelColor=0B0F14)
![Daily users](https://img.shields.io/badge/daily_active_users-200%2B-B026FF?style=for-the-badge&labelColor=0B0F14)
![API clients](https://img.shields.io/badge/API_clients-30%2B-FF2E97?style=for-the-badge&labelColor=0B0F14)
![Commits](https://img.shields.io/badge/my_commits-830%2B-39FF14?style=for-the-badge&labelColor=0B0F14)

</div>

<table>
<tr>
<td width="33%" valign="top">

### 🔌 Client API
[**`API docs ↗`**](https://api-client.ticketmetric.io/api/client/docs/)

Built **from scratch.** The public data API — Bearer API-key auth, Redis-backed rate limiting, tiered membership plans, and live Swagger docs.

**15M+ requests** served across **30+ client integrations.**

`Flask` `Redis` `MongoDB` `PM2`

</td>
<td width="33%" valign="top">

### 📊 Dashboard
[**`app.ticketmetric.io ↗`**](https://app.ticketmetric.io/dashboard/upcoming)

The customer-facing analytics product. **Led the full migration off MUI to shadcn/ui + Radix + Tailwind v4** — a ground-up rebuild of the component layer.

**200+ daily active users.**

`React` `TypeScript` `Tailwind v4` `Stripe`

</td>
<td width="33%" valign="top">

### ⚡ Dashboard API
`ticket_flask_api`

The analytics backend behind the dashboard — live sales, price history, presale/on-sale filtering, searchable inventory, and hot-section reporting.

`Flask` `MongoDB` `Docker` `Gunicorn`

</td>
</tr>
</table>

### How it fits together

```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'transparent',
  'primaryColor':'#0B0F14','primaryTextColor':'#E6EDF3','primaryBorderColor':'#00F0FF',
  'lineColor':'#B026FF','tertiaryColor':'#0B0F14',
  'clusterBkg':'#0B0F14','clusterBorder':'#233044',
  'edgeLabelBackground':'#0B0F14','fontSize':'15px'
}}}%%
flowchart LR
    subgraph SRC["MARKETPLACES"]
        A1[StubHub]
        A2[SeatGeek]
        A3[Ticketmaster / AXS]
    end

    subgraph ING["INGESTION"]
        B1["Go + Python scrapers<br/>Playwright · rotating proxies"]
        B2["Venue and capacity<br/>workers"]
    end

    subgraph CORE["DATA CORE"]
        C1[("MongoDB")]
        C2["Change-stream daemons<br/>presale / on-sale resolver"]
        C3["Event matcher<br/>Qdrant + LLM judge"]
    end

    subgraph ML["INTELLIGENCE"]
        D1["XGBoost forecasts<br/>1 / 3 / 7-day horizons"]
        D2["BUY · SELL · HOLD<br/>+ risk scoring"]
    end

    subgraph OUT["DELIVERY"]
        E1["Client API<br/>15M+ requests"]
        E2["Dashboard API"]
        E3["React dashboard<br/>200+ daily users"]
        E4["MCP server<br/>+ Discord bot"]
    end

    A1 & A2 & A3 --> B1
    B1 --> C1
    B2 --> C1
    C1 <--> C2
    C1 <--> C3
    C1 --> D1 --> D2
    D2 --> C1
    C1 --> E1
    C1 --> E2 --> E3
    C1 --> E4

    classDef src  fill:#0B0F14,stroke:#00F0FF,stroke-width:2px,color:#00F0FF
    classDef ing  fill:#0B0F14,stroke:#39FF14,stroke-width:2px,color:#39FF14
    classDef core fill:#0B0F14,stroke:#B026FF,stroke-width:3px,color:#D9A6FF
    classDef ml   fill:#0B0F14,stroke:#FF2E97,stroke-width:2px,color:#FF6FBE
    classDef out  fill:#0B0F14,stroke:#FFD60A,stroke-width:2px,color:#FFD60A

    class A1,A2,A3 src
    class B1,B2 ing
    class C1,C2,C3 core
    class D1,D2 ml
    class E1,E2,E3,E4 out

    linkStyle default stroke:#B026FF,stroke-width:1.5px
```

---

## `⚙` Other Systems I've Built

| System | What it does | Stack |
| :--- | :--- | :--- |
| **Cross-Marketplace Event Matcher** | Resolves the same real-world event across two ticket marketplaces despite mismatched names, venue aliases, tours, and multi-day passes. Vector similarity first, knowledge graph for aliases, LLM judge only for borderline cases. | `FastAPI` `Qdrant` `FastEmbed` `NetworkX` `GPT-4o-mini` |
| **Price Forecasting Engine** | Daily feature snapshots → median price forecasts at 1/3/7-day horizons, up/down direction classification, and BUY / SELL / HOLD calls with confidence and per-event risk scores. | `XGBoost` `pandas` `scheduled training` |
| **First-Sale Field Refresher** | Keeps precomputed presale/on-sale dates correct across platforms with conflicting conventions. Runs as both a change-stream daemon (reacts in seconds) and a cron sweep (safety net for missed resume tokens). | `MongoDB Change Streams` `Slack alerting` |
| **Distributed Ticket Scrapers** | Multi-source collection behind a rotating proxy pool with structured logging and per-source persistence strategies. Hot paths rewritten in Go for throughput. | `Go` `Playwright` `Redis` `MongoDB` |
| **MCP Server + Discord Bot** | Model Context Protocol server exposing the data layer to LLMs, with a Discord bot front-end for natural-language queries over the event database. | `MCP` `Python` `Discord API` |
| **Browser Extension** | Ticketmetric extension surfacing live pricing and inventory signals directly on marketplace pages. | `TypeScript` `Chrome APIs` |

### Where my commits go

```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'transparent',
  'pie1':'#00F0FF','pie2':'#B026FF','pie3':'#FF2E97',
  'pieOpacity':'1',
  'pieStrokeColor':'#0B0F14','pieStrokeWidth':'3px',
  'pieOuterStrokeColor':'#0B0F14','pieOuterStrokeWidth':'3px',
  'pieSectionTextColor':'#0B0F14','pieSectionTextSize':'18px',
  'pieTitleTextColor':'#B026FF','pieTitleTextSize':'20px',
  'pieLegendTextColor':'#7D8590','pieLegendTextSize':'15px'
}}}%%
pie showData
    title Commits across the production platform
    "Dashboard (React/TS)" : 527
    "Dashboard API (Flask)" : 206
    "Client API (Flask)" : 101
```

---

## `★` Selected Public Work

<table>
<tr>
<td width="50%" valign="top">

### [predii](https://github.com/aryansingh3/predii) ⭐ 4
Custom **named-entity recognition for the automotive domain** — a fine-tuned spaCy NER model plus a quantized Llama-2 7B, both published to Hugging Face with a hosted inference space and a full research write-up.

![Llama-2](https://img.shields.io/badge/Llama--2-0467DF?style=flat-square&logo=meta&logoColor=white) ![spaCy](https://img.shields.io/badge/spaCy-09A3D5?style=flat-square&logo=spacy&logoColor=white)

</td>
<td width="50%" valign="top">

### [timezone-lookup](https://github.com/aryansingh3/timezone-lookup)
Offline timezone resolution from a postal code or city/state/country. 200k+ city GeoNames database, 80+ countries, normalization for abbreviations and accents, optional Redis cache.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [audio-sentiment-analysis](https://github.com/aryansingh3/sentiment-analysis-by-analysing-audio)
Extracts sentiment, named entities, and conversation topics directly from audio, with a React front-end for exploring results.

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black) ![NLP](https://img.shields.io/badge/NLP-FF6F00?style=flat-square)

</td>
<td width="50%" valign="top">

### [blacklight-studios](https://github.com/aryansingh3/blacklight_studios)
Full-stack leaderboard service — current and historical weekly rankings, country filtering, and rank lookup by user ID. Deployed front and back.

![Angular](https://img.shields.io/badge/Angular-DD0031?style=flat-square&logo=angular&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [self-driving-car](https://github.com/aryansingh3/self-driving-car)
Neural-network-driven car learning to navigate traffic in a browser simulation, with sensors and a visualized network.

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Canvas](https://img.shields.io/badge/Canvas-E34F26?style=flat-square&logo=html5&logoColor=white)

</td>
<td width="50%" valign="top">

### [sorting-visualizer](https://github.com/aryansingh3/sorting-visualizer)
Step-through visualization of classic sorting algorithms with adjustable array size and animation speed.

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) ![Sass](https://img.shields.io/badge/Sass-CC6699?style=flat-square&logo=sass&logoColor=white)

</td>
</tr>
</table>

---

## `📄` Research

<table>
<tr>
<td valign="top">

### [Comparative Analysis for Speech Recognition using DeepSpeech](https://ieeexplore.ieee.org/document/10739129/)

[![IEEE Xplore](https://img.shields.io/badge/IEEE_Xplore-Published-00F0FF?style=for-the-badge&logo=ieee&logoColor=black&labelColor=0B0F14)](https://ieeexplore.ieee.org/document/10739129/)
![Primary author](https://img.shields.io/badge/Primary_author-B026FF?style=for-the-badge&labelColor=0B0F14)
![ICEECT 2024](https://img.shields.io/badge/ICEECT_2024-FF2E97?style=for-the-badge&labelColor=0B0F14)

**IEEE · 2024 International Conference on Electrical, Electronics and Computing Technologies** — Sharda University, 29 Aug 2024. Co-authored with NSUT Delhi faculty.

Automatic speech recognition for **English and Hindi** using a hybrid architecture: CNNs for feature extraction, RNNs for sequence learning, joined by **connectionist temporal classification** so transcription needs no linguistic pre-segmentation. Trained and evaluated on **LJSpeech** (English) and **OpenSLR** (Hindi), measured by **Word Error Rate**.

</td>
</tr>
</table>

---

## `⌨` Toolbox

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

**Backend & Data**

![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=for-the-badge&logo=qdrant&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)

**Frontend**

![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![Radix UI](https://img.shields.io/badge/Radix_UI-161618?style=for-the-badge&logo=radixui&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![React Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=for-the-badge&logo=reactquery&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=for-the-badge&logo=stripe&logoColor=white)

**ML & AI**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-337AB7?style=for-the-badge&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

**Infra**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=for-the-badge&logo=playwright&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Sentry](https://img.shields.io/badge/Sentry-362D59?style=for-the-badge&logo=sentry&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

</div>

---

## `📊` By The Numbers

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=aryansingh3&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=00000000&title_color=B026FF&icon_color=00F0FF&text_color=C9D1D9" />
  <img src="https://github-readme-stats.vercel.app/api?username=aryansingh3&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=00000000&title_color=B026FF&icon_color=00F0FF&text_color=1F2328" alt="GitHub stats" height="170" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=aryansingh3&hide_border=true&background=00000000&stroke=30363D&ring=B026FF&fire=FF2E97&currStreakLabel=00F0FF&sideLabels=C9D1D9&currStreakNum=C9D1D9&sideNums=C9D1D9&dates=8B949E" />
  <img src="https://streak-stats.demolab.com?user=aryansingh3&hide_border=true&background=00000000&stroke=D0D7DE&ring=B026FF&fire=FF2E97&currStreakLabel=00F0FF&sideLabels=1F2328&currStreakNum=1F2328&sideNums=1F2328&dates=6E7781" alt="Streak" height="170" />
</picture>

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=aryansingh3&layout=donut&langs_count=6&hide=jupyter%20notebook,c,cython,fortran,powershell,smarty,css,html&hide_border=true&bg_color=00000000&title_color=B026FF&text_color=C9D1D9" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=aryansingh3&layout=donut&langs_count=6&hide=jupyter%20notebook,c,cython,fortran,powershell,smarty,css,html&hide_border=true&bg_color=00000000&title_color=B026FF&text_color=1F2328" alt="Top languages" height="220" />
</picture>

</div>

---

## `📈` Contribution Activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=aryansingh3&bg_color=00000000&color=C9D1D9&line=00F0FF&point=FF2E97&area_color=B026FF&area=true&hide_border=true&custom_title=Commits%20over%20the%20last%20year" />
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=aryansingh3&bg_color=00000000&color=1F2328&line=00F0FF&point=FF2E97&area_color=B026FF&area=true&hide_border=true&custom_title=Commits%20over%20the%20last%20year" alt="Contribution activity graph" width="100%" />
</picture>

<br><br>

<img src="https://raw.githubusercontent.com/aryansingh3/aryansingh3/output/snake.svg" alt="Contribution snake" width="100%" />

<br>

<sub>Most of my commits land in private and organization repositories — the graphs above count them, the repo list can't show them.</sub>

</div>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:FF2E97,50:B026FF,100:00F0FF&height=120&section=footer" alt="" />

<div align="center">
<sub>Open to conversations about backend systems, data pipelines, and applied ML.</sub>
</div>
