# Autarks' Home Research Workbench: checkable AI-assisted research on hardware you own

*A model-independent engineering layer for AI-assisted research. Revised draft, 19 November 2026.*

*Status: planned, not yet built. This document sets out the method, the development plan and the evaluation design.*

## Where this fits in Autarks' Home

The Research Workbench is planned as the first research app on the local AI engine of the Autarks' Home appliance. Its purpose is to show owned, offline AI doing useful, checkable work for solo entrepreneurs, independent researchers and small publishers, with the sources, the records and the model all staying in the owner's home. The workbench treats the model as a source of suggestions, not of authority: every consequential claim in a finished brief is traced to an exact passage and a recorded human review. Like all Autarks' Home software, the workbench, its schema, method templates and example cases will be open source (AGPL proposed, not yet final), and usable without buying an appliance.

## Aim and research question

The workbench is a local tool that helps a person record, challenge and revise factual claims. It starts with one repeated task: turning a small packet of conflicting sources into a short brief whose consequential claims can be traced to exact passages and reviewed by another person. Development is staged, and each stage continues only when the prototype demonstrably improves the work.

The research question is this: can a modest local model, operating inside a workflow that requires evidence, competing explanations and explicit review, reduce consequential research errors at a tolerable cost in researcher time? The first test uses the same model and source packet on both sides. A comparison against a capable hosted model comes only after the effect of the method itself has been measured.

The project builds on the earlier discussion of how people learn to correct their own reasoning. The core idea is simple: people improve when their claims, their evidence and their changes of mind are written down where someone else can check them. Probability and statistics remain available where the question calls for them. The workbench records their assumptions, inputs and limits alongside other forms of warrant, such as a reproducible calculation, a documentary chain of custody, or a deduction from stated premises. A model's confidence score carries no evidential weight by itself.

## First use and scope

The initial user is the developer, working as researcher and editor, so the method is tried on real work from the start. The intended users are the people Autarks' Home is built for: solo entrepreneurs, independent researchers and small specialist publishers whose work involves repeated fact-checking against documentary sources. The first study uses public-domain, licensed or synthetic material. It begins with manually supplied text excerpts or text-based PDFs and human-verified anchors. Web crawling, automated OCR, collaboration, public hosting and foundation-model training are deferred.

The prototype delivers a local workspace, a versioned case file, a reviewer-readable audit report, and a clean Markdown brief. A consequential claim is one whose correction could change the brief's conclusion or the reader's decision. These claims are marked during review, and each must have a recorded disposition before final export. An explicitly labelled draft export is available for open work.

## What would justify continuing

A reviewer should be able to reopen the underlying passage, understand the inference, find contrary evidence, and see what changed after a correction. The engine should still support manual research when inference is unavailable. The first feasibility study should show fewer unsupported consequential claims under matched conditions and keep median active analyst time within 25% of the prompted baseline. These are proposed decision thresholds for a pilot.

# Evidence and Reasoning Workflow

## From question to reviewed brief

1. Frame the question. The researcher records scope, definitions, the decision at stake, and what evidence could change the conclusion. For confirmatory work the initial protocol is frozen and later departures are logged.

2. Capture sources. The workbench preserves the available version, rights, origin and retrieval record. Evidence is anchored to a specific passage, table cell or page image, and the record distinguishes a literal quotation from a transcription or paraphrase.

3. Propose claims. Compound assertions are broken into statements that can be reviewed independently. Each is classified as observation, interpretation, causal inference or calculation. Evidence is linked explicitly as supporting, contradicting or qualifying the claim, with a short rationale.

4. Challenge and review. The workbench presents competing explanations and the strongest contrary evidence. The reviewer records a decision and rationale, chooses whether the claim is supported, contested, insufficiently evidenced or withdrawn, and specifies what could reopen it. Disagreement and changes of mind are preserved.

5. Export and revise. The workbench generates a brief and a review appendix with stable claim references. A changed source or claim invalidates affected approvals and queues dependent conclusions for review. The prior brief is retained with its version identifier.

## Three kinds of checks

Mechanical checks verify exact quotation against the saved text, source version and locator resolution, required evidence links, date or unit consistency where encoded, and whether approvals still match the current claim. Simple numeric claims are recomputed from recorded inputs with a versioned script. For explicitly deductive steps, the workbench starts with small typed rules and looks for inconsistent premises or counterexamples within a declared domain. A pass certifies only the named check.

