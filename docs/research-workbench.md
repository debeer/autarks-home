# Autarks' Home Research Workbench: from first guess to testable opinion, with AI on hardware you own

*A model-independent engineering layer for AI-assisted reasoning. Version 3, draft, 19 November 2026.*

*Status: planned, not yet built. This document sets out the method, the development plan and the evaluation design.*

## Where this fits in Autarks' Home

The Research Workbench is planned as the first research app on the local AI engine of the Autarks' Home appliance. Its purpose is to show owned, offline AI doing useful, checkable work for solo entrepreneurs, independent researchers and small publishers, with the sources, the records and the model all staying in the owner's home. The workbench treats the model as a source of suggestions, not of authority: the researcher owns the original idea and every decision, and each step from that idea to a testable statement is recorded where another person can check it. Like all Autarks' Home appliance software, the workbench, its schema, method templates and example cases will be open source (AGPL), and usable without buying an appliance.

## Aim and research question

Much good research starts with a hunch: a first guess, grasped before it can be justified, resting on assumptions not yet spelled out. Few tools help turn an instinct into something that can be tested. Version 3 of the workbench is built around that step. It does not follow a fixed route from theory, through experiment, to conclusion. It starts from a first guess and its assumptions, works out what must logically follow if the guess is right, and then asks which consequences can be checked against evidence or tested by experiment. The philosopher Charles Sanders Peirce described this pattern of guess, deduction and test; the workbench uses it in plain terms.

The research question is this: does AI mediation, by a modest local model inside a workflow that keeps the researcher in charge, help people turn instincts into clearer, more testable statements, without flattening or discarding the original insight? "Flattening" means rewording an idea into a safer, more conventional claim that loses what made it distinctive. The first test uses the same model on every arm; a comparison against a capable hosted model comes only after the effect of the method itself has been measured.

The project builds on the earlier discussion of how people learn to correct their own reasoning. People improve when their claims, evidence and changes of mind are written down where someone else can check them; version 3 applies this one step earlier, to the guess itself. In the developer's personal view, statistical inference at scale fits poorly with human intuition, and he welcomes having that view tested to the limit. The workbench is one way to test it, and the results will be published either way.

## First use and scope

The initial user is the developer, working as researcher and editor, so the method is tried on real work from the start. The intended users are solo entrepreneurs, independent researchers and small publishers who need to know which of their ideas will stand up. The first study uses historical, licensed and synthetic cases and the developer's own working conjectures. Web crawling, automated OCR, collaboration, public hosting and foundation-model training are deferred.

The prototype delivers a local workspace, a versioned case file holding the full trail from instinct to testable statement, a reviewer-readable audit report, and a clean Markdown brief. Each consequential claim, one whose correction could change the conclusion, needs a recorded disposition before final export.

## What would justify continuing

A reviewer should be able to read the original guess in the researcher's words and follow every step from it to a test and its evidence. The engine should still support manual work without inference. The feasibility study should show more hidden assumptions surfaced and more testable consequences than a well-prompted model alone, with the original idea preserved and active time within 25% of the baseline (thresholds below).

# From Instinct to Testable Opinion

## The six steps

1. Capture the first guess. The researcher writes the instinct in their own words, with the date, what prompted it and, optionally, how confident they feel. It is labelled as a conjecture. The original text is never overwritten; every reformulation is stored as a new version beside it.

2. Make the assumptions explicit. The local model proposes the unstated assumptions the guess seems to rest on: what must be true of the world, the terms or the evidence for it to make sense. The researcher accepts, edits or rejects each one and can add their own. Rejected assumptions are kept with a reason, and the origin of each assumption, researcher or model, is recorded.

3. Derive the consequences. With the guess and accepted assumptions as premises, the researcher and the model work out one or more logical consequences: "if the guess and these assumptions hold, then this must follow." Each is stored as a numbered chain of short steps, and every step names the premises or earlier steps it relies on, so each move can be checked separately. The model also flags gaps, such as a step needing an unlisted assumption.

4. Turn each consequence into a testable opinion. The workbench asks what observation or experiment would support it, what result would count against it, whether the test separates this guess from its obvious rivals, and roughly what it would cost in time, money and equipment. A consequence that no possible result could count against is marked as not yet testable and cannot be promoted until it is sharpened.

5. Gather existing evidence. Before any new experiment, the workbench checks what is already known, using the evidence layer from version 2. Sources are anchored to exact passages; compound assertions are broken into reviewable claims classified as observation, interpretation, causal inference, calculation or conjecture; and evidence is linked as supporting, contradicting or qualifying. The model surfaces the strongest contrary evidence and competing explanations, with source pointers. For historical sources, review prompts start from the Library of Congress primary source analysis tool. [2]

