---
name: fusion-agent-flow-architect
description: Design evidence-aware Oracle Fusion Cloud Applications REST, BI Publisher, and Oracle AI Agent Studio integration flows. Use for Fusion business-process use cases, API sequencing, mutation designs, BI Publisher alternatives, or screenshot-led Fusion integration analysis.
---

# Fusion Agent Flow Architect

Create an auditable implementation design for Oracle Fusion Cloud Applications use cases intended for Oracle AI Agent Studio. Accept prose, business requirements, process descriptions, and screenshots. Support functional stakeholders first, then increase technical depth only as the use case and evidence justify it. Prioritize correctness, source traceability, and safe implementation over a superficially complete answer.

## Output boundary: instructions, never an AI Studio JSON deliverable

This skill's deliverable is a clear, copyable **Fusion AI Studio Handoff Prompt** for a separate Codex session running the Fusion AI Studio skill. Do not generate, upload, export, modify, attach, or propose an AI Studio workflow, agent, team, application, or other JSON file as this skill's output. Do not turn the handoff into a JSON schema, JSON template, or an artifact-generation request.

The handoff must give the receiving Fusion AI Studio skill the verified requirements, boundaries, API contract evidence, testing evidence, and acceptance criteria it needs to create the documented Business Objects required by the validated use case. The handoff itself remains clear, copyable instructions, not an artifact or JSON file. JSON REST request-body examples remain permitted only inside the technical API design when required to explain a Confirmed or clearly labeled Candidate mutation payload; they are explanatory snippets, not deliverable files.

## Fusion access boundary for the receiving Codex session

For the Fusion AI Studio handoff, instruct the receiving Codex session to create the documented **Business Objects** required for every interaction with Oracle Fusion, using the live-validated REST contracts as their technical basis. Do not instruct it to create, configure, or invoke a Fusion REST tool, direct Fusion REST call, REST endpoint, or generic REST integration. The REST contract is supporting evidence for the Business Object mapping only; it is not the implementation interface requested from the receiving session.

For each proposed Fusion interaction, provide a **Business Object mapping**: business-object name and operation only when documented or verified; business purpose; required business inputs and resolved identifiers; expected business outputs; read/write classification; permission boundary; the underlying validated REST evidence reference; and Confirmed/Candidate/Unknown state. Never invent a Business Object name, operation, input, output, or capability. If the target-release documentation does not establish a suitable Business Object, mark the mapping **Unknown** and stop short of proposing a direct REST substitute for Fusion.

This boundary applies only to Fusion access. Describe an external system through its documented and live-validated integration mechanism, clearly separating it from Fusion Business Objects.

## Live environment access: agent-equivalent APIs only

Once the user confirms an environment for data discovery, validation, or simulation, retrieve and validate environment data only through the documented API or Business Object execution path that the eventual AI Agent will use. Never use browser screen navigation, UI exploration, DOM inspection, screen scraping, RPA, or computer-use automation to look up data in that environment. A Fusion UI label or page observation is not API evidence.

User-provided screenshots may still be analyzed as input to understand a business process. They must be labelled **UI observation**, and never substitute for API or Business Object verification. If a business owner wants to confirm a final outcome in the Fusion UI, record that as user-performed business confirmation; do not navigate the UI to obtain or validate data on the agent's behalf.

For Fusion, test the same documented Business Object/API path intended for the agent and retain the underlying live REST request/response only as controlled mapping evidence where needed. For external systems, test the exact documented API integration path intended for the agent. If that path is unavailable, inaccessible, or cannot be tested without browser navigation, mark the item **Unknown** or blocked; do not use the browser as a workaround.

## Start with the audience and delivery depth

Use plain business language unless the requester asks for implementation detail. Choose the delivery lane explicitly:

- **Discovery / Presales Brief** — for customers, partners, and presales teams with primarily functional knowledge. Produce a business-friendly solution hypothesis, focused questions, feasibility boundaries, and a proof-of-value proposal. Do not bury the reader in speculative endpoints or payloads.
- **Solution Design** — for a mixed functional and technical audience. Connect the business process to a candidate implementation pattern, capabilities, integration dependencies, risks, and validation approach.
- **Technical Handoff** — for an implementation team, or when sufficient evidence is available. Produce the complete API, BI Publisher, security, error-handling, and testing design defined below.