Model suggestions surface missing qualifiers, misleading excerpts, alternative explanations, and possible shared origins. Each suggestion is recorded with its source pointers. A reviewer judges relevance, source credibility, whether a passage supports the claim in context, and how far a result generalises. An override records who made it and why. Broken anchors block reviewed export until they are repaired or the affected claim is withdrawn.

## Worked case

A newspaper claims a public library opened in 1894 and a later local history repeats the date. Council minutes show that a reading room opened that year, and a programme identifies the formal library opening in 1895. Both dates can be retained once the claims distinguish the two events. The later history cites the newspaper, so the reviewer records a shared origin. If a new scan changes the programme's date, the opening claim and any chronology derived from it return to review. The archive's silence about earlier activity remains a question about coverage.

# Scientific and Historical Methods

## Scientific inquiry

For a quantitative case, the workbench records the target population, outcome, exposure or intervention, comparison, sampling procedure, exclusions, and analysis plan before a confirmatory analysis is run. Exploratory findings and protocol departures are logged. The dataset fingerprint, code version, parameters and output are kept together so a second run can reproduce the reported quantity. The template asks which result would disconfirm the hypothesis and what measurement error, confounding or selection could explain the observation. Sensitivity checks are tied to those assumptions. For causal language, the template asks for the identification argument and an appropriate comparison.

A first fixture can use synthetic reading-room attendance. If attendance rises after longer opening hours, the reviewer records a competing explanation such as term-time demand and checks a comparison period or venue. The reported numerator, denominator and time window are verified from an extract. If the design leaves the effects entangled, the brief publishes the observed change and the unresolved causal question. The tool lets the reviewer downgrade only the causal clause while preserving the checked calculation.

## Historical inquiry

The workbench records creator, date of creation, date of the event described, intended audience, purpose, custody or publication history, and whether the reviewer examined an original, transcription, translation, or retelling. What the source says and what the researcher infers are kept in separate fields. Likely or documented dependencies between accounts are linked. In cases of conflicting testimony, the reviewer compares access to the event, proximity, independence and corroboration, and records gaps in the surviving evidence.

The library case tests whether the workbench can represent contested terms and dates without forcing an artificial resolution. A second case asks whether two reports of a decision derive from the same circular. The reviewer can retain rival readings with a rationale and an explicit account of what further records would distinguish them.

## Method rules as versioned records

A method template supplies prompts, required fields, available checks and review criteria. The template is chosen per case and its version pinned, so a later rule change can be audited. A reviewer can mark a requirement inapplicable with a reason. An examples folder holds one passing and one failing case per rule. Both methods use the same record types, and specialised fields are added only when they change a review decision. Experimental preregistration follows OSF guidance, and primary-source inquiry prompts start from the Library of Congress analysis tool. [1–2]

# Local Architecture and Ghost Boundary

## Data and ownership

The workbench uses SQLite for structured records and a local folder for source files, both on the owner's appliance. It stores a source ID, version hash, bibliographic identity, acquisition time and rights. Each evidence span is stored with source version, locator, exact excerpt or permitted reference, and extraction method. Each claim revision is stored with stable ID, statement, scope, type, premise and evidence links, author, and review status. Check results and review decisions are kept with the rule version, inputs, outcome and actor. Sources and revisions map to entities, checks to activities and reviewers to agents, so later interoperability can draw on W3C PROV. [3]

Revisions, their links and invalidation events are written in a single transaction. Saved bytes are verified on import, identical content is deduplicated while attribution and origin are retained, and an explicit tombstone is recorded when restricted material must be removed. A fingerprint detects byte changes within the recorded chain. Authenticity and credibility remain matters for source review. The workbench exports versioned JSON and permitted attachments with a manifest and checksums, and export and restore are verified in a fresh workspace. External exports are previewed for restricted passages and private annotations.

## Model adapter and local operation

The first version is a CLI, a generated HTML review report and a loopback-only inference adapter. The adapter accepts bounded passages and a task schema, then returns structured candidate claims, cited span IDs or objections. The result is validated, malformed suggestions are quarantined, and explicit review is required before anything is promoted into the claim record. The workbench logs model and weight identifiers, runtime, quantisation, prompt version, inputs, generation settings, latency and failures. It keeps the event and input records needed to replay a check, and distinguishes reproducible checks from variable model generations.

