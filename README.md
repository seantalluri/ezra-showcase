# Ezra

**Private study-to-pulpit workspace for pastors.**

**Live:** https://sermon.work  
**Source:** Private  
**Stage:** Active

> AI assists the work. The pastor owns the message.

## What Ezra Is

Ezra is a pastor-centered research and sermon-preparation workspace designed to support the path from study to preaching without replacing pastoral judgment.

It brings together research, Scripture handling, sermon drafting, a pastor library, rich editing, AI-assisted workflows, and a production-grade evaluation system for deciding which models should be trusted for which stages of the sermon pipeline.

## Product Surface

- Sermon research and manuscript preparation
- Pastor-owned library and study materials
- Scripture-centered workflows
- Rich-text sermon editing
- AI-assisted research and drafting
- Multi-provider AI architecture
- Stage-specific model routing
- Golden evaluation sets and regression harnesses
- Blind pastor review and human promotion gates
- Pastor vetting and access controls
- Progressive web application support
- Export and presentation-oriented workflows

## AI Architecture Direction

Ezra's architecture is designed around a reviewable pipeline rather than a single opaque prompt.

```mermaid
flowchart LR
    B[Pastor brief] --> T[Canonical text]
    T --> E[Evidence packet]
    E --> S[Sermon strategy]
    S --> D[Drafting]
    D --> R[Independent review]
    R --> V[Verification & evals]
    V --> P[Pastor review]
    P --> F[Prepared / preached]
```

The architecture emphasizes evidence packets, claim-aware drafting, deterministic Scripture verification, independent model review, versioned model/prompt behavior, explicit draft → prepared → preached lifecycle states, and human approval before promotion.

## LLM Evaluation & Model Selection

One of Ezra's strongest engineering layers is its **versioned model-evaluation system**. Model selection is treated as an experimental and governance problem—not as a preference for whichever model is newest or largest.

### Stage-specific model routing

The sermon pipeline evaluates models at distinct stages such as:

- outline / strategy formation;
- manuscript drafting;
- independent review;
- revision;
- factual and grounding audit.

The routing matrix supports multi-provider combinations and evaluates the marginal value of frontier models at individual stages rather than assuming a single model should perform every task.

### Controlled experimental design

The evaluation harness freezes research artifacts, prompt versions, pastor context, and sermon briefs while changing one critical-stage variable at a time. Scored runs disable provider fallback, record requested and resolved models, preserve critical failures in the sample, and enforce explicit budget ceilings.

That makes model comparisons reproducible instead of anecdotal.

### Golden sets

Ezra maintains multiple versioned golden-evaluation layers:

- an app-wide agent golden set covering unsupported factual claims, excessive agency, prompt injection, secret handling, and interpretive honesty;
- pastor-authored golden sermons used as authoritative references for voice, sermon form, structure, pastoral movement, application density, and delivery pattern;
- benchmark sermon cases spanning multiple sermon types, biblical genres, and risk categories.

Golden sermons are intentionally **not treated as factual ground truth**. Their voice and structure can be authoritative while lexical, historical, geographical, quotation, or interpretive claims are independently audited.

### Multi-layer grading

Candidate outputs are evaluated using a combination of:

1. deterministic checks;
2. independent model judges from different providers;
3. weighted quality and grounding rubrics;
4. critical veto graders;
5. blind pastor review;
6. pastor UAT before production promotion.

A missing or malformed judge result blocks promotion rather than silently lowering the evidence bar.

### Promotion gates

A candidate route must satisfy explicit quality, grounding, pastoral-rating, regression, cost/quality, and rollback requirements before it can become a default route.

The system supports a progression conceptually similar to:

```text
candidate → evaluated → pastor UAT → shadow / controlled route → production
```

while retaining the current production route as a rollback path.

## A Result That Changed the Architecture

The benchmark produced an important finding: **the most expensive all-frontier configuration was not the best route.**

For the Main sermon benchmark, an economical stage-specific cascade scored **89.10**, had **zero critical failures**, received pastor-review-ready judgments from both independent judges, and outperformed the all-frontier control.

The winning pattern used stronger models where they added measurable value and lower-cost independent models for routine review and audit, with escalation only when ambiguity or theological disagreement warranted it.

That result changed the product architecture from a simplistic “premium model everywhere” strategy to **sermon-type- and stage-specific model routing**.

## Evaluation Safety & Reproducibility

The harness also incorporates production-minded controls:

- hard dollar budgets for paid model experiments;
- checkpointing so valid judgments are reused after interrupted runs;
- no production database mutations during benchmark runs;
- provider failures preserved as failed eval outcomes;
- blind variant labels for human review;
- cross-provider judges separated from the writer where possible;
- randomized comparison ordering;
- retained ties instead of forced winners;
- trace IDs, token usage, cost, latency, and fallback state recorded locally;
- privacy-minimized hosted traces that omit prompts, retrieved evidence, and manuscripts;
- explicit kill switches and rollback routes.

## Quality Gates Beyond LLM Evals

Ezra's CI also treats quality as a release contract. The repository runs backend tests across multiple Python versions, dependency audits, compile checks, automated safety/migration/agent tests, frontend tests, production builds, and release identity recording before a build is considered verified.

## Public-Safe Technology Surface

- React / Vite
- Python / FastAPI
- Supabase
- Vector retrieval infrastructure
- Multi-provider AI integrations
- LLM evaluation harnesses
- Deterministic + model-graded evaluation
- Human-in-the-loop UAT
- Model routing and policy registry
- Trace/cost observability
- Rich-text editing and document-generation tooling
- Vercel + Railway deployment model

## Design Principles

### Pastor authority is non-delegable
AI can research, suggest, organize, draft, critique, and evaluate. It does not become the preacher.

### Scripture handling should be mechanically checkable
Quoted Scripture and references should be validated independently of generated prose wherever possible.

### Claims should be traceable
A factual statement supported by evidence is materially different from an unsupported one.

### Evaluation belongs in the product lifecycle
Model quality should be measured before release, not inferred from one impressive output.

### Bigger is not automatically better
Models are selected by measured task performance, grounding, cost, latency, and pastoral usefulness—not brand hierarchy.

### Promotion must fail closed
Missing judges, critical grounding failures, malformed outputs, or unmet pastor-UAT thresholds block promotion.

### Local product permissions remain local
Suite-level identity or eligibility should not silently become Ezra-level permission to perform sensitive actions.

## Development Activity

![Ezra private activity](https://raw.githubusercontent.com/seantalluri/portfolio-metrics/main/metrics/ezra.svg)

The badge publishes aggregate activity only. It does not expose commit messages, diffs, branches, SHAs, authors, filenames, or source code.

## What Is Intentionally Not Public

- Application source code
- Production schemas and migrations
- Provider credentials and internal endpoints
- Proprietary prompts and full evaluation datasets
- Pastor manuscripts and private evidence
- Production routing implementation details that would create operational risk
- Security-sensitive implementation details

## Skills Demonstrated

`AI product architecture` · `LLMOps` · `model evaluation` · `golden datasets` · `eval harness design` · `multi-provider orchestration` · `model routing` · `human-in-the-loop systems` · `AI governance` · `cost/quality optimization` · `prompt/version governance` · `grounding & factuality evaluation` · `observability` · `experiment design` · `release gating` · `rollback design`

## My Role

Product strategy · system architecture · AI architecture · evaluation strategy · model-routing policy · UX direction · implementation · governance · safety boundaries · production operations

---

**Private implementation. Public architecture. Measured AI quality. Pastor-owned outcome.**