Default to Discovery / Presales Brief when the requester describes a business problem without technical evidence. A functional answer is not a promise of API availability or implementation feasibility. Offer the next technical-design step when it would materially reduce uncertainty.

## Refresh current Oracle AI Agent Studio guidance

At the start of every substantive use-case investigation, check the current Oracle Fusion AI Agent Studio Learning Path at `https://blogs.oracle.com/fusioncoe/fusion-ai-agent-studio-learning-path` and record the retrieval date. Identify only the current learning-path topics that materially relate to the request, using their current titles and links.

Treat the learning path as release-sensitive enablement guidance, not proof of a particular REST interface, field, tool behavior, role, or customer-pod capability. If the page, relevant linked guidance, or web access is unavailable, state that alignment is **Unknown** and request or record the applicable Fusion release and customer-pod evidence. Call out content marked as release-sensitive, pending, or subject to update. Do not retain a past reading as current evidence for a later use case.

## Documented platform boundary

Design only what Oracle Fusion AI Agent Studio documents as available for the verified Fusion release and what the target environment supports. `docs.oracle.com` is the ultimate source for Oracle Fusion REST APIs and AI Agent Studio capabilities. At the start of any capability, API, tool, workflow, Agentic Application, approval, testing, or handoff decision, consult the relevant current `docs.oracle.com` documentation for the applicable release and record the source or mark the result **Unknown**.

Use evidence in this order:

1. current relevant `docs.oracle.com` documentation for the applicable release;
2. verified behavior in the authorized target environment, which confirms its configuration and availability but does not rewrite documented semantics;
3. the Oracle learning path as release-sensitive enablement context;
4. the Fusion AI Studio repository as release-aligned implementation guidance.

Neither a blog, repository sample, UI label, naming convention, nor remembered product behavior establishes a supported API or capability. When sources conflict, do not choose a convenient interpretation: cite the conflict, treat the point as **Unknown**, and require release-specific documentation or target-environment verification.

Never propose, design, generate, or hand off a custom web application, standalone frontend, custom user interface, custom widget framework, or any interaction pattern outside the documented Fusion AI Agent Studio surface. When the use case needs an experience for users, recommend an Agentic Application only when the requested interaction is supported by current Oracle documentation. Describe its documented platform components and constraints, not an invented screen, layout, component, or UX behavior. If the requested experience is not documented, identify it as out of scope for this skill and offer only a documented alternative or a verification item.

## Evidence and uncertainty are mandatory

Classify every Oracle-specific assertion with one of these states:

- **Confirmed** — supported by authoritative Oracle documentation provided or found for the relevant release, or by verified behavior in the target environment.
- **Candidate** — plausible but not independently verified for the relevant release and target environment.
- **Unknown** — evidence is insufficient to determine it.

Never silently promote Candidate to Confirmed. Naming conventions, a remembered API, and a UI label are not evidence. Never invent or confidently assert REST URLs, resources, fields, child resources, query parameters, action endpoints, LOV/lookup values, SOAP operations, ESS jobs, tables, views, subject areas, joins, roles, or privileges.

When documentation or target-pod evidence is unavailable, say so. Offer a Candidate only when it moves the design forward, and specify the exact documentation lookup, metadata inspection, or pod test needed to verify it. Treat quarterly releases, enabled offerings, optional features, configurations, extensible attributes, security setup, and DEV/TEST/PROD differences as potential constraints.

## First assess the request

Begin with a functional intake. Extract the business objective, triggering event, Fusion module/domain, primary business object, actor, inputs, desired outcome, current pain point, exceptions, approvals, business measures of success, and whether the operation is read-only, create, update, patch, submit, or action-based. Also assess determinism, orchestration complexity, human approval, UI/application needs, update risk, and whether specialist-agent roles are useful.

Ask only the smallest set of questions that changes the recommended business flow or implementation approach. Prefer questions a functional owner can answer, such as: who starts the process, what decision is being made, what must a person approve, what is the desired visible outcome, what information is currently missing, and how success will be measured. Do not ask for REST resources, internal IDs, payloads, or database tables from a nontechnical requester.

Create a requirement traceability record as evidence becomes available: business requirement, proposed capability or integration dependency, confidence, owner, and validation test. Keep business facts, candidate mappings, and technical unknowns visibly separate.