Phase one benchmarks a quantised instruct model on hardware the project already has. The smallest usable configuration is selected on measured latency, memory use, structured-output validity and review effort. Context and retries are capped, truncated inputs are reported, and manual capture, review and export stay available on timeout or invalid output. Offline operation is confirmed with outbound networking disabled. Source text is treated as untrusted data, and the model is limited to suggestions, with no tool or publishing privileges. Any hosted inference is a separate, explicit experiment using a public packet.

## Ghost integration

The workbench is a separate application with its own storage, configuration and release cadence. Its publishing path is a clean Markdown draft sent to the owner's own Ghost site, with no changes to the site itself; the owner then edits and publishes it in the usual way. The handoff is tested first against a disposable Ghost instance, including formatting, citation links and exclusion of private material. Once its value is measured, an optional reader may retrieve the owner's published material through Ghost's read-only Content API. [4] Rolling back means disabling the optional reader or discarding the export; publishing on the site carries on unaffected.

# Development Plan

The plan below is proposed as phase one of the Mozilla Foundation Fellowship year (June 2027 to May 2028), if that application is funded, planned for September to November 2027, after the invited beta of the appliance has started. Phase one runs on existing hardware. The later phases are described after it.

## Stage 0: Establish the baseline

Weeks 1–2, 20–30 hours. One research brief the project would genuinely use is selected. One historical and one scientific case record are built by hand. The review rubric is written, consequential errors are defined, and a small development set, distinct from the later evaluation packets, is frozen. Two timed runs are recorded using a conventional prompted assistant and the supplied packets. The stage is complete when the manual workflow can produce an auditable brief and exposes at least one concrete failure that a rule or review step could catch.

## Stage 1: Build the manual core

Weeks 3–5, 30–40 hours. This stage implements source capture, stable anchors, claim and evidence edits, the review queue and Markdown plus JSON export. Fixtures cover broken and moved anchors, duplicate source lineage, disputed claims, and stale approvals. Two full cases are demonstrated offline, and an exported case is restored in a fresh workspace. The stage is complete when every fixture behaves as specified and the manual path is practical enough to use for a third brief.

## Stage 2: Add local assistance

Weeks 6–8, 30–40 hours. This stage implements the model adapter, validation, suggestion review and audit records. One local model is used for the matched trial and a second compatible model for a swap test. The same cases are run with inference disabled to confirm that the audit decisions and exports are still accessible. The stage is complete when all scripted source and revision checks pass with either backend, offline operation is measured, and invalid model output leaves the authoritative record intact.

## Stage 3: Evaluate and trial publication

Weeks 9–12, 35–50 hours. This stage runs the frozen comparison, a small independent double-review where feasible, and a dry run of the Markdown handoff on a disposable Ghost instance. A few prospective users are invited to perform a real research task using non-sensitive material. The paid pilot (below) starts only if the evaluation meets its gate and prospective users show repeat use or payment intent on the terms proposed.

## Time budget and decision log

Phase one takes 115–160 hours across 12 part-time weeks, roughly 10–13 hours a week on average. Paid reviewer and evaluation time would come from the Fellowship project budget. Each gate is a go/no-go point for scope: at each one, the decision log records the observed result, what changed, the hours used and the next step. If a stage overruns by more than a week, scope is cut back to the manual evidence and review flow before the schedule is extended.

## Later phases

Phase two (December 2027 to February 2028) connects the workbench's Markdown handoff to the owner's own Ghost site as part of the appliance's paper-publishing path, and adds a larger local model arm on the testbed hardware requested for the Fellowship, with the same frozen packets run across machines.

Phase three (March to May 2028) repeats the benchmarks across the full hardware range, including a Mac Studio-class machine if one is available, and adds a hosted-model comparison arm using public packets only. It widens user pilots beyond the developer and invited prospective users, and publishes the case set, method templates and findings, whatever the results show.

# Evaluation and Decision Rules

## Comparison design

The evaluation freezes 12 held-out packets, six historical and six scientific, plus at least four development packets for tuning. Each held-out packet defines a question, expected consequential claims, acceptable evidence spans, ambiguous cases, and planted failure modes such as recycled testimony, an out-of-context quotation, a confounded inference or an incorrect denominator. Some cases make abstention the right disposition. The rubric, budget and thresholds are registered before the holdout is opened.

