# Design overview

This is a public slice of the Autarks' Home design. It covers goals, principles, the main user journeys, the guild model and the planned AI peripheral. Internal security design, operational configuration and unfinished private specifications are omitted.

Guilds and the AI peripheral are planned work. They are reflected in the architecture and the public project page, but a detailed product specification for them has not yet been written.

## Goals

Autarks' Home is a self-hosted, plug-and-play content management appliance for authors, independent creators, crafters, small businesses, local councils, and anyone who values independence, self-sufficiency and personal agency. One box, no server administration required, on which an owner can run their own site.

The longer aim is a digital home people can own, run and govern: publishing they control, and, with a planned add-on, affordable local AI, without depending on a platform company or rented APIs.

## Principles

**The interface is the product.** The appliance only makes sense if "no technical skill required" is true in practice, at every step. A feature that cannot be made simple and clear in the interface is not ready to ship, regardless of backend readiness. The interface is one design system: a simple owner view by default, with an admin view underneath for infrastructure and, later, additional controls.

**Preserve "it just works".** Every future feature must be deliverable without compromising the plug-and-play promise. A feature that needs per-installation vendor intervention, infrastructure the owner cannot manage, or specialised technical setup is not ready to ship until it can be delivered in a way that still "just works". Uncertain ideas belong on a research list, not in the committed feature set.

**Public addresses identify publications, not software.** Switching CMS must never require a public URL to change.

**The owner does two jobs.** One is familiar: running a publication — telling a story, showing work, serving readers. The other is less familiar: owning an appliance that should protect itself but still has to be looked after. First setup is honestly a short appliance job. Once a publication exists, day-to-day work should feel like publishing, with appliance management available when it is needed, and status always visible so the owner can look even when nothing is wrong.

**If the company disappears, owners lose nothing.** Software will be open source, firmware and OS builds will be documented and published, and keys and backups stay in the owner's possession, so anyone can rebuild and maintain the system. You should not have to buy the appliance to use the software.

## User journeys

**First setup.** The owner powers the appliance on and is guided by a setup wizard. The aim is a short, confidence-inspiring first boot, not a lesson in server administration.

**Creating a publication.** The owner creates a site or publication by name. The Core app provisions a containerised CMS for it. The owner is not asked to think in terms of containers or infrastructure.

**Writing and publishing.** The default path is writer-first. The author writes on their own computer, in tools they already know, and sends the finished work to the appliance. It is saved as a draft in the CMS, complete with graphics and custom formatting, and the author publishes when ready. This path is in use on the lab prototype; the remaining work before beta is principally the owner-facing interface, so the command line is no longer required.

**Day-to-day use and looking after the box.** Day-to-day publishing is meant to stay in a simple owner view. Structural or administrative actions belong in a distinct admin view. The owner should always be able to see the appliance's status, including backups, even when nothing is flagged.

**Joining or founding a guild.** After the first reliable appliance is in an owner's home, that appliance can join another appliance, or a group of appliances, as a guild node. This journey is planned, not built; see below.

## Guilds

Every Autarks' Home appliance is a node in its own right. It does not have to join anything to be useful.

Beyond that, an appliance can join another appliance, or a group of appliances, as a guild node, and its owner thereby becomes a guild member. Whoever forms a guild — the founders, and in due course a board of governors — sets the rules for membership, governance and any fees. Membership fees, if any, are for each guild to decide, not for Autarks' Home to levy. Autarks' Home's role is that of an administrative tool. An appliance is not limited to one guild, so an owner can be a member of any number of guilds at once.

While a guild has few members, the management system may run on a founder's own node; as it grows, members might set up a dedicated node for a guild manager. A guild management module must still be designed and built; it is not funded by the current grant applications. The software for that module is intended to be open source. Services around it — for example hosted or managed guild-manager nodes, setup and support — are a possible later source of revenue.

Guilds are the step from individual autarky to community. A guild could be individuals forming a club, a group of machine shops with complementary fabrication systems and skills, a parish council, a library, a co-op or a book publisher. One possibility being explored is sharing idle compute among guild nodes.

## Planned AI peripheral

Plans include a peripheral AI compute engine for Autarks' Home. As described on the project page and in the Fellowship letter of intent, development plans include:

- applications for technical and scientific research, and a way to publish papers;
- software that stretches modest hardware;
- an open buyer's blueprint, with compute-per-pound and per-watt benchmarks, so owners can choose a configuration they can afford;
- a modest, exploratory test of federated adaptation across mixed, intermittently connected home appliances, aiming for privacy guarantees explained in plain language. Raw data stays in the home.

The Fellowship proposal describes a box in the region of £3,000, able to run 32B-class models, as the kind of system this work is aimed at. The aim is a public prototype people can try, including software usable without buying an appliance. In that proposal this work sits in the funded year if the application succeeds; it is not part of the pre-beta appliance work.

## How the project pays its way

The project will earn its keep by selling preassembled appliances and certified builds under the Autarks' Home name, and services such as managed updates and backups, hosted or managed guild-manager nodes, setup and support.
