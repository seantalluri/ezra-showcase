# Ezra

**Private study-to-pulpit workspace for pastors.**

**Live:** https://sermon.work  
**Source:** Private  
**Stage:** Active

> AI assists the work. The pastor owns the message.

## What Ezra Is

Ezra is a pastor-centered research and sermon-preparation workspace designed to support the path from study to preaching without replacing pastoral judgment.

It brings together research, Scripture handling, sermon drafting, a pastor library, rich editing, and AI-assisted workflows inside a system where the pastor remains responsible for the final message.

## Product Surface

- Sermon research and manuscript preparation
- Pastor-owned library and study materials
- Scripture-centered workflows
- Rich-text sermon editing
- AI-assisted research and drafting
- Multi-provider AI architecture
- Pastor vetting and access controls
- Progressive web application support
- Export and presentation-oriented workflows

## AI Architecture Direction

Ezra's evolving architecture is designed around a reviewable pipeline rather than a single opaque prompt.

```mermaid
flowchart LR
    B[Pastor brief] --> T[Canonical text]
    T --> E[Evidence packet]
    E --> S[Sermon strategy]
    S --> D[Drafting]
    D --> R[Editorial review]
    R --> V[Verification & evals]
    V --> P[Pastor review]
    P --> F[Prepared / preached]
```

The long-term design emphasizes evidence packets, claim-aware drafting, independent evaluation, deterministic Scripture verification, versioned model/prompt behavior, and explicit draft → prepared → preached lifecycle states.

Not every architectural phase shown here is represented as fully production-complete today. This section describes the direction of the system and the standards guiding implementation.

## Public-Safe Technology Surface

- React / Vite
- Python / FastAPI
- Supabase
- Vector retrieval infrastructure
- Multi-provider AI integrations
- Rich-text editing and document-generation tooling
- Vercel + Railway deployment model

## Design Principles

### Pastor authority is non-delegable
AI can research, suggest, organize, and draft. It does not become the preacher.

### Scripture handling should be mechanically checkable
Quoted Scripture and references should be validated independently of generated prose wherever possible.

### Claims should be traceable
A factual statement supported by evidence is materially different from an unsupported one.

### Evaluation belongs in the product lifecycle
Model quality should be tested before release, not inferred from one good-looking output.

### Local product permissions remain local
Suite-level identity or eligibility should not silently become Ezra-level permission to perform sensitive actions.

## Development Activity

![Ezra private activity](https://raw.githubusercontent.com/seantalluri/portfolio-metrics/main/metrics/ezra.svg)

The badge publishes aggregate activity only. It does not expose commit messages, diffs, branches, SHAs, authors, filenames, or source code.

## What Is Intentionally Not Public

- Application source code
- Production schemas and migrations
- Provider credentials and internal endpoints
- Proprietary prompts and evaluation datasets
- Pastor data, sermon content, or private evidence
- Security-sensitive implementation details

## My Role

Product strategy · system architecture · AI architecture · UX direction · implementation · evaluation strategy · governance · production operations

---

**Private implementation. Public architecture. Pastor-owned outcome.**