6. The researcher decides. For each testable opinion the researcher records a decision: pursue the test, revise the guess, park it, or abandon it, with a rationale and what could reopen it. Changes of mind are preserved. If an assumption is later rejected or a source changes, everything that depended on it returns to review.

The AI mediates. It proposes, questions and finds; it does not own the intuition and it does not decide.

## Guarding the original insight

The biggest risk is that a helpful model turns an unusual idea into an ordinary one. The original wording is always shown beside the current formulation. The model is asked, as a separate task, to name what is distinctive in the original guess and to flag any reformulation that drops it. Before a testable statement is exported, the researcher confirms that it still expresses their idea, or records what was given up and why. Fidelity is also measured directly in the evaluation.

## Checks

Mechanical checks verify that every step cites only listed premises or earlier steps, that no rejected assumption is still in use, that every consequence promoted as testable has a stated result that would count against it, and that approvals match the current version. From version 2 they also verify exact quotation, locator resolution, required evidence links and recomputation of simple numeric claims. For explicitly deductive steps, small typed rules look for inconsistent premises or counterexamples within a declared domain. A pass certifies only the named check.

Model suggestions are recorded with their inputs; the reviewer judges each one, and an override records who made it and why.

## Worked case

Michael Faraday's long-held instinct, in plain terms, was that electric and magnetic forces act through the space between bodies, along lines of force that are physically real, and that light might be connected with the same agency. That is step 1. Step 2 makes assumptions explicit: the space around a magnet is in a real physical state; a transparent material in that space shares that state; and light passing through the material could be influenced by it. Step 3 derives a consequence: a strong magnetic field should change light passing through a transparent material. Step 4 makes it testable: pass polarised light through dense glass in a strong field; no change under good conditions would count against it. Faraday ran a test of this kind in 1845 and found that the plane of polarisation rotates. The record would show what the result supports and what it leaves open, the full theory of fields that others later developed. The reconstruction is a simplified teaching case, not a claim about exactly how Faraday reasoned.

# Historical Cases as a Reference Standard

The evaluation needs cases where the instinct, assumptions, consequences and later tests are well documented. Each is written at the level of standard historical accounts, citing published secondary sources, with no invented quotations or figures, and is reviewed by someone with historical knowledge before the holdout is frozen. The candidates are:

- Faraday's lines of force, as in the worked case.
- Wegener's continental drift: the core guess proved broadly right while its proposed mechanism did not, testing whether the workbench can separate a sound instinct from a weak assumption.
- Semmelweis and childbed fever: a consequence, that hand-washing would reduce deaths, was supported in practice while his explanation was rejected at the time.
- The luminiferous ether, as a counter-case: an intuition carried cleanly to a test, the Michelson–Morley experiment, that counted against it, so the case set does not reward agreeing with every guess.

A model may already know how these stories end, so each case is also run disguised, with names, dates and terms altered and the logical structure kept. Synthetic cases and the developer's own open conjectures are added, and results are reported by case type.

# Local Architecture and Ghost Boundary

## Data and ownership

The workbench uses SQLite for structured records and a local folder for source files, both on the owner's appliance. Version 3 adds five record types to the version 2 schema: the instinct (original text, author, date, prompt, optional confidence, never overwritten), the assumption (text, origin, status, rationale), the consequence (numbered steps with premise links), the test proposal (supporting result, counting-against result, rivals separated, estimated cost, status) and the decision (choice, rationale, what could reopen it). Version 2's source, evidence, claim, check and review records are kept and map onto W3C PROV. [3]

Revisions, links and invalidation events are written in a single transaction, so rejecting an assumption reliably queues every dependent step, consequence, test and decision for review. Exports are versioned JSON with a manifest and checksums, restore is verified in a fresh workspace, and external exports are previewed for private notes.

## Model adapter and local operation

The first version is a CLI, a generated HTML review report and a loopback-only inference adapter. The adapter accepts a bounded input and a task schema (propose assumptions, propose or critique a chain, propose tests, find evidence spans, flag drift from the original) and returns structured suggestions. Output is validated, malformed suggestions are quarantined, and review is required before anything enters the record. Model, quantisation, prompt version, inputs, settings, latency and failures are logged.

Phase one benchmarks a quantised instruct model on hardware the project already has: a Raspberry Pi 5 with the local AI peripheral. The smallest usable configuration is chosen on measured latency, memory and output validity, and the manual path stays available on failure. Offline operation is confirmed with outbound networking disabled. Source text is treated as untrusted data, and the model has no tool or publishing privileges. Any hosted inference is a separate, explicit experiment using public cases only.

