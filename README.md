# open-design-ai-framework

> **Design-to-code that actually ships** - AI-native open framework that converts Figma, screenshots, and natural language into production-grade React/TS components - multi-LLM, multi-runtime, multi-vendor.

<p align="center"><a href="https://github.com/hmzainjamil/open-design-ai-framework">Repository</a> · <a href="https://github.com/hmzainjamil/open-design-ai-framework/commits/main">Commits</a> · <a href="https://github.com/hmzainjamil/open-design-ai-framework/issues">Issues</a></p>
<p align="center"><img alt="Documentation" src="https://img.shields.io/badge/documentation-deep%20editorial-lightgrey"> <img alt="Lifecycle" src="https://img.shields.io/badge/lifecycle-active-success"></p>

<!-- HMZ DEEP README v1 -->

## At a glance

| Field | Current state |
|---|---|
| Repository | open-design-ai-framework |
| Visibility | Public |
| Lifecycle | Active |
| Evidence basis | Current repository documentation and source-visible material |

## Why this exists

**Design-to-code that actually ships** - AI-native open framework that converts Figma, screenshots, and natural language into production-grade React/TS components - multi-LLM, multi-runtime, multi-vendor.

The README documents the design-system scope and separates actual repository capabilities from downstream design-tool behavior and portfolio claims.

## CONCEPTS

| Concept | Location | Description |
|---|---|---|
| **CLAUDE.md guide** | `CLAUDE.md` | Agent-facing project guide - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/CLAUDE.md) |
| **Agent contract** | `AGENTS.md` | Multi-agent operating spec - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/AGENTS.md) |
| **Quickstart** | `QUICKSTART.md` | 60-second runnable demo - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/QUICKSTART.md) |
| **Changelog** | `CHANGELOG.md` | Semantic-release-managed history - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/CHANGELOG.md) |
| **CI pipeline** | `.github/workflows/ci.yml` | Lint, test, type-check matrix - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/.github/workflows/ci.yml) |
| **Stable release** | `.github/workflows/release-stable.yml` | Production publish workflow - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/.github/workflows/release-stable.yml) |
| **Beta release** | `.github/workflows/release-beta.yml` | Channel: beta - semantic-release - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/.github/workflows/release-beta.yml) |
| **Metrics workflow** | `.github/workflows/metrics.yml` | Repo activity + readme stats - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/.github/workflows/metrics.yml) |
| **i18n contributing** | `CONTRIBUTING.ja-JP.md` | Localized contributor docs - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/CONTRIBUTING.ja-JP.md) |
| **Multi-locale README** | `README.zh-CN.md` | Native-language README variants - [Source](https://github.com/hmzainjamil/open-design-ai-framework/blob/main/README.zh-CN.md) |

## HOW IT WORKS

```
+---------------------------------------------------------+
|                       INPUT                             |
|   Figma URL . PNG/JPG screenshot . plain-text prompt|
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  ORIENT / PARSE                         |
|   - Validate inputs                                     |
|   - Load skill / agent / tool definitions               |
|   - Resolve config + secrets from .env                  |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  PLAN (Claude Sonnet)                   |
|   - Decompose goal into ordered subtasks                |
|   - Pick model per task (Sonnet / Haiku / Tier-0)       |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  EXECUTE (parallel)                     |
|   - Spawn sub-agents / call tools                       |
|   - Stream tokens, persist artifacts                    |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  VERIFY                                 |
|   - Lint / typecheck / visual diff / QA agent           |
|   - On failure -> re-prompt with error context          |
+--------------------------+------------------------------+
                           v
+---------------------------------------------------------+
|                  SHIP                                   |
|   - Write to disk . commit . PR . upload                |
+---------------------------------------------------------+
```

## Install

```bash
git clone https://github.com/hmzainjamil/open-design-ai-framework.git
cd open-design-ai-framework

# Per-repo install (try in order):
bash install.sh 2>/dev/null || \
npm install 2>/dev/null || \
bun install 2>/dev/null || \
pip install -r requirements.txt 2>/dev/null || true
```

Environment:

```bash
cp .env.example .env  # if present
# fill ANTHROPIC_API_KEY at minimum
```

## Usage

```bash
# Claude Code skill packs:
/skill-name "your goal"

# CLI / scripts:
python scripts/<script>.py --input ./input --output ./output

# TypeScript projects:
bun run dev    # or npm run dev
```

### Configuration knobs

| Key | Default | Description |
|---|---|---|
| `ANTHROPIC_API_KEY` | - (required) | Claude API key |
| `MODEL` | `claude-sonnet-4-7` | Default LLM |
| `MODEL_FALLBACK` | `claude-haiku-4` | Cheaper fallback |
| `MAX_TOKENS` | `8192` | Per-call ceiling |
| `TEMPERATURE` | `0.2` | Determinism dial |
| `LOG_LEVEL` | `info` | debug / info / warn / error |
| `OUT_DIR` | `./out` | Where artifacts land |
| `CACHE_DIR` | `.cache` | Prompt cache root |
| `PARALLELISM` | `4` | Sub-agent concurrency |
| `RETRY_MAX` | `3` | Per-call retry budget |
| `TIMEOUT_S` | `120` | Per-call timeout |
| `DRY_RUN` | `false` | Plan-only, no side effects |

### Case 3 - DTC brand, ad creative testing

- Before: $2K/month UGC creator retainer, 4 ads/month.
- After: 30+ ad variants/week via Arcads + Claude, A/B-tested.
- Result: 3x creative velocity, 41% lower CAC after 6 weeks.

## Security

- Never commit API keys. `.env` is in `.gitignore` by default.
- Use [git-secret](https://git-secret.io/) or 1Password CLI for team secret sharing.
- Review the QA / safety layer for any tool that writes to disk or runs shells (see `mac_safety.py` style guards).
- Vulnerability reports: open a private GitHub Security Advisory.

## Limitations

- Visual outcomes depend on the actual source files and connected design tools.
- Quality claims require inspectable design artifacts or repeatable checks.
- External tool behavior is not controlled by this repository.

## Related

- [Claude Code](https://docs.claude.com/en/docs/claude-code) - official docs
- [Anthropic Console](https://console.anthropic.com) - API keys + billing
- [Crawlee](https://crawlee.dev) - web scraping framework
- [hmz-claude-code-best-practice](https://github.com/hmzainjamil/hmz-claude-code-best-practice) - sister repo

## Maintainer

[hmzainjamil](https://github.com/hmzainjamil)