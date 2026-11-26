# Autarks' Home

A plug-and-play home appliance so people can own, run and govern their compute, data and publishing, rather than rent them from a distant cloud.

**Website:** [https://autarks-home.com](https://autarks-home.com)  
**Contact:** [john@debeer.com](mailto:john@debeer.com)

## What it is for

Autarks' Home is an internet-enabled appliance with three main purposes:

1. It brings affordable AI into the home, where it may be controlled by the owner, while avoiding the expense of using APIs.
2. It enables disengagement from curated online services in general.
3. It establishes the means by which an owner may associate freely with peers.

It is packaged as a plug-and-play appliance, hosted in a home or office, perched on a shelf or desk. It can host a website, keep published articles in order and, with a planned AI add-on, provide local compute power, without requiring that its owner learn server administration. Association is enabled by a guild paradigm, planned for in the architecture so that individual owners may progress to guild founders.

## What works today

The core platform is about 90% ready for beta testing. The lab prototype is a maxed-out Raspberry Pi 5 with a 2TB NVMe SSD and Power over Ethernet, on a switch with three other Pis.

- A setup wizard onboards the owner.
- A writer-first publishing workflow accepts finished work done on the owner's own computer and saves it as a draft in a containerised Ghost CMS, from where the author may publish it, complete with graphics and custom formatting.

Beta testing starts as soon as the user interface, currently under development, is complete, after which the command line is no longer required.

[demo to be added]

The full working codebase remains private for now. This repository is a public showcase: an overview of the design, the stack and the roadmap. Finished code will be published here as it stabilises, before beta.

## Roadmap in brief

Before invited beta, the remaining work is principally the owner-facing interface, together with planned hardware-key and passkey authentication. Those steps, and the start of an invited beta, are also the first quarter of a proposed Mozilla Foundation Fellowship (June–August 2027), if that application is successful.

If funded, the Fellowship year (June 2027–May 2028) would add a local AI peripheral, research and paper-publishing applications, an open buyer's blueprint, compute-per-pound and per-watt benchmarks, and a modest exploratory test of federated adaptation across mixed, intermittently connected home appliances. A public prototype would ship within that year, usable without buying an appliance.

A guild management module must still be designed and built. It is on the roadmap after beta, is not funded by the current grant applications, and will be a separate commercial product.

A data modeling module is also planned: a general-purpose tool for designing and maintaining models of an owner's or a group's own data, in any subject, so that a local AI can work on it, with AI assisting in the modeling. It is later work, is not funded by any grant application, and will be a separate commercial product, outside the open-source commitment. It is an optional addition. The open appliance, the AI engine and the Research Workbench do not depend on it and are usable without it.

See [ROADMAP.md](ROADMAP.md) for the full picture, with funded and unfunded work labelled.

## Open source

The Autarks' Home appliance software will be open source under the GNU Affero General Public Licence (AGPL): everything that runs on the appliance and its planned AI peripheral, including the research applications. You should not have to buy the appliance to use the software.

The guild management module and the data modeling module come later, as separate commercial products, and are not part of this open-source commitment. The open software does not depend on either.

The commitment is that if the company disappears, owners lose nothing: firmware and OS builds will be fully documented and published, and keys and backups stay in the owner's possession, so anyone can rebuild and maintain the system.

See [LICENSE-NOTE.md](LICENSE-NOTE.md) and [CONTRIBUTING.md](CONTRIBUTING.md).

## Further reading

- [Architecture](docs/architecture.md) — the high-level stack and how the parts fit together
- [Design overview](docs/design-overview.md) — goals, principles, user journeys, the guild model and the planned AI peripheral
- [Research Workbench](docs/research-workbench.md) — the planned first research app on the local AI engine: method, development plan and evaluation design
- [Roadmap](ROADMAP.md)
- Project page: [https://autarks-home.com](https://autarks-home.com)
