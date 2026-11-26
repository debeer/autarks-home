# Research Workbench: from first guess to testable statement, with AI on hardware you own

*A summary of the design. The Workbench is planned; where the work stands is on the website, [autarks-home.com](https://autarks-home.com).*

## What it is

The Research Workbench is planned as the first research application on the local AI engine of the Autarks' Home appliance. Its purpose is to show owned, offline AI doing useful, checkable work for solo entrepreneurs, independent researchers and small publishers, with the sources, the records and the model all staying in the owner's home.

Much good research starts with a hunch: a first guess, grasped before it can be justified, resting on assumptions not yet spelled out. Few tools help turn an instinct into something that can be tested. The Workbench is built around that step. It treats the model as a source of suggestions, not of authority: the researcher owns the original idea and every decision, and each step from that idea to a testable statement is recorded where another person can check it.

## What the Workbench is, and what it is not

The Research Workbench is one application with one job: recording the trail from a researcher's first guess to a testable statement. Its schema is fixed and published as part of the method. It consists of the record types for a guess, its assumptions, the consequences derived from them, the tests proposed, the evidence and the decisions, and it is the same for every user. All of it is open source.

The Workbench does not design data models, and it does not model an owner's other data. That is the purpose of a planned data modeling module, which is a separate commercial product. The Workbench does not depend on that module and is complete without it.

## The six steps

1. **Capture the first guess.** The researcher writes the instinct in their own words. The original text is never overwritten; every reformulation is stored beside it.
2. **Make the assumptions explicit.** The local model proposes the unstated assumptions the guess seems to rest on. The researcher accepts, edits or rejects each one, and the origin of each is recorded.
3. **Derive the consequences.** "If the guess and these assumptions hold, then this must follow." Each consequence is stored as a chain of short steps, each naming what it relies on.
4. **Turn each consequence into a testable statement.** What observation would support it, and what result would count against it? A consequence that no possible result could count against is marked as not yet testable.
5. **Gather existing evidence.** Before any new experiment, check what is already known. Sources are anchored to exact passages, and the model surfaces the strongest contrary evidence.
6. **The researcher decides.** Pursue the test, revise the guess, park it or abandon it, with a reason and what could reopen it.

The AI mediates. It proposes, questions and finds; it does not own the intuition and it does not decide. The pattern of guess, deduction and test was described by the philosopher Charles Sanders Peirce; the Workbench uses it in plain terms.

## Guarding the original insight

The biggest risk is that a helpful model turns an unusual idea into an ordinary one. The original wording is always shown beside the current formulation, and before a testable statement is exported the researcher confirms that it still expresses their idea, or records what was given up and why.

## How it runs

The Workbench is a separate application with its own storage. Records and source files stay on the owner's appliance. The model runs locally, receives a bounded task, and returns suggestions that the researcher must review before anything enters the record. The model has no tool or publishing privileges, and the Workbench still supports manual work when no model is available.

A finished piece leaves the Workbench as a clean draft sent to the owner's own publication, where the owner edits and publishes it in the usual way, choosing which parts of the trail to include.

## Open source

The Workbench application, its schema, the method, the templates and the example cases will be open source. There are no paid method packs, proprietary editions or patents. This covers the Workbench only; the separate data modeling module is a commercial product and is outside it. The licence is set out in the [README](../README.md).

Whether the Workbench is funded, and by whom, is set out in the [roadmap](../ROADMAP.md).