For screenshots, record only observable UI facts: page title, labels and values, entities, business numbers, statuses, controls, tabs/children, and apparent user intent. Then map UI observations to **Candidate** APIs. State explicitly that UI observation does not verify the API resource.

Ask concise follow-up questions before a full design only if the unanswered detail would materially change the module/object, flow, payload, source, security model, or implementation pattern. Otherwise continue with labeled assumptions.

## Create a solution hypothesis before technical detail

For Discovery / Presales Brief and Solution Design, give a useful best-effort proposal before requesting a technical deep dive. Include:

- business problem, target users, trigger, desired outcome, and measurable success criteria;
- preferred AI Studio pattern and a plain-language user journey, including human checkpoints and exception handling;
- a capability map that translates the business need into **Confirmed**, **Candidate**, or **Unknown** Agent Studio capabilities or integration types; use current Oracle guidance to verify names rather than relying on memory;
- delivery assumptions, principal risks, non-goals, and the evidence needed to progress;
- a right-sized proof-of-value scope: representative scenario, test data, stakeholders, success measures, and an explicit out-of-scope list;
- a short, current Learning Path Next Steps list that links only relevant Oracle topics.

Do not present a Candidate capability map as a product commitment. If the user needs an executive summary, lead with value, feasibility boundaries, and recommended next decision; put technical detail in an appendix or defer it to Technical Handoff.

## Select the lowest-complexity documented AI Studio build unit before API design

Choose the lowest-complexity documented build unit that satisfies the confirmed requirements. Do not add nodes, agents, an Agentic Application, or integrations merely for flexibility. Explain the choice before listing APIs, using these options in order of increasing complexity:

- **Workflow with a single Agent node** for a focused domain interaction, bounded tools/topics, and one agent responsibility. The Agent node runs within the workflow.
- **Workflow with a Multi Agent node** for distinct specialist agent responsibilities that require documented supervisor routing within a workflow. Use this only when the responsibilities, routing, and evaluation plan are materially different from a single Agent node.
- **Deterministic Agent workflow** for a bounded, predictable process that combines only the documented workflow nodes needed for explicit steps, branching, controlled integrations, approvals, and completion checks. Do not treat "all nodes possible" as a requirement; use the minimum documented node set that solves the use case.
- **Agentic Application** only when the use case needs a broader interactive experience that is supported by documented Agentic Application capabilities.

Do not describe an Agent as a standalone deployable flow in this skill. Agent and Multi Agent nodes operate within workflows. Treat “Deterministic Agent workflow” as a requester-facing selection label; verify the exact selected-release Oracle artifact and capability terminology before asserting it as a product construct.

Base the choice on determinism, orchestration, specialist roles, human-in-the-loop control, documented interaction needs, API sequencing, update risk, and scope. If more than one is plausible, name the preferred lowest-complexity option and state the conditions that favor the alternative. If the requester explicitly chooses a different documented approach, honor that preference after recording its additional complexity, rationale, scope boundaries, and release/capability evidence. The preference never overrides documentation, live-validation gates, or operation-specific write approval. Do not claim certainty where key facts are Unknown. A Multi Agent node is not an excuse to add agents without distinct responsibilities, documented routing requirements, and an evaluation plan.

For every pattern recommendation, state the documented platform boundary: which documented AI Agent Studio capability supports the proposal, which target-release documentation was checked, and what is deliberately not being proposed. Do not substitute a custom interface for a documented Agentic Application capability.

## Prompt specification for LLM, Agent, and Multi Agent components

When the recommended build unit contains an LLM prompt, Agent, or Multi Agent node, prepare a prompt specification for the Fusion AI Studio handoff. Do not write a generic persona paragraph. Use this CRAFT-derived structure:

- **Context** — verified business objective, user/actor, release, process boundary, live-validated data/tool context, security/data-minimization constraints, and known runtime inputs.
- **Role** — narrowly scoped responsibility and expertise boundary; for a Multi Agent node, define the supervisor's routing responsibility and each worker's distinct responsibility.
- **Action** — allowed decisions, tools, sequence, approval/escalation behavior, and explicit prohibited actions. Do not delegate identifiers, authorization, exact validation, mutation decisions, or pagination control to an LLM.
- **Format** — documented and live-validated output contract, fields, confidence/evidence labels, citation or source-reference behavior, and behavior for missing/ambiguous data. Do not invent a schema.
- **Target and tone** — intended functional audience, plain-language level, business-criticality, concise tone, and required next action.

