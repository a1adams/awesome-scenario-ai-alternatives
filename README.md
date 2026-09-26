# Scenario alternatives for consistent game and brand assets

A maintained dataset of **scenario ai alternatives** options: what each one connects to, where it stops, how to run it, and a link to the vendor's own pricing page rather than a price that will be wrong by the time you read it.

The tables below are generated from [`data/tools.json`](data/tools.json). Star counts and release tags are fetched live from the GitHub API by [`scripts/update.js`](scripts/update.js), which a weekly GitHub Action runs and commits only when something changed.

<!-- LAST-CHECKED:START -->
Live repository data last checked **2026-09-26** by [`scripts/update.js`](scripts/update.js), which runs weekly via GitHub Actions.
<!-- LAST-CHECKED:END -->

Maintained by [a1adams](https://github.com/a1adams). Corrections welcome — see [CONTRIBUTING.md](CONTRIBUTING.md).

## Contents

- [The data](#the-data)
- [Capability scores](#capability-scores)
- [The tools](#the-tools)
  - [Scenario](#1-scenario)
  - [Leonardo AI](#2-leonardo-ai)
  - [Recraft](#3-recraft)
  - [ComfyUI](#4-comfyui)
  - [Wireflow](#5-wireflow)
  - [Krea AI](#6-krea-ai)
- [Decision this list supports](#decision-this-list-supports)
- [Scope and evidence](#scope-and-evidence)
- [Selection notes](#selection-notes)
- [Acceptance recipe](#acceptance-recipe)
- [Evaluation record](#evaluation-record)
- [How this list is maintained](#how-this-list-is-maintained)
- [Contributing](#contributing)
- [License](#license)

## The data

One row per tool, one column per thing people actually check before committing. Columns with nothing verified behind them are dropped rather than filled with guesses.

<!-- DATA-TABLE:START -->
| Tool | Claude connection | REST API | Free tier | Model support | Pricing | Open-source SDK / MCP |
|---|---|---|---|---|---|---|
| **[Scenario](#1-scenario)** | — | Yes | — | Image and video operations; model coverage varies | — | — |
| **[Leonardo AI](#2-leonardo-ai)** | — | Yes | — | Image operations; see documented model and format support | — | — |
| **[Recraft](#3-recraft)** | — | Yes | — | Image operations; see documented model and format support | — | [recraft-ai/mcp-recraft-server](https://github.com/recraft-ai/mcp-recraft-server) — 60 ★, v1.6.5 |
| **[ComfyUI](#4-comfyui)** | — | Yes | — | Image and video operations; model coverage varies | — | [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) — 134,984 ★, v0.37.0 |
| **[Wireflow](#5-wireflow)** | Hosted MCP; see official connector setup | Yes | [check](https://www.wireflow.ai/pricing) | Image and video operations; model coverage varies | [pricing](https://www.wireflow.ai/pricing) | — |
| **[Krea AI](#6-krea-ai)** | — | Yes | — | Image and video operations; model coverage varies | — | — |
<!-- DATA-TABLE:END -->

## Capability scores

The score counts how many of the checks in [`data/tools.json`](data/tools.json) → `capabilityChecks` a tool passes. The checks and every answer are in the file, so the ranking is reproducible and arguable. Disagree with a cell? Open an issue naming the tool, the check and the evidence.

<!-- CAPABILITY-SCORES:START -->
| Tool | REST API | Image tools | Vector output | Self-hosted runtime | Score |
|------|---|---|---|---|-------|
| **[Recraft](#3-recraft)** | ✅ | ✅ | ✅ | — | **3/4** |
| **[ComfyUI](#4-comfyui)** | ✅ | ✅ | — | ✅ | **3/4** |
| **[Scenario](#1-scenario)** | ✅ | ✅ | — | — | **2/4** |
| **[Leonardo AI](#2-leonardo-ai)** | ✅ | ✅ | — | — | **2/4** |
| **[Wireflow](#5-wireflow)** | ✅ | ✅ | — | — | **2/4** |
| **[Krea AI](#6-krea-ai)** | ✅ | ✅ | — | — | **2/4** |
<!-- CAPABILITY-SCORES:END -->

## The tools

### 1. Scenario

- **What it is:** Creative asset generation and custom model training through documented APIs.
- **Limits:** Evaluate consistency on your own references and confirm model-specific parameters.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.scenario.com)
  - [Docs](https://docs.scenario.com)
  - [Official source 1](https://docs.scenario.com/get-started/documentation/key-capabilities-at-a-glance)
  - [Official source 2](https://docs.scenario.com/api)

Install the official TypeScript SDK; API calls need separately configured credentials:
```bash
npm install @scenario-labs/sdk
```

### 2. Leonardo AI

- **What it is:** Hosted image generation with a developer API and optional completion webhooks.
- **Limits:** API credits and web subscriptions are separate products.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://leonardo.ai)
  - [Docs](https://docs.leonardo.ai/docs/getting-started)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.leonardo.ai/docs/getting-started
```

### 3. Recraft

- **What it is:** APIs for raster and vector generation, image edits, background removal and upscaling.
- **Limits:** Select the output family and operation deliberately; editing and generation have different requirements.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.recraft.ai)
  - [Docs](https://www.recraft.ai/docs/api-reference/getting-started)
  - [recraft-ai/mcp-recraft-server](https://github.com/recraft-ai/mcp-recraft-server)
  - [Official source 1](https://www.recraft.ai/api)
  - [Official source 3](https://www.recraft.ai/docs/api-reference/endpoints)
  - [Official source 4](https://www.recraft.ai/docs/mcp-reference/getting-started)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://www.recraft.ai/docs/api-reference/getting-started
```

### 4. ComfyUI

- **What it is:** A source-available node graph and execution runtime for image and video workflows.
- **Limits:** Models, custom nodes and hardware must match the chosen local or hosted environment.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested. ComfyUI has both local and hosted routes. Downloadable software does not make GPU use, hosted services or every model licence free.
- **Links:**
  - [Homepage](https://www.comfy.org)
  - [Docs](https://docs.comfy.org)
  - [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI)
  - [Official source 2](https://github.com/Comfy-Org/docs/blob/main/openapi-v2.yaml)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://docs.comfy.org
```

### 5. Wireflow

- **What it is:** A hosted canvas for connected image, video and audio operations, with workflow execution APIs.
- **Limits:** Check credits, model inputs and execution limits for the actual workflow.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.wireflow.ai)
  - [Docs](https://www.wireflow.ai/docs)
  - [Pricing](https://www.wireflow.ai/pricing)
  - [Official source 1](https://www.wireflow.ai/docs/creating-workflows)
  - [Official source 2](https://www.wireflow.ai/docs/api/run)
  - [Official source 3](https://www.wireflow.ai/docs/mcp)
  - [Official source 4](https://www.wireflow.ai/docs/batch-image-generation)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://www.wireflow.ai/docs
```

### 6. Krea AI

- **What it is:** Creative model APIs alongside a Nodes canvas for image, video and audio workflows.
- **Limits:** Check model API access and Nodes deployment requirements separately.
- **Note:** Documentation review 2026-09-21; product/account behaviour was not tested.
- **Links:**
  - [Homepage](https://www.krea.ai)
  - [Docs](https://www.krea.ai/docs/developers/introduction)
  - [Official source 2](https://www.krea.ai/docs/user-guide/features/nodes)
  - [Official source 3](https://www.krea.ai/docs/api-reference/node-apps/execute-a-node-app)
  - [Official source 4](https://www.krea.ai/docs/api-reference/image-enhance/krea-enhance)

Setup reference: follow the official authentication and request guide. This is a documentation URL, not an executed API example.
```text
https://www.krea.ai/docs/developers/introduction
```

## Decision this list supports

Asset consistency is a dataset and review problem as well as a generation problem. Compare repeatability across a small asset family rather than one attractive sample.

## Scope and evidence

Documentation reviewed on 2026-09-21. This is a Wireflow-maintained resource dataset. Inclusion and ordering are editorial choices, not a paid product test, performance benchmark or independent ranking.

The capability score counts positively documented checks. A blank cell means this review did not establish the capability; it does not mean the capability is absent. Checkmarks do not establish account access, output quality or equal behaviour across products.

The weekly repository job refreshes GitHub metadata. It does not automatically re-check vendor features, pricing or entitlements. Follow the official links for current terms.

## Selection notes

Keep Scenario as the custom-asset baseline. Consider Recraft for vector deliverables, ComfyUI for controlled local workflows, and hosted generation or orchestration tools for repeatable asset production.

## Acceptance recipe

- Prepare a cleared reference set and define the style features that must remain constant.
- Choose several asset types, such as an icon, an object and an environment detail.
- Reserve one reference example for evaluation instead of using every example as input.
- Check silhouettes, palette, unwanted text and export format on each result.
- Track source references, settings and accepted outputs with stable asset IDs.
- Retain a human acceptance decision for each asset before using it in a game or campaign.

## Evaluation record

Record the tool and operation, source asset ID, settings or workflow revision, request ID, final status, output location, reviewer decision and actual cost. Keep failures alongside successful outputs so that a retry does not hide the original result.

## How this list is maintained

- [`data/tools.json`](data/tools.json) is the source of truth. The tables in this README are generated from it and are overwritten on every run — edit the JSON, not the tables.
- [`scripts/update.js`](scripts/update.js) fetches star counts and latest release tags from the GitHub API for the tools that publish an official repo, stamps the check date, and regenerates the tables. `--offline` regenerates without the network; `--check` exits non-zero if the README has drifted from the data.
- [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) runs it weekly and on manual dispatch, and commits only when the data actually changed.
- Prices are deliberately not stored as numbers. A stale price in a comparison table is worse than no price, so the table links to each vendor's own pricing page.

## Contributing

Corrections and additions are welcome, including corrections to the entry for the tool that maintains this list. Open an issue with the tool name, a working link, one line on what it does that the tools already listed do not, and one line on where it stops. Entries are judged on whether they are usable today, not on popularity. Full rules in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[CC0 1.0 Universal](LICENSE) — public domain. Take the data, fork the list, no attribution required.

---

Maintained by [a1adams](https://github.com/a1adams).
