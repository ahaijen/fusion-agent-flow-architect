# Fusion Agent Flow Architect repository

This repository contains the `fusion-agent-flow-architect` Codex skill. Use that skill for Oracle Fusion Cloud Applications integration-design requests that involve Oracle AI Agent Studio patterns, REST/API flows, BI Publisher alternatives, or implementation testing.

Oracle-specific facts must be classified as **Confirmed**, **Candidate**, or **Unknown**. Do not infer endpoints, fields, child resources, database objects, joins, operations, or privileges from naming conventions or UI labels. Mutation-capable scenarios must begin with read-only testing and require explicit verification before changes are recommended for production. Do not create a Fusion AI Studio handoff prompt until required Fusion and external APIs are live-tested in a user-authorized environment and the process is simulated end-to-end; writes need fresh explicit approval for the exact operation and test record.

Use `docs.oracle.com` as the authority for Fusion REST APIs and AI Agent Studio capabilities. Do not propose custom interfaces or capabilities outside the documented Fusion AI Agent Studio platform.

The skill's final deliverable is clear, copyable instructions for a separate Fusion AI Studio Codex session, never an AI Studio JSON file. REST request-payload examples may be included only as explanatory API-design snippets where evidence permits.

Decompose each use case into small, independently testable increments. Start with a useful query-only path by default, and select the lowest-complexity documented AI Studio build unit that solves the confirmed requirement. Honor an explicit user request for broader first-iteration scope or another documented build approach while retaining documented-capability, live-validation, and operation-specific mutation-approval gates.
