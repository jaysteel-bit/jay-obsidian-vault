




---


---

I pulled all **125** starred repos via the GitHub API (verified against your Stars tab), plus license and last-push data, since license and maintenance status are decisive for an "assemble Layer 1, never fork" strategy.

Two quick notes before the table: **TimescaleDB and Constructive's `agentic-db` are not in your stars** — you mentioned them but they aren't starred, so they're not in this list. And `page-agent` *is* there (alibaba/page-agent).

---

# 1. All 125 starred repos

The **L** column is my first-pass layer call using your own stack: **L1** = commodity infra to wrap, **L3** = surface/asset, **skill** = prompt/content asset (not architecture), **⚠** = overlaps Layer 2 / danger, **—** = no use here.

| # | Repo | Lang | License | What it is | L |
|---|------|------|---------|-----------|---|
| 1 | [PrimeIntellect-ai/prime-agent](https://github.com/PrimeIntellect-ai/prime-agent) | TS | MIT | Self-improving agent for long-running coding work | L1 |
| 2 | [motion-canvas/motion-canvas](https://github.com/motion-canvas/motion-canvas) | TS | MIT | Code-driven animation engine | L3 |
| 3 | [motion-canvas/examples](https://github.com/motion-canvas/examples) | JS | MIT | Examples (stale, 2024) | — |
| 4 | [WyattBlue/auto-editor](https://github.com/WyattBlue/auto-editor) | Nim | Unlicense | Automatic video cut/trim | L1 |
| 5 | [baidu/Unlimited-OCR](https://github.com/baidu/Unlimited-OCR) | Py | MIT | Long-document OCR / parsing | L1 |
| 6 | [andrewyng/openworker](https://github.com/andrewyng/openworker) | Py | MIT | Agentic worker framework | L1 |
| 7 | [video-db/call.md](https://github.com/video-db/call.md) | TS | **NONE** | Meeting capture → live agent loops | ⚠ |
| 8 | [WASasquatch/comfyui-plugins](https://github.com/WASasquatch/comfyui-plugins) | — | NONE | ComfyUI plugin index (dead since 2023) | — |
| 9 | [space-nuko/ComfyBox](https://github.com/space-nuko/ComfyBox) | TS | — | Alternate ComfyUI frontend | L3 |
| 10 | [comfyanonymous/ComfyUI_examples](https://github.com/comfyanonymous/ComfyUI_examples) | HTML | NOASSERT | Workflow examples | L3 |
| 11 | [Comfy-Org/ComfyUI](https://github.com/comfyanonymous/ComfyUI) | Py | **GPL-3.0** | Node-based diffusion backend + API | L1 |
| 12 | [emilkowalski/skills](https://github.com/emilkowalski/skills) | — | — | Design/eng agent skills | skill |
| 13 | [firecrawl/anydoc](https://github.com/firecrawl/anydoc) | Rust | MIT | Office/EPUB/CSV/PDF → text | L1 |
| 14 | [elayadesign/ai-design-skills](https://github.com/elayadesign/ai-design-skills) | — | — | Design skills for agents | skill |
| 15 | [teng-lin/notebooklm-py](https://github.com/teng-lin/notebooklm-py) | Py | MIT | NotebookLM unofficial API/skill | L1 |
| 16 | [firecrawl/pdf-inspector](https://github.com/firecrawl/pdf-inspector) | Rust | MIT | Fast PDF classify + extract | L1 |
| 17 | [trycompai/crm](https://github.com/trycompai/crm) | TS | MIT | Agent-first open-source CRM | L3 |
| 18 | [every-app/open-seo](https://github.com/every-app/open-seo) | TS | MIT | Open SEO/keyword tooling | L3 |
| 19 | [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | Py | MIT | Hermes agent runtime | L1 |
| 20 | [RinDig/Interpretable-Context-Methodology](https://github.com/RinDig/Interpretable-Context-Methodology) | Py | MIT | Folder structure as agent architecture | skill |
| 21 | [block/buzz](https://github.com/block/buzz) | Rust | Apache-2.0 | Multi-agent comms / "hive mind" | L1 |
| 22 | [permissionlesstech/bitchat](https://github.com/permissionlesstech/bitchat) | Swift | — | BLE mesh chat | — |
| 23 | [palmier-io/palmier-pro](https://github.com/palmier-io/palmier-pro) | Swift | — | macOS AI video editor | — |
| 24 | [CoreBunch/Instatic](https://github.com/CoreBunch/Instatic) | TS | MIT | Agentic CMS / site builder | L3 |
| 25 | [virgiliojr94/book-to-skill](https://github.com/virgiliojr94/book-to-skill) | Py | — | Book PDF → agent skill | skill |
| 26 | [grandamenium/understand-open-source](https://github.com/grandamenium/understand-open-source) | — | — | Deep repo comprehension | skill |
| 27 | [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | Py | Apache-2.0 | Codebase+docs+schema → graph | L1 |
| 28 | [vercel-labs/opensrc](https://github.com/vercel-labs/opensrc) | Rust | Apache-2.0 | Fetch npm source for agent context | L1 |
| 29 | [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) | Py | — | Concise-output agent skill | skill |
| 30 | [LottieFiles/dotlottie-flutter](https://github.com/LottieFiles/dotlottie-flutter) | Dart | — | Lottie player for Flutter | — |
| 31 | [outsourc-e/hermes-workspace](https://github.com/outsourc-e/hermes-workspace) | JS | — | Web workspace for Hermes | L3 |
| 32 | [0xNyk/awesome-hermes-agent](https://github.com/0xNyk/awesome-hermes-agent) | — | NOASSERT | Hermes ecosystem directory | skill |
| 33 | [builderz-labs/mission-control](https://github.com/builderz-labs/mission-control) | TS | MIT | Self-hosted agent control plane | L3 |
| 34 | [builderz-labs/marketing-dashboard](https://github.com/builderz-labs/marketing-dashboard) | TS | MIT | Local-first marketing ops center | L3 |
| 35 | [AhmadIbrahiim/Website-downloader](https://github.com/AhmadIbrahiim/Website-downloader) | HTML | — | Site asset downloader | — |
| 36 | [anthropics/claude-quickstarts](https://github.com/anthropics/claude-quickstarts) | TS | — | Starter projects | skill |
| 37 | [anthropics/financial-services](https://github.com/anthropics/financial-services) | Py | — | Finance-domain agent examples | skill |
| 38 | [anthropics/html-effectiveness](https://github.com/anthropics/html-effectiveness) | HTML | — | HTML rendering examples | skill |
| 39 | [anthropics/claude-plugins-community](https://github.com/anthropics/claude-plugins-community) | Py | — | Community plugin registry | skill |
| 40 | [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) | Py | — | Official plugin registry | skill |
| 41 | [anthropics/knowledge-work-plugins](https://github.com/anthropics/knowledge-work-plugins) | Py | — | Knowledge-work plugins | skill |
| 42 | [anthropics/skills](https://github.com/anthropics/skills) | Py | — | Agent Skills repo | skill |
| 43 | [anthropics/courses](https://github.com/anthropics/courses) | Jupyter | — | Educational courses | skill |
| 44 | [baairon/