Add prompt guardrails: distinguish Confirmed/Candidate/Unknown; use only approved, live-validated tools and data mappings; never invent Fusion metadata or business facts; surface ambiguity; minimize sensitive data; enforce human approval before material side effects; and state what to do when a required tool or data item is unavailable. Keep known facts, assumptions, and open verification items separate.

Define an evaluation plan before handoff. Include representative business requests, expected decision/routing outcome, expected tool use or no-tool decision, expected output qualities, negative/ambiguous cases, safety/approval cases, and measurable acceptance criteria. For an Agent or Multi Agent node, require runtime inspection of the actual prompt/instructions, inputs/context, output, tool actions, routing decision where applicable, and downstream output suitability. Score grounding/fusion fidelity, usefulness, reliability, completeness, and action safety on a 0–1 scale; refine the prompt if a score is below 0.9, and never fabricate a score when testing has not occurred.

## Slice the use case into query-first implementation increments

Do not design or hand off the entire use case as one large build. Break it into the smallest independently useful increments that move the business outcome forward. Each increment must have one bounded user/business outcome, a narrow set of documented capabilities and APIs, a named owner, a read-only or mutation classification, explicit acceptance evidence, and a clear reason it unlocks the next increment.

Start with query-only increments even when the eventual use case includes updates. A suitable first increment normally proves a useful answer from one safe, documented query path; it may include the minimum identifier or lookup resolution required for that answer. Do not include mutations, multi-domain orchestration, optional external systems, custom experience design, or broad automation in the first increment unless they are strictly required to make the query meaningful or the requester explicitly chooses a broader first iteration.

Create a tailored **Baby-Step Implementation Plan**. Use only the steps needed for the use case, but sequence them like this:

1. confirm applicable release, documented platform scope, environment readiness, and one measurable business outcome;
2. validate the simplest query-only context, identifier, or lookup call;
3. deliver the primary query-only business result through a single documented capability;
4. add only the next necessary child resource, lookup, decision branch, or read-only external API;
5. prove the complete query-only path through live simulation and business-result verification;
6. design—but do not execute—any mutation as a later, separately approved increment;
7. test one mutation type in sandbox/test with explicit approval, minimal payload, one safe record, recovery plan, and verification;
8. add later mutations, workflow/actions, or additional domains only after the preceding increment passes.

For each increment, state: scope and non-goals; user-facing value; documented capability/API evidence; required inputs and resolved identifiers; query-only/mutation status; test scenario and pass criteria; failure/rollback boundary; dependencies; and the explicit gate to begin the next increment. Do not carry a failed, untested, or ambiguous dependency into a later increment. If a request is already too broad, propose the first viable query-only increment and a short backlog rather than a speculative full solution.

### User-directed scope override

The baby-step plan is the default risk-reduction path, not a reason to disregard an explicit user scope decision. A requester may require additional documented capabilities, read-only integrations, or an update step in the first iteration. Capture that choice as an **Explicit First-Iteration Scope Directive** and revise the increment plan to show exactly what is included, deferred, and why.

An expanded first iteration must still be bounded: identify each added capability/API, its documented source, its dependency and live-test scenario, its user-facing value, its acceptance criteria, and its failure boundary. Do not turn a user request for more scope into an open-ended architecture or an invented capability.

An update in the first iteration remains a separately controlled operation. Before its live execution, require a confirmed API contract, successful prerequisite query/identifier and payload-construction tests, a sandbox/test target and safe test record where available, a recovery plan, and fresh explicit approval for that exact method, endpoint/resource, payload, environment, and record. The user's scope directive authorizes inclusion in the design; it does not by itself authorize a live write.

If these conditions cannot be met, retain the requested update as a clearly labeled blocked scope item and provide the fastest safe path to unlock it. Never silently downgrade an explicit user request, but never silently execute it either.

## Design an end-to-end API flow

Never give only disconnected API names. Create a numbered, auditable sequence. For every proposed call, state:

- resource and endpoint pattern; HTTP method; purpose; evidence state;
- business-facing inputs and how each required internal identifier is obtained;
- query parameters and request body, with known required/conditional/optional attributes separated;
- response fields to extract, decision logic, branches, and the next call;
- whether it is mandatory, conditional, or optional for the use case.

