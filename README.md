# Fusion Agent Flow Architect

A reusable Codex skill for designing evidence-aware Oracle Fusion Cloud Applications integration flows for Oracle AI Agent Studio. It turns business use cases, process descriptions, requirements, and screenshots into an auditable design: first the appropriate AI Studio pattern, then an end-to-end API flow, implementation safeguards, and a BI Publisher alternative where useful.

The skill is deliberately conservative. It distinguishes documented or pod-verified facts from plausible candidates and unknowns, and it never turns a UI label, remembered convention, or guessed naming pattern into an Oracle API or data-model assertion.

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

Typical requests include designing a read/update integration for a Fusion business process, mapping a screenshot-driven requirement to candidate APIs, deciding between an AI Workflow, AI Agent Team, and Agentic Application, or proposing a BI Publisher reporting fallback. The skill covers identifier resolution, supporting and child resources, mutation controls, security, failure recovery, release/configuration sensitivity, and a staged testing plan.

## Design and verification philosophy

The skill selects the implementation pattern before it designs APIs. API designs are sequences, not disconnected resource names: every call accounts for its inputs, extracted output, branching, and verification state. REST sufficiency is assessed explicitly; SOAP, ESS, workflow/action interfaces, and BI Publisher are considered only where relevant.

Production-oriented BI Publisher SQL is supplied only when documented sources, columns, and joins are sufficiently verified. Otherwise the skill labels it **Assumption-Based Draft SQL** and records every assumption and required documentation/pod check. Mutation flows start with the simplest safe `GET`, use sandbox/test data, and finish by verifying the business result through the applicable UI, REST, report, workflow, ESS, or downstream outcome.

## Use in Codex

Invoke `$fusion-agent-flow-architect` and provide the use case, known Fusion module and release, target environment, available documentation or API evidence, and whether read-only or mutation behavior is intended. Attach screenshots when relevant. The skill asks focused questions only when an answer would materially alter the business object, API flow, payload, data source, or security model; otherwise it proceeds with clearly marked assumptions.

## Maintenance

Keep the skill in review like source code: make focused commits, describe the behavior change, and validate YAML/frontmatter after edits. Prefer links or evidence references supplied in the request over embedding unverified Oracle catalogs. Update instructions when supported product behavior changes, and preserve the Confirmed/Candidate/Unknown boundary in every change. Before publishing to GitHub, initialize a repository if needed, review `git diff`, and ensure no environment-specific data, credentials, or customer artifacts are included.
