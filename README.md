<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0EA5E9,50:6366F1,100:8B5CF6&height=200&section=header&text=Aryan%20Singh&fontSize=64&fontColor=ffffff&fontAlignY=36&desc=backend%20%C2%B7%20data%20pipelines%20%C2%B7%20applied%20ML&descSize=18&descAlignY=58&animation=fadeIn" alt="Aryan Singh" />

<div align="center">

<a href="https://github.com/aryansingh3">
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=2800&pause=900&color=6366F1&center=true&vCenter=true&width=620&lines=I+build+the+pipelines+behind+live-event+ticket+markets.;Distributed+scrapers.+Change+streams.+Price+forecasts.;Python+%C2%B7+Go+%C2%B7+MongoDB+%C2%B7+XGBoost+%C2%B7+Qdrant" alt="Typing SVG" />
</a>

<sub>B.Tech Computer Science, NSUT Delhi '24 · Noida, India</sub>

<br><br>

[![Email](https://img.shields.io/badge/Email-aryansinghnse%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aryansinghnse@gmail.com)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-aryan10022001-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/aryan10022001)

![Profile views](https://komarev.com/ghpvc/?username=aryansingh3&style=for-the-badge&color=6366F1&label=PROFILE+VIEWS)

</div>

---

## `~` About

I work on **data infrastructure for live-event ticketing** — the systems that scrape, reconcile, and forecast a market where prices move by the minute and the source data is hostile, inconsistent, and rate-limited.

Day to day that means distributed scrapers behind rotating proxy pools, MongoDB change-stream daemons that keep denormalized fields honest, vector search for entity resolution across marketplaces, and gradient-boosted models that turn all of it into a price call.

> Most of this lives in private repositories, so the sections below describe the systems rather than link to them.

---

## `⚙` Systems I've Built

| System | What it does | Stack |
| :--- | :--- | :--- |
| **Cross-Marketplace Event Matcher** | Resolves the same real-world event across two ticket marketplaces despite mismatched names, venue aliases, tours, and multi-day passes. Vector similarity first, knowledge graph for aliases, LLM judge only for borderline cases. | `FastAPI` `Qdrant` `FastEmbed` `NetworkX` `GPT-4o-mini` |
| **Price Forecasting Engine** | Daily feature snapshots → median price forecasts at 1/3/7-day horizons, up/down direction classification, and BUY / SELL / HOLD calls with confidence and per-event risk scores. | `XGBoost` `pandas` `scheduled training` |
| **First-Sale Field Refresher** | Keeps precomputed presale/on-sale dates correct across platforms with conflicting conventions. Runs as both a change-stream daemon (reacts in seconds) and a cron sweep (safety net for missed resume tokens). | `MongoDB Change Streams` `Python` `Slack` |
| **Distributed Ticket Scrapers** | Multi-source collection behind a rotating proxy pool with structured logging and per-source persistence strategies. Hot paths rewritten in Go for throughput. | `Go` `Playwright` `Redis` `MongoDB` |
| **Ticketing REST API** | Analytics and subscription APIs — live sales, price history, presale/on-sale filtering, searchable inventory. | `Flask` `MongoDB` `Gunicorn` `Docker` |
| **MCP Server + Discord Bot** | Model Context Protocol server exposing the data layer to LLMs, with a Discord bot front-end for natural-language queries over the event database. | `MCP` `Python` `Discord API` |

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

### [timezone-lookup](https://github.com/aryansingh3/TimeZone_Folder)
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

## `⌨` Toolbox

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

**Backend & Data**

![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=for-the-badge&logo=qdrant&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)

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
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)

</div>

---

## `📊` By The Numbers

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=aryansingh3&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=00000000&title_color=8B5CF6&icon_color=0EA5E9&text_color=C9D1D9" />
  <img src="https://github-readme-stats.vercel.app/api?username=aryansingh3&show_icons=true&count_private=true&include_all_commits=true&hide_border=true&bg_color=00000000&title_color=6366F1&icon_color=0EA5E9&text_color=1F2328" alt="GitHub stats" height="170" />
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=aryansingh3&hide_border=true&background=00000000&stroke=30363D&ring=8B5CF6&fire=0EA5E9&currStreakLabel=8B5CF6&sideLabels=C9D1D9&currStreakNum=C9D1D9&sideNums=C9D1D9&dates=8B949E" />
  <img src="https://streak-stats.demolab.com?user=aryansingh3&hide_border=true&background=00000000&stroke=D0D7DE&ring=6366F1&fire=0EA5E9&currStreakLabel=6366F1&sideLabels=1F2328&currStreakNum=1F2328&sideNums=1F2328&dates=6E7781" alt="Streak" height="170" />
</picture>

<br>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=aryansingh3&layout=donut&langs_count=6&hide=jupyter%20notebook,c,cython,fortran,powershell,smarty,css,html&hide_border=true&bg_color=00000000&title_color=8B5CF6&text_color=C9D1D9" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=aryansingh3&layout=donut&langs_count=6&hide=jupyter%20notebook,c,cython,fortran,powershell,smarty,css,html&hide_border=true&bg_color=00000000&title_color=6366F1&text_color=1F2328" alt="Top languages" height="220" />
</picture>

</div>

---

## `📈` Contribution Activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-activity-graph.vercel.app/graph?username=aryansingh3&bg_color=00000000&color=C9D1D9&line=8B5CF6&point=0EA5E9&area_color=6366F1&area=true&hide_border=true&custom_title=Commits%20over%20the%20last%20year" />
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=aryansingh3&bg_color=00000000&color=1F2328&line=6366F1&point=0EA5E9&area_color=8B5CF6&area=true&hide_border=true&custom_title=Commits%20over%20the%20last%20year" alt="Contribution activity graph" width="100%" />
</picture>

<br><br>

<img src="https://raw.githubusercontent.com/aryansingh3/aryansingh3/output/snake.svg" alt="Contribution snake" width="100%" />

<br>

<img src="https://github-profile-trophy.vercel.app/?username=aryansingh3&column=7&margin-w=8&margin-h=8&no-bg=true&no-frame=true&theme=discord" alt="Trophies" />

<br><br>

<sub>Most of my commits land in private repositories — the graphs above count them, the repo list can't show them.</sub>

</div>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:8B5CF6,50:6366F1,100:0EA5E9&height=120&section=footer" alt="" />

<div align="center">
<sub>Open to conversations about backend systems, data pipelines, and applied ML.</sub>
</div>