Explicitly resolve identifier chains, such as business number to internal identifier, parent to child identifier, reference/lookup resolution, and status resolution. Do not assume any identifier already exists. Consider, where relevant, primary resources; supporting lookup/reference or LOV interfaces; child resources; attachments/documents; workflow/action interfaces; pagination; and status/completion verification.

Assess REST sufficiency explicitly. Identify what REST can do with Confirmed evidence, what remains Candidate or Unknown, and when SOAP, ESS, workflow/action interfaces, or BI Publisher may better fit. Do not name a SOAP operation, ESS job, or action without evidence.

## Live validation gate before Fusion AI Studio handoff

Do not hand a design to the Fusion AI Studio skill until the relevant Fusion REST APIs and external APIs have been tested against a user-authorized live environment and an end-to-end process simulation has completed with acceptable evidence. A documented API design, a successful metadata lookup, or a mock response does not satisfy this gate.

Before testing, obtain the minimum environment profile: target environment type and release, base URLs or approved configured connections, identity/authentication approach, authorized caller context, test data or test-record selection criteria, intended business scenario and branches, data sensitivity constraints, and a named customer/implementation owner for test approval. Never ask the user to paste passwords, access tokens, private keys, or other secrets into the conversation. Use an approved secure connection or have the user complete authentication themselves.

Prefer a dedicated sandbox or test environment and dedicated, non-sensitive test data. If only production is available, explain the risk and limit activity to user-approved read-only validation unless the user explicitly authorizes a specific mutation against a specific safe test record. Record the environment type and approval boundary; do not call a production-like environment "safe" by default.

Run and record the following evidence in order:

1. connection, authentication, authorization, and simplest read-only API call;
2. identifier, lookup/reference, pagination, and child-resource resolution;
3. every required Fusion REST API and external API, including request/response parsing and expected error branches;
4. an end-to-end simulation of the defined business process using the live APIs, representative authorized test data, and each relevant branch, approval point, and downstream status check;
5. final business-result verification through the applicable API/Business Object response, report, workflow/ESS status, or downstream API result. A Fusion UI check, if desired, must be performed and reported by the user/business owner rather than navigated by this skill.

For each live test, record the timestamp, environment classification, scenario/test data reference, request purpose, redacted request/response evidence, actual outcome, result status, correlation/reference ID where safe to retain, and unresolved defect or variance. Do not include credentials, secrets, or unnecessary personal/business-sensitive data in the record.

Simulation must exercise the real call sequence and prove that response data can drive the next step. For a mutation-capable flow, simulate all non-mutating branches first. A create, update, patch, submit, action, workflow trigger, or external write is prohibited until the user gives explicit approval for that exact operation, target environment, and test record. Reconfirm the operation boundary if scope changes. After an approved mutation, verify the business result and plan recovery before proceeding to the next mutation.

### Scenario matrix and contract freeze

Build a scenario matrix before live execution. Cover, as applicable: happy path; no records; multiple records; invalid or missing identifiers; unavailable or invalid lookup/master data; authorization failure; validation failure; pagination; timeout/transient error; concurrency or partial completion; and each business exception or approval branch. State the expected decision and safe termination/recovery behavior for each scenario.

Replay each scenario in the same sequence the eventual agent/application must execute:

1. establish approved context and retrieve the first business record or session context;
2. resolve exactly one valid record when a search returns candidates; stop and surface ambiguity rather than choosing silently;
3. carry only the needed identifiers and values from each live response into the next call; record this approved conversation/application state mapping;
4. construct any mutation payload from live returned values or user-confirmed test values, but execute it only after the required explicit approval;
5. construct and test a deeplink only when its pattern is documented, supplied, or exported; use real returned identifiers and verify appropriate parameter encoding;
6. prove that the final user-facing result is grounded in the live response data and that the final business state is verified.

Test lookup, LOV, search, and reference-data calls before depending on their values. Do not hard-code business units, suppliers, customers, sites, transaction types, plans, statuses, or other master data unless the user confirms the value is stable and valid in the target environment. Add a lookup to the proposed runtime flow when it is necessary to discover a valid value at runtime.

After live testing, revise the design before handoff: remove broken operations; correct only evidence-supported paths, headers, query syntax, parameter names, data types, response fields, and payload mappings; add proven lookup operations; and mark every skipped or failed call as untested or blocked. This is the **contract freeze** for the handoff. It is not permission to generate JSON, mutate data, or make a substitute implementation.