The comparison has three arms: A, the same local model with a good prompt requesting citations and caveats; B, the same model plus the workbench; and C, the workbench used manually. All arms get the same source packets and completion instructions. A and B have equal model-call or token ceilings, and actual usage, hardware, wall time and active analyst time are logged. Balanced condition ordering and spacing between repeats reduce carryover. Exported briefs are randomised and normalised for blind scoring where practical. If the solo developer runs all arms, memory and workflow familiarity are recorded as limitations. A second reviewer scores at least four packets independently before disagreements are discussed.

## Primary measures and guardrails

Unsupported consequential claim rate is the count of asserted consequential claims lacking adequate support divided by all asserted consequential claims. Omissions are scored separately as the share of expected consequential claims correctly covered. Unjustified causal claims and false corroboration are recorded as named error types. For traceability, the measure is the count of consequential citations a reviewer can reopen at the quoted passage on the exact saved version. Both initial production and the task of finding and correcting a seeded error are timed. Median and worst cases, raw paired results, reasons for disagreement and examples of failures are all recorded.

The feasibility gate is passed if B reduces unsupported consequential claims by at least 30% relative to A, loses at most five percentage points in expected claim coverage, resolves at least 95% of consequential citations on the first review pass, and takes at most 25% more median active analyst time. Reviewed exports must have zero known broken anchors among approved citations, and the scripted fixtures must show full stale-approval detection. If A produces zero unsupported claims, correction time is assessed and a fresh, harder holdout is run before any accuracy gain is claimed.

## Interpretation and next experiment

Arm C shows whether local inference earns its place through reduced effort or improved coverage. If the method helps but local inference adds little, the manual workbench stays and inference is narrowed to one demonstrably useful task. If quality improves at excessive cost, the review form is simplified and retested on fresh cases. If two iterations fail to improve either errors or correction time, product investment stops and the case set and findings are preserved and published. The results are feasibility evidence from a small sample. The later hosted-model arm tests whether portability changes the result.

# Open Source, Sustainability and Principal Risks

## Open source and IP hygiene

The workbench application, its schema, method specification, method templates and example cases will be open source, like all Autarks' Home software (AGPL proposed, not yet final). There are no paid method packs or proprietary editions. The project keeps a dated design log and an inventory of code, generated contributions, model terms, corpora and dependencies, and records the right to use and redistribute each component. Restricted corpora and client materials are kept out of the software and the public benchmark. Attribution and licence notices are captured, and provenance and licensing are verified for any incorporated generated code. The licence check on models and corpora is completed before the first public release.

## Sustainability through services

The first market is independent researchers and specialist publishers who repeatedly need defensible briefs. Five of them are interviewed about their last disputed claim, the time spent checking it, their current use of tools such as Zotero, and who pays for review. Zotero already supports citations and anchored annotations, so the interviews test whether claim-level decisions, source dependencies and revision after a correction add value in their existing workflow. [5]

Revenue comes from services, not from the software: setup, onboarding, support and the paid pilot. The pilot is a fixed-scope support-and-onboarding service for one brief or review workflow, with local deployment and a portable audit export. Its test price is £250, covering up to four hours of developer onboarding and support. The pilot asks for payment or a written purchase commitment. It continues only if two users commit, at least one uses the workflow on a second brief, and recorded support time fits the price. After repeat use, the next test is an ongoing support and updates service. Hosted collaboration is considered only when demand and capacity justify it.

## Principal risks and responses

- False assurance. Open issues stay visible and each pass is attached to its specific check. The evaluation audits examples where valid citations still support the wrong inference.
- Review overhead. Active minutes are measured against the baseline. Fields that make no observable difference to review decisions are removed.
- Data exposure and rights. Offline operation and restore are tested, exports are limited to permitted evidence, and redactions are reviewed before a brief leaves the workspace.
- Pilot bias and solo maintenance. The case set is frozen, independent scoring is invited, and the release is kept small enough to support within the time budget.
- Publishing coupling. The handoff is rehearsed on a disposable Ghost instance, and integration pauses if it would need any change to the owner's site.

## References

[1] Center for Open Science, OSF Registrations

[2] Library of Congress, Primary Source Analysis Tool

[3] W3C, PROV Data Model

[4] Ghost, Content API

[5] Zotero, PDF Reader and Note Editor
