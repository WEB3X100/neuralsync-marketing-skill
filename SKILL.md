---
name: neuralsync-marketing-arsenal
description: Evaluate and route NeuralSync marketing work to a curated open-source tool, producing a least-privilege decision packet before any clone, install, authentication, publishing, messaging, CRM change, spend, or deployment.
---

# NeuralSync Marketing Arsenal

Use this skill when NeuralSync needs to choose or evaluate a marketing, distribution, analytics, content, research, or workflow tool.

This is a routing and evaluation skill, not authority to install software or operate external accounts. Default to draft-only work.

## Operating Boundaries

- Use **NeuralSync** as the active operating-system brand. Do not introduce retired alternate-brand naming.
- Start from the job to be done, not from a preferred tool.
- Select at most one primary candidate per job. Name an alternative only when a real constraint justifies comparison.
- Prefer a link and evaluation packet over cloning a repository.
- Treat publishing, email sending, CRM mutation, analytics writes, credentials, customer data, spend, and production deployment as consequential actions requiring explicit human approval.
- Never infer approval for one consequential action from approval for another.
- Do not use client names, proof, private data, or testimonials unless the user supplies them for the task and confirms their use.

## Candidate Map

| Job | Primary candidate | Alternative or later option | Default posture |
| --- | --- | --- | --- |
| Social planning and scheduling | `gitroomhq/postiz-app` (AGPL-3.0) | `inovector/mixpost` (MIT) | Evaluate only; no account connection or publishing |
| Newsletter and mailing lists | `knadh/listmonk` (AGPL-3.0) | `useplunk/plunk` for application-triggered email | Draft lists and templates; no send |
| Full marketing automation | `mautic/mautic` (GPL-3.0-or-later) | — | Later-stage reference; operationally heavy |
| CRM | `twentyhq/twenty` (mixed AGPL/MIT/enterprise-marked portions) | — | Read-only evaluation; no customer mutation |
| Privacy-first analytics | `umami-software/umami` (MIT) | `plausible/analytics` (AGPL-3.0) | Read-only first |
| Experimentation | `growthbook/growthbook` (MIT core with enterprise directories) | — | Design experiments before activation |
| SEO rank tracking | `towfiqi/serpbear` (MIT) | — | Read-only evaluation after keywords exist |
| Web quality audits | `GoogleChrome/lighthouse` (Apache-2.0) | — | Read-only audits |
| Content hub or CMS | `payloadcms/payload` (MIT) | `strapi/strapi` (MIT community; separate enterprise terms) | Local evaluation; no public deploy |
| Editorial publication | `TryGhost/Ghost` (MIT) | — | Draft-only evaluation |
| Transcription | `openai/whisper` (MIT) | — | Authorized media only |
| Reproducible image workflows | `Comfy-Org/ComfyUI` (GPL-3.0) | — | Isolated evaluation; review model licenses too |
| Public-web research extraction | `unclecode/crawl4ai` (Apache-2.0) | `firecrawl/firecrawl` (AGPL-3.0) | Public, read-only research; obey site terms |
| Browser and campaign QA | `microsoft/playwright` (Apache-2.0) | — | Local or staging validation; no production mutation |
| Workflow automation | `activepieces/activepieces` (MIT core with separately licensed enterprise code) | `windmill-labs/windmill` for engineering-owned workflows | No production activation |

Keep these outside the default open-source stack pending separate terms review:

- `remotion-dev/remotion`: eligibility-based commercial terms may apply.
- `n8n-io/n8n`: source-available Sustainable Use License, not a standard OSI open-source license.

License labels are an operational aid, not legal advice. Re-check the upstream repository and exact pinned revision before adoption.

## Evaluation Workflow

1. State the marketing job, desired outcome, audience, and success signal.
2. Identify data involved, credentials required, external actions, deployment surface, and potential spend.
3. Choose one primary candidate from the map. Compare an alternative only when the primary conflicts with a stated requirement.
4. Verify current upstream license, release activity, security guidance, and deployment requirements from authoritative sources.
5. Produce the decision packet below.
6. Stop for approval before cloning, installing, authenticating, sending, publishing, mutating data, spending, or deploying.

## Required Decision Packet

```markdown
## Marketing Tool Evaluation

- Job to be done:
- Recommended candidate:
- Why it fits:
- Upstream repository:
- Version or commit to pin:
- License posture:
- Data involved:
- Credentials required:
- External actions:
- Deployment surface:
- Security and operational risks:
- Safer fallback:
- Approval required for next step:
```

## After Approval to Evaluate Locally

- Clone into an isolated evaluation directory, never into the active marketing workspace.
- Pin a release or commit instead of using a moving default branch.
- Grant no production credentials during evaluation.
- Review dependencies, secret handling, license obligations, network listeners, telemetry, and update behavior before execution.
- If code or assets are copied, record source URL, commit, license, copied files, and local changes in `VENDORED.md`.
- Do not install competing tools for the same job without an explicit comparison decision.

Approval to evaluate locally does not authorize public distribution or production operation.