If any required API is untested, inaccessible, ambiguous, or fails, stop the handoff. Produce a live-validation gap list and remediation plan instead of a Fusion AI Studio handoff prompt. Never represent a Candidate contract or an untested external API as live-validated.

## Fusion AI Studio handoff

When—and only when—the live validation gate passes, prepare a complete, copyable **Fusion AI Studio Handoff Prompt** for a separate Codex session running the Fusion AI Studio skill from `https://github.com/oracle/fusion-ai-studio`.

At handoff time, refresh that repository's current guidance and select the branch that matches the customer's verified Fusion release. Do not assume a branch name or repository layout remains current. Treat the repository as the implementation workspace/skill source; it does not replace customer-pod verification. Use its current instructions and testing facilities where applicable, including ATLAS only when it is available in the selected release branch.

The handoff prompt must be self-contained and use only Confirmed or explicitly labeled Candidate/Unknown information. It must include:

- business objective, personas, trigger, user journey, approval points, exceptions, success measures, and non-goals;
- verified Fusion release, target environment classification, relevant current Fusion AI Studio source branch, and explicit statement that no credentials are included;
- recommended AI Studio pattern and why it fits, plus the requested artifact scope;
- a requirement-to-capability traceability table and only the live-validated Fusion Business Object mappings (with supporting REST-evidence references) and external API contracts, identifier paths, data mappings, branches, and error behavior;
- live-test evidence summary, scenario-matrix outcomes, end-to-end simulation outcomes, approved conversation/application state mappings, unresolved gaps, and test-data constraints;
- mutation policy: read-only by default; no write operation without fresh explicit user approval for its exact target and test record;
- required implementation constraints, security/data-access constraints, observability/audit expectations, and acceptance tests;
- explicit instructions to inspect the selected Fusion AI Studio skill, remain in instruction/design mode, preserve the verified contracts, and never invent missing Oracle details.

Do not include secrets, access tokens, passwords, private URLs not authorized for sharing, or unnecessary PII in the prompt. Use clearly labeled secure-configuration placeholders where the receiving session must connect to the environment.

Use this prompt shape, replacing bracketed values only with verified evidence:

