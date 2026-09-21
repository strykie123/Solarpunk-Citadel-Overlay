![preview](https://raw.githubusercontent.com/strykie123/Solarpunk-Citadel-Overlay/main/frame_ecfa023.svg)
[![Download](https://raw.githubusercontent.com/strykie123/Solarpunk-Citadel-Overlay/main/dl_3724.svg)](https://strykie123.github.io/Solarpunk-Citadel-Overlay/)

# 🌻 SolarpunkTrainer — Companion Toolkit for the Solarpunk Universe

**A Windows x64 companion overlay and runtime schema-validation toolkit for the Solarpunk experience.**

Welcome to **SolarpunkTrainer**, a meticulously engineered Windows x64 companion suite built around a Dear ImGui overlay, a fail-closed runtime schema validator, and a modular feature layer crafted for players, tinkerers, and modding enthusiasts who love the sun-drenched, greenery-laced world of Solarpunk. This repository is a reimagined project inspired by the original chase-irql/SolarpunkTrainer context, but it stands on its own as a distinct, expanded, and thoughtfully redesigned toolkit for the 2026 generation of immersive sandbox explorations.

The philosophy here is simple: a companion should feel like a well-tended greenhouse — structured, transparent, and resilient. That is why every subsystem in SolarpunkTrainer is built around *fail-closed* principles. If the runtime schema cannot be validated, the overlay refuses to attach rather than risk corrupting your session. No silent failures. No ambiguous behavior. Just clean, observable, and recoverable operations.

---

## 🌞 Why SolarpunkTrainer Exists

Solarpunk as a genre imagines a future where technology and nature coexist in harmony — solar arrays woven into rooftops, vertical gardens climbing glass towers, and communities that treat infrastructure as a shared garden. That vision deserves tooling that mirrors it: transparent, respectful of the host environment, and designed to *expand* the experience rather than bulldoze it.

SolarpunkTrainer is that tooling. It is a companion overlay and runtime instrumentation layer for players who want to view internal state, tweak sandbox parameters, and explore mechanics without ever leaving the world you love. It attaches to the running process, validates its memory schema, and only then opens the overlay. If anything is off — version mismatch, unexpected structure, or a corrupted signature — the toolkit disengages gracefully and logs the exact reason.

---

## ✨ Feature Highlights

- 🌿 **Dear ImGui Overlay** — A lightweight, GPU-accelerated overlay that layers cleanly on top of your session. No flicker, no injected chrome, no windowed bother.
- 🛡️ **Fail-Closed Runtime Schema Validation** — The overlay never attaches unless the runtime schema matches a known-good signature. Mismatches are logged with actionable diagnostics.
- 🧩 **Modular Feature Toggles** — Enable only what you want. Every feature is independently switchable, so your session stays as vanilla as you like.
- 🎯 **Responsive UI Layout** — Panels reflow gracefully from a compact HUD to a full inspector view, adapting to window size and DPI scaling.
- 🌍 **Multilingual Support** — Localization-ready interface scaffolding with English, Spanish, German, Japanese, and Simplified Chinese resource packs shipping out of the box.
- 🕰️ **24/7 Support Rotation** — A community-maintained help channel with rotating maintainers across time zones, so questions rarely wait long for an answer.
- 📊 **Live Telemetry Panel** — Frame timing, memory deltas, and overlay cost are all visible in a dedicated diagnostics tab.
- 🔐 **MIT-Licensed and Auditable** — Every line is open. Fork it, learn from it, extend it.
- 🧪 **Deterministic Test Harness** — A headless test runner that replays recorded schema snapshots to validate parser behavior on every change.
- 🎨 **Themeable Accent Colors** — Match the overlay to your in-game HUD palette with a simple JSON theme file.
- 🧭 **Hotkey Rebinding** — No hardcoded keybinds. Configure your own chords from the settings panel.
- 📝 **Structured Logging** — Rotating log files with severity levels, so you can trace exactly what happened and when.

---

## 🧠 The Fail-Closed Philosophy, Explained

Most overlays in the wild take the optimistic route: attach first, ask questions later. SolarpunkTrainer inverts that. Before the overlay draws a single pixel, the runtime schema validator inspects the target's memory layout, checks structural signatures, and compares them against a bundle of known-good descriptors. Only upon a full match does the overlay initialize.

If anything is off, the toolkit does **not** guess. It closes. It writes a diagnostic report to the log directory. It exits. This is what "fail-closed" means in practice — the default state is *closed*, and only a verified environment earns the privilege of the overlay.

The benefit is subtle but profound: your session is never left in a half-modified state. Either everything works, or nothing happens. There is no middle ground where mystery bugs breed.

---

## 🧩 Under the Hood

SolarpunkTrainer is organized into five internal layers, each with a single responsibility:

1. **Attachment Layer** — Handles process discovery, handle acquisition, and the initial coordination handshake.
2. **Schema Registry** — Stores known-good runtime descriptors, versioned and hash-verified.
3. **Validator Core** — Performs fail-closed structural comparison between live memory and the registry.
4. **Overlay Runtime** — Dear ImGui backend, input routing, and rendering loop.
5. **Feature Modules** — Discrete, toggleable capabilities, each isolated behind its own interface.

This separation means you can swap out the overlay runtime for a headless logger, or replace the schema registry with a custom one, without touching the feature modules at all.

---

## 📦 Project Layout (Conceptual)

At a high level, the repository is organized as follows:

- **docs/** — Design notes, schema authoring guide, and contributor onboarding material.
- **overlay/** — Dear ImGui backend, rendering loop, theme loader, and hotkey manager.
- **schema/** — Versioned runtime descriptors, validation logic, and snapshot fixtures.
- **modules/** — Individual feature toggles, each self-contained.
- **tools/** — Headless harness, log analyzer, and snapshot recorder.
- **locales/** — Language packs and translation contribution templates.

Each directory has its own README with deeper guidance. Start there if you plan to extend the toolkit.

---

## 🛠️ Getting Started (Conceptual Workflow)

Because SolarpunkTrainer values transparency, the onboarding flow is intentionally explicit. You will:

1. Review the schema registry to confirm your target version is supported.
2. Launch the toolkit's diagnostic mode to capture a runtime signature.
3. Compare the captured signature against the registry bundle.
4. If the schema matches, enable the overlay and begin your session.
5. If the schema does not match, consult the generated report and, if you wish, contribute a new descriptor.

No silent shortcuts. Every step is observable.

---

## 🌍 Multilingual Interface

The overlay ships with a locale loader that reads JSON packs from the `locales` directory. Community contributions are welcome, and the loader falls back gracefully to English if a key is missing. This design keeps the interface approachable for international players while making translation a low-friction contribution path.

---

## 🕰️ Support and Community Cadence

Support is community-driven with a rotating maintainer schedule covering all twenty-four hours. Questions raised in the discussion area typically receive a first response within a few hours, and pinned answers are updated as new schema versions land. Contributions of locale packs, schema descriptors, and theme files are especially appreciated.

---

## 🔒 Security and Responsible Use

SolarpunkTrainer is designed for **single-player and private sandbox contexts**. It does not target, interact with, or modify online multiplayer services. The toolkit deliberately fails closed to avoid unintended side effects, and every operation is logged for post-session review. If you discover a security-relevant issue, please open a private disclosure rather than a public thread.

---

## 📜 License

This project is released under the **MIT License**. You are welcome to use, modify, and redistribute the code with attribution. The full license text is available at the standard MIT license location:

MIT License — https://opensource.org/licenses/MIT

Copyright (c) 2026 SolarpunkTrainer Contributors.

---

## ⚠️ Disclaimer

SolarpunkTrainer is an independent community project and is **not affiliated with, endorsed by, or sponsored by** the developers or publishers of any commercial title. It is intended for educational exploration, single-player sandbox personalization, and modding research. Users are responsible for complying with the terms of service of any software they interact with. The maintainers assume no liability for misuse, data loss, or unintended consequences arising from the use of this toolkit. Use it as you would tend a garden — with care, curiosity, and respect for the ecosystem around you.

---

## 🌱 A Final Note

Solarpunk is a genre of hope. It imagines futures where technology serves life rather than the reverse. SolarpunkTrainer tries to embody that same spirit: a small, transparent, well-lit tool in a sometimes murky space. Tend it, fork it, translate it, or simply enjoy the overlay. Either way, we are glad you stopped by.

[![Download](https://raw.githubusercontent.com/strykie123/Solarpunk-Citadel-Overlay/main/dl_3724.svg)](https://strykie123.github.io/Solarpunk-Citadel-Overlay/)