# NeuralSync Marketing Arsenal

A human-governed routing skill for choosing, evaluating, and safely adopting open-source marketing and distribution tools for **NeuralSync**.

The skill helps an agent answer:

1. What marketing job are we trying to complete?
2. Which single open-source tool is the best first candidate?
3. What data, credentials, permissions, licenses, and operational risks are involved?
4. What can be prepared safely now?
5. What requires explicit human approval?

It does **not** grant authority to clone, install, authenticate, publish, message customers, change CRM data, spend money, or deploy software.

## Start here

- **Humans:** read [Human quick start](#human-quick-start), then review the approval boundary before enabling the skill.
- **Agents:** read [Agent operating contract](#agent-operating-contract), then follow the workflow in [SKILL.md](./SKILL.md).
- **OpenMaus users:** import the repository root:

```text
https://github.com/WEB3X100/neuralsync-marketing-skill
```

## What this repository contains

| File | Purpose |
| --- | --- |
| [`SKILL.md`](./SKILL.md) | Executable agent instructions, candidate map, evaluation workflow, and required decision packet |
| [`README.md`](./README.md) | Human onboarding, agent interface, memory design, and governance guidance |
| [`LICENSE`](./LICENSE) | MIT license for this repository |

The upstream tools listed by the skill keep their own licenses. Always verify the exact upstream revision and terms before adoption.

## Human quick start

1. Import the repository root into OpenMaus.
2. Review the imported `SKILL.md` before enabling it.
3. Keep the skill in evaluation mode until a named human approves a specific next action.
4. Give the agent a job, outcome, audience, constraints, and success signal.
5. Expect a **Marketing Tool Evaluation** packet—not an automatic installation.
6. Approve or reject each consequential step separately.

A useful first test is:

> Evaluate an open-source tool for scheduling NeuralSync social content. Do not clone, install, authenticate, publish, or connect an account. Return the required decision packet and stop for approval.

### Human approval checklist

Before approving the next step, confirm:

- the proposed tool matches the actual job;
- its current license and upstream activity were checked;
- the proposed version or commit is pinned;
- data, credentials, network access, and deployment surface are named;
- the requested action is narrow and reversible;
- no customer communication, public publishing, CRM mutation, spend, or production change is bundled into the approval;
- a safer fallback is documented.

Approval to evaluate locally is not approval to deploy, connect production credentials, or operate a live channel.

## Agent operating contract

When this skill is active, the agent must:

1. Treat **NeuralSync** as the only public-facing product brand.
2. Begin with the job to be done, not a favorite tool.
3. Recommend one primary candidate unless a real constraint requires comparison.
4. Verify current facts from authoritative upstream sources before recommending adoption.
5. Prefer a decision packet and upstream link over cloning software.
6. Default to read-only research and draft-only output.
7. Name every credential, dataset, external action, deployment surface, and potential cost.
8. Stop for explicit human approval before any consequential action.
9. Interpret approval narrowly; one approved action does not authorize another.
10. Never place secrets, private customer data, unsupported claims, or unapproved testimonials in memory, content, logs, or repositories.

### Inputs the agent should request or infer conservatively

| Input | Example |
| --- | --- |
| Job | Schedule launch content across approved social channels |
| Outcome | Maintain a two-week publishing queue |
| Audience | Operations leaders at growing service businesses |
| Success signal | Approved posts scheduled on time with no policy violations |
| Constraints | Self-hostable, low operational overhead, no production credentials during evaluation |
| Data sensitivity | Public content only; no customer records |
| Approval owner | Named NeuralSync founder or delegated operator |

If an omitted input would materially change risk or tool selection, the agent should ask for it. Otherwise, it should state a conservative assumption and continue with a draft evaluation.

### Required output

Every recommendation must use the decision packet defined in [`SKILL.md`](./SKILL.md). A valid packet names the candidate, upstream source, pinned revision, license posture, data, credentials, external actions, deployment surface, risks, fallback, and exact approval required next.

## How OpenMaus memory should be organized

OpenMaus uses two memory layers:

- **`MEMORY.md`** is compact, durable context that loads into every conversation.
- **Topic notes** are separate files under `memory/<topic>.md`. They hold deeper subject-specific context and are recalled or read when relevant.

The **Topic name** field in the Memory panel creates one of those topic files. Use a stable subject name—not a one-off task, campaign date, or chat title.

### Keep in `MEMORY.md`

Only facts and rules the marketing agent needs on nearly every turn:

- NeuralSync is the only public-facing brand.
- NeuralSync is an AI-powered operating system for businesses.
- The agent defaults to draft-only work.
- Publishing, sending, account connection, spend, CRM mutation, and deployment require explicit human approval.
- Claims, customer names, proof, and testimonials require an approved source.
- Secrets and credentials never belong in memory.

Keep this file concise because it is loaded every turn.

### Recommended topic notes

Start with a small set and add others only when real durable context exists.

| Topic name | What belongs there |
| --- | --- |
| `brand-and-positioning.md` | Approved positioning, category language, value propositions, prohibited or retired naming |
| `audiences-and-icp.md` | Ideal customer profiles, buyer roles, pains, triggers, objections, and exclusions |
| `products-and-offers.md` | Current capabilities, packaging, offers, calls to action, and availability constraints |
| `voice-and-style.md` | Tone, vocabulary, channel-specific writing rules, examples, and anti-patterns |
| `approved-claims-and-proof.md` | Approved evidence, citations, metrics, case studies, and claim expiration or review dates |
| `channels-and-distribution.md` | Owned and approved channels, channel goals, publishing constraints, and access owners |
| `campaigns-and-experiments.md` | Active hypotheses, audiences, variants, success measures, status, and decisions |
| `content-calendar-and-cadence.md` | Durable publishing cadence and recurring themes—not short-lived task status |
| `tool-decisions-and-integrations.md` | Evaluated tools, pinned revisions, license notes, approvals, rejected options, and integration owners |
| `lessons-and-retrospectives.md` | Verified outcomes, failed assumptions, reusable lessons, and follow-up decisions |

Do not create all ten just to fill the panel. A good initial set is:

1. `brand-and-positioning.md`
2. `audiences-and-icp.md`
3. `voice-and-style.md`
4. `channels-and-distribution.md`
5. `tool-decisions-and-integrations.md`

### Topic note template

OpenMaus can use frontmatter to show a clearer topic index and improve recall through aliases.

```markdown
---
title: Brand and positioning
description: Approved NeuralSync category language, value propositions, and naming boundaries.
aliases:
  - brand
  - positioning
  - messaging
  - category
---

# Brand and positioning

## Approved

- NeuralSync is the only public-facing brand.
- NeuralSync is an AI-powered operating system for businesses.

## Avoid

- Retired internal or alternate product names in public material.
- Unsupported superlatives, outcomes, or market claims.

## Sources and review

- Owner:
- Approved source:
- Last reviewed:
- Review trigger:
```

### Memory quality rules

- Store durable facts, decisions, and reusable context—not raw transcripts.
- Include an owner, source, and review date for claims that can become stale.
- Mark superseded decisions instead of silently rewriting history.
- Prefer one canonical topic over near-duplicate topics.
- Use aliases for words humans and agents may use to find the same subject.
- Keep temporary task state in the task or campaign system, not long-term memory.
- Never store passwords, API keys, access tokens, private keys, or unnecessary personal data.
- Treat memory as context, not authority: an external action still requires the permissions and approval stated in the skill.

## Typical workflow

```text
Human goal
   ↓
Clarify job, audience, constraints, and success signal
   ↓
Select one primary candidate from the arsenal
   ↓
Verify upstream license, activity, security guidance, and deployment needs
   ↓
Return the Marketing Tool Evaluation packet
   ↓
Human approves one narrow next action
   ↓
Perform only that action and report the result
```

## Maintenance

Review the skill when:

- a candidate repository changes license or ownership;
- a project becomes inactive, archived, compromised, or materially harder to operate;
- NeuralSync changes positioning, channels, or approval policy;
- a repeated marketing job lacks a suitable candidate;
- an approved evaluation produces a reusable lesson.

When changing the arsenal:

1. verify upstream facts;
2. explain why the candidate is being added, replaced, or removed;
3. update the candidate map in `SKILL.md`;
4. preserve the least-privilege approval boundary;
5. record important adoption decisions in `tool-decisions-and-integrations.md`.

## License

This repository is available under the [MIT License](./LICENSE). Licenses and terms for referenced projects remain those of their respective owners.