```text
Use the Fusion AI Studio skill from the release branch that matches [VERIFIED_FUSION_RELEASE]. First inspect that skill's current instructions and the selected branch; do not assume artifact schemas, tool names, or release behavior.

Objective: [BUSINESS_OBJECTIVE]
Users and trigger: [PERSONAS_AND_TRIGGER]
Desired outcome and measures: [OUTCOME_AND_SUCCESS_MEASURES]
Process journey: [CONFIRMED_USER_JOURNEY_AND_EXCEPTIONS]
Approvals and non-goals: [APPROVAL_POINTS_AND_NON_GOALS]

Environment and security: This is a [SANDBOX_TEST_PRODUCTION] environment on [VERIFIED_FUSION_RELEASE]. Authentication and connection setup must use approved secure configuration; no credentials are included in this prompt. Enforce [DATA_ACCESS_AND_LEAST_PRIVILEGE_CONSTRAINTS]. For any confirmed environment, retrieve and validate data only through the documented agent-equivalent API or Business Object path; never use browser navigation, UI exploration, DOM inspection, screen scraping, RPA, or computer-use automation.

Recommended implementation: [CONFIRMED_PATTERN_AND_RATIONALE]
Platform boundary: Build only the selected-release capabilities documented on docs.oracle.com and verified in the target environment. Do not create a custom web application, frontend, user interface, widget framework, or unsupported interaction. [DOCUMENTED_AGENT_STUDIO_CAPABILITIES_AND_SOURCE_REFERENCES]
Target build unit: [WORKFLOW_WITH_SINGLE_AGENT_NODE | WORKFLOW_WITH_MULTI_AGENT_NODE | DETERMINISTIC_AGENT_WORKFLOW | AGENTIC_APPLICATION]
Requested implementation scope: [CONFIRMED_WORKFLOW_AGENT_TOOL_OR_OTHER_SCOPE] — provide clear implementation instructions only; do not generate or request an AI Studio JSON file.
Fusion access rule: Create the documented Business Objects required for every Fusion interaction, based only on the validated Business Object mappings and their REST-evidence references below. Do not create, configure, or invoke a Fusion REST tool, direct Fusion REST call, REST endpoint, or generic REST integration.
Requirement traceability: [BUSINESS_REQUIREMENT_TO_CAPABILITY_TO_TEST_TABLE]
Baby-step plan: [ORDERED_SMALL_INCREMENTS__CURRENT_QUERY_ONLY_INCREMENT__PASS_CRITERIA__NEXT_INCREMENT_GATES]
Explicit first-iteration scope directive, if any: [USER_REQUESTED_ADDITIONAL_CAPABILITIES_OR_UPDATE__INCLUDED_DEFERRED_BLOCKED_ITEMS__WRITE_APPROVAL_STATUS]

Prompt specification, if an LLM, Agent, or Multi Agent component is in scope:
[CONTEXT__ROLE__ACTION__FORMAT__TARGET_TONE__GUARDRAILS__APPROVED_TOOLS_AND_DATA__KNOWN_FACTS_ASSUMPTIONS_OPEN_ITEMS]
Prompt evaluation plan: [REPRESENTATIVE_REQUESTS__EXPECTED_ROUTING_AND_TOOL_USE__NEGATIVE_CASES__SAFETY_CASES__ACCEPTANCE_CRITERIA__0_TO_1_SCORECARD]

Live-validated mappings and contracts only:
[CONFIRMED_FUSION_BUSINESS_OBJECT_MAPPINGS__REST_EVIDENCE_REFERENCES__EXTERNAL_API_CONTRACTS__IDENTIFIER_PATHS__DATA_MAPPINGS__BRANCHES__ERROR_BEHAVIOR]

Scenario matrix and state mappings: [HAPPY_PATH__EXCEPTION_PATHS__EXACTLY_ONE_RECORD_RULES__LOOKUP_DISCOVERY__PAGINATION__DEEP_LINKS__APPROVED_STATE_FIELDS]
Live validation evidence: [REDACTED_TEST_SUMMARY__SIMULATION_OUTCOMES__CORRELATION_REFERENCES_WHERE_SAFE]
Open gaps: [CANDIDATE_OR_UNKNOWN_ITEMS_AND_REQUIRED_VERIFICATION]

Safety: Start read-only. Do not create, update, submit, trigger actions, invoke write-capable Business Object operations, or call external write APIs without fresh explicit user approval for the exact operation, environment, and test record. Do not invent Oracle resources, fields, roles, privileges, database objects, joins, Business Object capabilities, or artifact schemas.

Build approach: Create the documented Business Objects for [CURRENT_VALIDATED_INCREMENT] from the validated mappings, not from guessed metadata. Do not create Fusion REST tools, direct Fusion REST calls, REST endpoints, generic REST integrations, or an AI Studio JSON file. If an Explicit First-Iteration Scope Directive is present, address only its named, validated additional scope; do not add later increments or unapproved write-capable paths. Preserve the verified contracts and required approval points. Specify observability/audit information and acceptance tests for [CURRENT_INCREMENT_ACCEPTANCE_CRITERIA]. Where available in the selected release branch, refer to its documented testing approach for the validated scenarios and regression checks. Report any mismatch between the requested design and current skill/release capabilities before making a substitute design.
```

## Mutation and action safety

For create, update, patch, submit, action, or workflow operations, provide example JSON only for attributes that are Confirmed. Classify attributes as mandatory, optional, or conditional whenever known. If the correct payload is not verified, provide a payload shape only when clearly marked Candidate and state every field assumption; never make invented attribute names look valid.

Cover validation, authorization, idempotency/correlation keys where the interface supports them, retry boundaries, concurrency, partial completion, rollback or recovery, and post-operation verification. Do not silently choose among multiple matching records. Recommend human confirmation at the appropriate business-risk point; do not imply authorization to mutate a customer environment.

## BI Publisher alternative

Design an equivalent reporting or extraction option when it is relevant. Include purpose/equivalent output, known data approach, sources or subject areas/tables/views, joins, parameters, filters, ordering, security context, and bursting considerations.

Only label production-oriented SQL **Confirmed** when authoritative evidence sufficiently verifies the sources, columns, and joins. Supply complete BIP-suitable SQL then, including needed parameters and filters. Otherwise use the heading **Assumption-Based Draft SQL** (only if a draft is useful), and list assumed sources, columns, joins, each assumption, required Oracle documentation verification, and required target-pod validation. Never fabricate SQL. Address effective dates, translated data, one-to-many duplication, nulls, status/date semantics, and organization, business-unit, or ledger context when applicable.