## Ghost integration

The workbench is a separate application with its own storage, configuration and release cadence. Its publishing path is a clean Markdown draft sent to the owner's own Ghost site, with no changes to the site itself; the owner edits and publishes it in the usual way, choosing which parts of the trail to include. The handoff is tested first on a disposable Ghost instance; a later optional reader may use Ghost's read-only Content API. [4] Rolling back leaves the site unaffected.

# Development Plan

The plan below is proposed as phase one of the Mozilla Foundation Fellowship year (June 2027 to May 2028), if that application is funded, planned for June to August 2027. Phase one does not depend on the appliance beta and involves no beta users or members of the public: it runs on existing hardware, with the developer as researcher. Paid expert raters score anonymised outputs; they do not use the software.

## Stage 0: Establish the baseline

Weeks 1–2, 20–30 hours. Historical, disguised and synthetic cases are written with reference lists, the rubric is set, a development set is frozen, and the developer records at least two of his own conjectures. Two timed runs are recorded with a conventionally prompted local model. The stage is complete when the manual record can hold a full trail from instinct to test for one case and the baseline shows at least one concrete failure, such as a missed assumption or an untestable consequence, that a rule or review step could catch.

## Stage 1: Build the manual core

Weeks 3–5, 30–40 hours. This stage implements the five new record types, step-by-step chains with premise links, dependency invalidation, the version 2 evidence layer, the review queue, and Markdown plus JSON export. Fixtures cover a rejected assumption still in use, a step citing a missing premise, a consequence with no counting-against result, an overwritten original, broken anchors and stale approvals. The stage is complete when every fixture behaves as specified and the manual path is practical on one of the developer's own conjectures.

## Stage 2: Add local assistance

Weeks 6–8, 30–40 hours. This stage implements the model adapter, the five suggestion tasks, validation and audit records. One local model is used for the matched trial and a second for a swap test. The same cases are run with inference disabled to confirm the records and exports remain usable. The stage is complete when all scripted checks pass with either backend, offline operation is measured, and invalid model output leaves the record intact.

## Stage 3: Evaluate and trial publication

Weeks 9–12, 35–50 hours. This stage runs the frozen comparison, blind scoring by paid expert raters, and a dry run of the Markdown handoff on a disposable Ghost instance. The results, including failures, are written up as a case-set report.

## Time budget and decision log

Phase one takes 115–160 hours across 12 part-time weeks, roughly 10–13 hours a week. Paid rater time would come from the Fellowship project budget. Each gate is a go/no-go point recorded in a decision log. If a stage overruns by more than a week, scope is cut back to the manual records and review flow before the schedule is extended.

## Later phases

Phase two (September 2027 to February 2028) connects the Markdown handoff to the owner's own Ghost site as part of the appliance's paper-publishing path, adds a larger local model arm on the Fellowship testbed hardware, and invites a few researchers to try the method on their own non-sensitive conjectures. The paid pilot starts only if phase one meets its gate.

Phase three (March to May 2028) repeats the benchmarks across the hardware range, adds a hosted-model arm on public cases, widens trials to more invited researchers, and publishes the case set, templates and findings, whatever the results show.

# Evaluation and Decision Rules

## Comparison design

The evaluation freezes 12 held-out cases: the four historical cases in named and disguised form (eight), plus four synthetic cases, with at least four more kept for development. Each held-out case defines the starting instinct in neutral wording, reference lists of hidden assumptions, valid consequences and plausible tests, a small evidence packet, and planted traps such as a consequence that does not follow, an assumption that quietly changes the idea, and a test that cannot discriminate between rivals. The developer's own conjectures run as a separate strand with no reference answer; only fidelity, testability and time are measured there. The rubric, budget and thresholds are registered before the holdout is opened, following OSF guidance. [1]

The comparison has three arms: A, the same local model with a good prompt asking it to list assumptions, derive consequences and propose tests; B, the same model inside the workbench; and C, the workbench used manually, with no model. All arms start from the same instinct and evidence packet. A and B have equal model-call or token ceilings, and usage, hardware, wall time and active analyst time are logged. Condition order is balanced, and outputs are normalised and randomised for blind rating. If the developer runs all arms, memory and familiarity are recorded as limitations.

## Primary measures

