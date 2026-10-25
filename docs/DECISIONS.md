# Project Decisions

This file records decisions that are currently accepted for the Christian Belief Explorer project.

It is not a list of every idea considered during development. Experiments, rejected approaches, and unresolved questions belong primarily in the [Development Journal](DEVELOPMENT_JOURNAL.md) or in area-specific documentation.

## Status labels

- **Accepted** — currently governs the project.
- **Superseded** — was previously accepted but has been replaced by a later decision.

---

## 2026-10-23 — Each area is independent

**Status:** Accepted

Each game area is an independent unit.

Results from different areas must not be combined into:

- a shared overall score;
- a global ranking of traditions;
- an overall verbal profile of the player.

An area may be completed independently, and its result is based only on that area's answers, comparison profiles, and comparison/scoring rules.

**Reason:** Different theological areas may require different questions, evidence, profiles, and comparison logic. Combining them would create a stronger claim about the player than the underlying data warrants.

---

## 2026-10-23 — First pilot area

**Status:** Accepted

The first pilot area is **Bible and Interpretive Authority**.

The pilot is the primary place for developing and testing:

- question wording;
- branching;
- comparison profiles;
- scoring/comparison logic;
- result presentation;
- usability of theological concepts for ordinary users.

---

## 2026-10-23 — No AI is required during gameplay

**Status:** Accepted

The player-facing game is intended to operate with predefined data and rules in the browser.

Questions, answer options, branching rules, comparison profiles, and scoring/comparison rules are authored in advance.

The game must not require an AI model to interpret the player's answers or generate the next question dynamically.

**Reason:** Predictability, inspectability, reproducibility, privacy, and accessibility to users who do not want AI involved are part of the product concept.

AI may still be used during research, design, testing, or development.

---

## 2026-10-23 — The goal is exploration, not forced classification

**Status:** Accepted

The primary purpose is to help players clarify their own thinking and compare it with established Christian models.

The game does not need to find one single, fully matching theological category for every player.

A player may:

- resemble different profiles on different comparison points;
- combine positions that do not correspond exactly to one named profile;
- remain uncertain on some questions;
- receive a useful result without an exact match.

**Reason:** The comparison profiles are reference models, not exhaustive containers for every possible individual belief structure.

---

## 2026-10-23 — Multiple complementary views may be expressed

**Status:** Accepted

Where the subject permits it, the interface must allow a player to express more than one compatible consideration.

Answer design must not force artificial either/or choices when several statements may reasonably be true at the same time.

This does not mean that every question should be multi-select. If several dimensions are being mixed together, separate follow-up questions may be preferable.

---

## 2026-10-23 — Uncertainty and missing data are distinct states

**Status:** Accepted

The project must distinguish between:

- a player whose own position is open or uncertain;
- a comparison profile for which the relevant information is not yet known;
- documented internal diversity within a tradition.

These states must not be collapsed into the same neutral score or "unknown" category.

---

## 2026-10-23 — Confidence is separate from the position itself

**Status:** Accepted

A player's theological position, confidence in that position, and attitude toward alternative positions are separate dimensions.

Confidence must not be used to shift the substantive theological answer toward another position.

---

## 2026-10-23 — Important differences remain visible alongside any aggregate score

**Status:** Accepted

Within an area, compatibility tables, weights, averages, or other aggregate measures may be experimented with.

However, any overall number must be accompanied by meaningful named similarities and differences.

Different question sets do not become comparable merely by attaching a coverage indicator.

The exact scoring method remains open.

---

## 2026-10-25 — Prototype before scaling

**Status:** Accepted

Small, working prototypes should be used before committing to larger structures.

The normal development loop is:

1. formulate a limited idea;
2. make it concrete enough to experience;
3. test it;
4. identify what the test reveals;
5. revise the model;
6. only then expand it.

**Reason:** The project has repeatedly exposed conceptual and wording problems only after a question path was experienced in practice.

---

## 2026-10-25 — Repository and documentation language

**Status:** Accepted

The canonical repository is:

`oikumene-works/christian-belief-explorer`

All repository content, including draft player-facing wording and prototype interfaces, is written in English.

Development discussion with the project owner may take place in Finnish.

---

## 2026-10-25 — Repository license

**Status:** Accepted

The repository uses **CC0 1.0 Universal** for original project material unless otherwise noted.

The intention is to allow others to reuse, modify, redistribute, and build upon the project's original material as freely as possible, including commercially and without an attribution requirement.

Third-party material is not relicensed by this decision.