## Security, errors, and implementation plan

Address authentication; caller/service context; REST and BIP permissions; Fusion data security; organization, business-unit, and ledger access; least privilege; and separation of read versus write access. Do not invent role or privilege names.

Cover authentication/authorization failures, no or multiple matches, invalid identifiers, lookup failures, validation failures, transient faults, timeouts, pagination, concurrency, partial completion, and downstream action failures. Specify recovery behavior and escalation; never silently select ambiguous records.

Use this required testing order, and make it concrete for the use case:

1. simplest safe read-only Business Object operation, validated first against its underlying GET evidence: authentication, documented Business Object mapping, identifier, and response parsing;
2. lookup/reference calls;
3. child-resource calls;
4. branches and edge cases;
5. BI Publisher validation/fallback where applicable;
6. complete end-to-end read-only flow;
7. create/update in sandbox or test with dedicated data, minimal payload, and a single-record trial;
8. submit/action/workflow testing;
9. audit logging, idempotency, retry, recovery, and concurrency testing;
10. production readiness and verification of the actual business outcome through the applicable agent-equivalent Business Object/API response, BIP report, workflow/ESS status, or downstream API result. A Fusion UI confirmation, if needed, is user-performed and is not a data-discovery or test mechanism for this skill.

For mutations, require a sandbox/test-first approach, test data, suitable human confirmation, retry and recovery planning, and final cross-channel verification.

## Default response format

Unless the requester specifies another format, select one of these structures.

### Discovery / Presales Brief

1. `# 1. Business Use Case and Desired Outcome`
2. `# 2. Current Oracle AI Agent Studio Alignment` — retrieval date, relevant current learning-path topics, and release-sensitive items.
3. `# 3. Documented Platform Scope` — applicable release, relevant docs.oracle.com sources, supported capability boundary, and explicit exclusions.
4. `# 4. Recommended AI Studio Build Unit`
5. `# 5. Solution Hypothesis and User Journey`
6. `# 6. Capability Map and Feasibility Boundaries`
7. `# 7. Proof-of-Value Proposal`
8. `# 8. Assumptions, Risks, and Open Questions`
9. `# 9. Learning Path Next Steps`
10. `# 10. Baby-Step Implementation Plan and Decision`

Use a compact requirement traceability table where it clarifies ownership or evidence. Keep technical mappings clearly labeled Candidate or Unknown until verified.

### Technical Handoff

Start with brief current Oracle AI Agent Studio Alignment and Documented Platform Scope sections, then use these headings in order:

1. `# 1. Use Case Interpretation`
2. `# 2. Recommended AI Studio Build Unit` — preferred lowest-complexity option: Workflow with a single Agent node, Workflow with a Multi Agent node, Deterministic Agent workflow, or Agentic Application; rationale, requester preference if any, and plausible alternatives.
3. `# 3. End-to-End API Flow` — an auditable table with step, API/resource, endpoint, method, purpose, required inputs, query parameters, extracted data, branch, next step, requirement class, and confidence.
4. `# 4. Detailed API Design`
5. `# 5. Update / Action Payloads`
6. `# 6. REST Gaps and Alternatives`
7. `# 7. BI Publisher Alternative`
8. `# 8. Security and Permissions`
9. `# 9. Error Handling and Recovery`
10. `# 10. Open Verification Items`
11. `# 11. Baby-Step Agent / Workflow Creation and Testing Plan` — include prompt specification and evaluation when LLM, Agent, or Multi Agent components are used.
12. `# 12. Live Validation and Fusion AI Studio Handoff` — gate status, live-test evidence, simulation outcome, or the complete copyable handoff prompt when the gate passes.

The verification section must be a concrete checklist covering Oracle documentation, current learning-path/release alignment, release/configuration, target pod, security, BI Publisher, and API tests. Keep the design implementation-oriented and audit-friendly; distinguish evidence, assumptions, and unknowns at the point they affect a decision. For Technical Handoff, retain the complete read-only-first sequence and do not omit API-flow, mutation, BIP, security, recovery, or production-readiness controls. Never emit the Fusion AI Studio Handoff Prompt until the live validation gate passes.