- Assumptions surfaced: the share of reference assumptions that appear, accepted, in the final record, plus the share of listed assumptions raters judge relevant, so padding is not rewarded.
- Validity: the share of derived consequences that blind expert raters judge logically sound, each step following from the stated premises.
- Testability: the share of consequences raters judge genuinely testable, with a result that would count against them and a test that separates the guess from at least one rival.
- Fidelity: whether the final statements still express the original idea. On his own conjectures the developer rates this on a five-point scale; on reference cases a blind rater records whether the distinctive element of the starting instinct survived.
- Evidence layer, from version 2: unsupported consequential claim rate and share of consequential citations that reopen at the quoted passage.
- Effort: median and worst-case active analyst time, and time to find and correct a seeded error.

A second rater scores at least four cases independently, agreement is reported, and raw results and failures are published.

## Pass thresholds

The feasibility gate is passed if, compared with A, arm B:

- surfaces at least 20 percentage points more of the reference assumptions (proposed);
- achieves at least 80% of consequences rated logically sound, and no lower than A (proposed);
- achieves at least 25% more consequences rated genuinely testable (proposed);
- keeps the distinctive element of the original instinct in at least 90% of cases, with a median fidelity rating of at least four out of five on the developer's own conjectures, and no lower than A (proposed);
- reduces unsupported consequential claims by at least 30%, and resolves at least 95% of consequential citations on the first review pass (as version 2);
- takes at most 25% more median active analyst time (as version 2).

Approved exports must have zero known broken anchors and zero uses of rejected assumptions, and the fixtures must show full detection of stale approvals and dependent consequences. If A already scores near the ceiling on a measure, a fresh, harder set of cases is run before any gain is claimed. Any change to the proposed numbers is made and logged before the holdout is opened.

## Interpretation and next experiment

Arm C shows whether the method's structure helps by itself and whether local inference earns its place. If B beats A but not C, the gain comes from the method, and inference is narrowed to the task where it demonstrably helps. If B improves testability but lowers fidelity, the model is flattening ideas; the drift check is strengthened and the trial repeated on fresh cases. If named and disguised versions differ sharply, the named result is treated as memory. If two iterations fail to improve assumptions, testability or fidelity, product investment stops and the case set and findings are published. The results are feasibility evidence from a small sample.

# Open Source, Sustainability and Principal Risks

## Open source and IP hygiene

The workbench application, schema, method specification, templates and example cases, including the historical reference cases, will be open source, like all Autarks' Home appliance software (AGPL). There are no paid method packs, proprietary editions or patents. A dated design log and an inventory of code, model terms, corpora and dependencies record the right to redistribute each; client material stays out of the public case set. The licence check on models and corpora is completed before the first public release.

## Sustainability through services

The first market is independent researchers, specialist publishers and solo entrepreneurs who have ideas worth testing and little help in shaping them. Five are interviewed about a recent hunch they pursued or dropped and their current tools, such as Zotero, to test whether a recorded trail from guess to test adds value beyond citations and annotations. [5]

Revenue comes from services, not the software: setup, onboarding, support and a paid pilot. The pilot takes one question from first guess to testable statement, with local deployment, at a test price of £250 for up to four hours of support, paid or committed in writing. It continues only if two users commit, one reuses the workflow, and support time fits the price.

## Principal risks and responses

- Flattening the idea. The original is never overwritten, a drift check compares each reformulation with it, and fidelity is a pass criterion.
- False rigour. Every chain shows its premises, rejected assumptions are blocked mechanically, and the evaluation plants invalid steps.
- Memorised history. Historical cases run named and disguised, alongside synthetic and live cases.
- Review overhead and solo bias. Active time is measured against the baseline, the case set is frozen, and scoring is blind and independent.
- Data exposure. Operation is offline, and unpublished conjectures stay in the workspace unless the owner publishes them.

## References

[1] Center for Open Science, OSF Registrations

[2] Library of Congress, Primary Source Analysis Tool

[3] W3C, PROV Data Model

[4] Ghost, Content API

[5] Zotero, PDF Reader and Note Editor

Historical case write-ups will cite the published secondary sources they draw on; these are added in Stage 0.

# What changed from version 2

- Reframed around moving from instinct to testable opinion in six steps, with the decision left to the researcher; the research question asks whether AI mediation helps without flattening the insight.
- Version 2's claim checking is kept as the evidence layer; five record types are added.
- Arms A, B and C are kept; new measures (assumptions, validity, testability, fidelity) have proposed thresholds.
- Historical cases, run named and disguised, become the reference standard; Faraday replaces the library worked case, and the method-template sections are folded into the six steps.
- Phase one involves no invited researchers; paid raters only score outputs. Invited researchers and the paid pilot move to phase two.
- The developer's personal view on intuition is stated as a view to be tested.
