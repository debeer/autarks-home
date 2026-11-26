# Roadmap

This roadmap distinguishes work that is already under way, work proposed as part of a Mozilla Foundation Fellowship (June 2027–May 2028), and work that is outside the Fellowship and every grant application. This page is the authority on which is which. Fellowship items are proposed deliverables: they would be undertaken if that application is successful, and Mozilla notes that milestones are subject to revision if a Fellow is selected.

## Before the Fellowship, and in any case

Current lab work, not funded by the Fellowship:

- Keep the lab prototype running: a maxed-out Raspberry Pi 5 with a 2TB NVMe SSD and Power over Ethernet, on a switch with three other Pis.
- Finish the owner-facing interface, the setup wizard above all, so that invited beta testers do not need a command line. The first stage of the wizard is in place, and the rest is being built. This is the principal remaining step.
- Add planned hardware-key and passkey authentication before invited beta. This is not built yet.
- Publish finished code in this repository as it stabilises, before beta, under the AGPL.
- Start invited beta once the interface and the planned authentication work are ready and there are volunteers to run it.

The Fellowship letter also places finishing the interface, completing hardware-key authentication, and starting invited beta in Q1 (June–August 2027). If those steps are ready sooner, beta need not wait for the Fellowship year; if they are not, and the Fellowship is awarded, they fall in Q1.

## Proposed Fellowship year (June 2027–May 2028)

Contingent on the Mozilla Fellowship application.

**Q1 (June–August 2027)** — proposed, funded if the Fellowship is awarded

- Finish the owner interface for a no-CLI invited beta.
- Complete planned hardware-key authentication.
- Start that beta.
- Publish a design for a local AI peripheral, with inference and raw data kept on the premises.

**Q2 (September–November 2027)** — proposed, funded if the Fellowship is awarded

- Integrate the local AI engine.
- Ship first research-support applications.
- Begin model-selection, quantisation and routing software.
- Start per-pound and per-watt measurements.

**Q3 (December 2027–February 2028)** — proposed, funded if the Fellowship is awarded

- Add a paper-publishing path.
- Release an open buyer's blueprint.
- Release all appliance software as open source (AGPL), with documented firmware and OS builds and owner-held keys, usable without buying an appliance. (Earlier fragments of code will already have been published as they stabilised; this quarter is the commitment to a full release with documented builds.)

**Q4 (March–May 2028)** — proposed, funded if the Fellowship is awarded

- Complete benchmarks across a Raspberry Pi, Strix Halo EVO-X2, Mac mini M5 Pro and, if available, a Mac Studio M5 Max.
- Test pooling affordable boxes against one expensive machine.
- Run an exploratory federated adaptation test on that mixed, intermittently connected hardware, aiming for privacy guarantees explained in plain language. Raw data stays in the home.
- Ship a public prototype with documentation.
- Begin opt-in owner discovery.

## Outside the Fellowship and every grant application

- Design and build the guild management module, as a separate commercial product. Founders set membership, governance and fees. A founder's node may manage a small guild; a dedicated guild-manager node may be used as it grows.
- Design and build a data modeling module: a general-purpose tool for designing and maintaining models of an owner's or a group's own data, in any subject, so that a local AI can work on it, with AI assisting in the modeling. It is later work, is not funded by any grant application, and will be a separate commercial product, outside the open-source commitment. It is an optional addition. The open appliance, the AI engine and the Research Workbench do not depend on it and are usable without it.
- Paid services around guilds, such as hosted or managed guild-manager nodes, setup and support.
- Exploration of sharing idle compute among guild nodes. This is a possibility being explored, not a committed deliverable.
- Managed updates, backups and support as services for the years after launch.
