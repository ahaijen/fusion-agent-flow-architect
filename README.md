# Fusion Agent Flow Architect

A reusable Codex skill for designing evidence-aware Oracle Fusion Cloud Applications integration flows for Oracle AI Agent Studio. It turns business use cases, process descriptions, requirements, and screenshots into an auditable design: first a functional solution hypothesis and appropriate AI Studio pattern, then—when evidence and audience needs justify it—an end-to-end API flow, implementation safeguards, and a BI Publisher alternative.

The skill is deliberately conservative. It distinguishes documented or pod-verified facts from plausible candidates and unknowns, and it never turns a UI label, remembered convention, or guessed naming pattern into an Oracle API or data-model assertion.

It is also platform-bound: it proposes only capabilities documented for the applicable Fusion AI Agent Studio release. `docs.oracle.com` is the authority for APIs and product capabilities; the Oracle learning path and Fusion AI Studio repository provide useful, release-sensitive context but do not override Oracle documentation. The skill never designs a custom web UI, standalone frontend, or unsupported interaction in place of documented Agentic Application capabilities.

## Contents

```text
.
├── AGENTS.md
├── README.md
├── .gitignore
└── skills/
    └── fusion-agent-flow-architect/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## What it supports

Typical requests include turning a functional business problem into a presales solution hypothesis, designing a read/update integration for a Fusion business process, mapping a screenshot-driven requirement to candidate APIs, choosing the lowest-complexity documented build unit—Workflow with a single Agent node, Workflow with a Multi Agent node, Deterministic Agent workflow, or Agentic Application—or proposing a BI Publisher reporting fallback. The skill does not add nodes or agents merely because they are available; a requester can explicitly choose another documented approach, subject to the same evidence and safety gates. It covers discovery questions, proof-of-value scope, identifier resolution, supporting and child resources, mutation controls, security, failure recovery, release/configuration sensitivity, prompt specifications, and a staged testing plan.

## Design and verification philosophy

The skill selects the implementation pattern before it designs APIs. It begins in a business-friendly Discovery / Presales Brief lane by default and can move through Solution Design to Technical Handoff. It decomposes each use case into small, independently verifiable increments: prove a useful query-only outcome first, then add only the next dependency required to advance the business result. A requester can explicitly choose a broader first iteration, including a documented update capability, but that scope remains bounded and every live write still requires prerequisite validation and fresh operation-specific approval. API designs are sequences, not disconnected resource names: every call accounts for its inputs, extracted output, branching, and verification state. REST sufficiency is assessed explicitly; SOAP, ESS, workflow/action interfaces, and BI Publisher are considered only where relevant.

When an LLM, Agent, or Multi Agent component is needed, the handoff uses a CRAFT-derived prompt specification: context, role, action, format, target/tone, guardrails, and an evaluation plan. Prompts remain evidence-grounded, use only approved tools/data mappings, surface uncertainty, and are refined against measurable quality and safety criteria before acceptance.

For every substantive investigation, the skill refreshes Oracle's live Fusion AI Agent Studio Learning Path and records the retrieval date and relevant current topics. That source informs current enablement alignment only; it never substitutes for documentation or target-pod verification of a REST resource, field, tool behavior, role, or permission.

## Live validation and implementation handoff

The skill does not hand a design to Fusion AI Studio solely from documentation or mock data. Before it produces a copyable implementation prompt, every required Fusion REST and external API must be tested against a user-authorized live environment, and the defined business process must be simulated end-to-end with representative authorized test data. The test plan uses a scenario matrix for happy paths, exception paths, ambiguity, lookup/master-data resolution, pagination, validation, and recoverable failures. It carries identifiers only from real responses into downstream calls, avoids hard-coded master data unless confirmed stable, and updates the proposed contract from test evidence before handoff. Read-only validation is the default. Any write, submit, action, workflow trigger, or external write requires fresh explicit approval for the exact operation, environment, and test record.

When the gate passes, the skill emits a complete **Fusion AI Studio Handoff Prompt** for a separate Codex session using Oracle's [Fusion AI Studio repository](https://github.com/oracle/fusion-ai-studio). The prompt includes only verified, non-secret contracts and evidence, and tells the receiving session to select the release branch matching the verified Fusion release, inspect the current skill instructions, and preserve the tested approval and safety boundaries. It directs the receiving session to create documented Business Objects for all Fusion interactions, using live-validated REST contracts only as supporting evidence; it never asks that session to create or invoke Fusion REST tools or direct REST calls. This skill never generates or proposes an AI Studio JSON file: its handoff is clear implementation guidance. If any API or branch is untested or fails, the skill emits a remediation plan instead of a handoff prompt.

Production-oriented BI Publisher SQL is supplied only when documented sources, columns, and joins are sufficiently verified. Otherwise the skill labels it **Assumption-Based Draft SQL** and records every assumption and required documentation/pod check. Mutation flows start with the simplest safe `GET`, use sandbox/test data, and finish by verifying the business result through the applicable UI, REST, report, workflow, ESS, or downstream outcome.

## Use in Codex

Invoke `$fusion-agent-flow-architect` and describe the business problem in your own words. Useful context includes the actor, trigger, desired outcome, approval points, exceptions, known Fusion module and release, target environment, and success measures. Attach screenshots when relevant. The skill uses functional questions first, then asks for technical evidence only when it materially changes the business object, API flow, payload, data source, or security model. Request a **Technical Handoff** when you want the full API and BIP design.

## Maintenance

Keep the skill in review like source code: make focused commits, describe the behavior change, and validate YAML/frontmatter after edits. Prefer links or evidence references supplied in the request over embedding unverified Oracle catalogs. Update instructions when supported product behavior changes, and preserve the Confirmed/Candidate/Unknown boundary in every change. Before publishing to GitHub, initialize a repository if needed, review `git diff`, and ensure no environment-specific data, credentials, or customer artifacts are included.
