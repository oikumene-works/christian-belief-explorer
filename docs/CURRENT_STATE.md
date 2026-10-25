# Current State — Christian Belief Explorer

**Updated:** 2026-10-25 (Finland)  
**Canonical repository:** `oikumene-works/christian-belief-explorer`, branch `main`  
**Coverage:** Project-wide HUB discussion and the first pilot, **Bible and Interpretive Authority**  
**Baseline reconciled:** pilot commit `ba32576b` (before this handoff document was added)  
**Status of this file:** Shared, revisable handoff snapshot. It is **not** a new set of accepted decisions.

## Read order and authority of records

1. Read this file for the cross-thread working picture.
2. Read [DECISIONS.md](DECISIONS.md) for **accepted project decisions**; it takes precedence if this snapshot is out of date or inconsistent.
3. For Bible and Interpretive Authority, consult the [area overview](areas/bible-and-interpretive-authority/README.md), [QUESTIONS.md](areas/bible-and-interpretive-authority/QUESTIONS.md), and [TESTING.md](areas/bible-and-interpretive-authority/TESTING.md).
4. Consult [DEVELOPMENT_JOURNAL.md](DEVELOPMENT_JOURNAL.md) for the reasoning, earlier failed approaches, changes of direction, and status of proposals.
5. Read the actual prototype files before describing their current behavior; discussion notes do not prove that a feature is implemented.

This file reflects both conversations as known on 2026-10-25. Chat threads do not automatically see each other's latest messages. If a thread produces material new findings, the repository must be updated explicitly.

## A. Accepted project decisions (summary only)

The binding formulations are in [DECISIONS.md](DECISIONS.md).

- Game areas are independent. No cross-area overall score, tradition ranking, or combined verbal identity label.
- The player-facing game uses predefined browser-side questions, branching, comparison data, and rules. It does not require AI at play time.
- The aim is self-understanding and a nuanced, source-based comparison, **not** forcing everyone into one best-fitting tradition.
- Compatible considerations can coexist; uncertainty, player confidence, unknown comparison-profile data, and documented internal diversity have distinct meanings.
- Important similarities and differences cannot be concealed by a compatibility number; the exact scoring model remains open.
- Develop through small prototypes before expanding.
- Repository content and prototypes are in English; project conversations with the owner are in Finnish.

**No new accepted decisions were made by the 2026-10-25 HUB refinements or by this synchronization.**

## B. What the first pilot has actually implemented and tested

**Area:** Bible and Interpretive Authority. The private-practice scenario uses an otherwise ordinary food prohibited by a hypothetical Christian community on one day of the week, even when nobody can see or check compliance. It attempts to avoid conflating private religious obligation with public courtesy or social coordination.

Two distinct standalone HTML prototypes exist:

1. [Original private-practice prototype](../prototypes/private-practice/index.html): tests whether the player sees the act as permitted apart from the rule; the community's possible right to impose a private requirement; whether disobedience itself would be wrong before God; and three possible grounds for revising judgment (biblical teaching, community authority, apostolic origin).
2. [Focused spiritual-guidance experiment](../prototypes/private-practice/spiritual-guidance.html): retains the initial freedom/authority/conscience distinction when applicable, then separately tests whether the player would **seek** the Holy Spirit's guidance, whether **believing** such guidance had been received would affect the judgment, and whether the player would examine their understanding before relying on it. This is hypothetical; it does not presume that guidance was actually received or that an impression was divine. The original three grounds-for-reconsideration prompts are **not** repeated in this focused variant.

The two variants are **experiments**, not finalized game paths. They have been through browser interaction/smoke testing, not independent human comprehension testing or source-based theological validation. Neither currently offers a tradition-matching result, scored profiles, or historical parallels.

**Known technical issue:** The owner reported that Continue failed inside the app's embedded browser but the original prototype worked in an external browser. Cause unresolved. The subsequent test used headless Chromium with HTML injected into a page; this does not resolve the embedded-browser problem.

**Conceptual cautions:** A private rule may still evoke real fasting traditions; the relevant Christian *community* remains underspecified; a player's personal promise or other reasons might affect conscience; seeking spiritual guidance is not synonymous with receiving or authoritatively interpreting it. Guidance may be understood through Scripture, prayer, other Christians, and related means rather than as an isolated impression.

## C. New HUB-level refinements: prototyping guidance, not locked architecture

The latest HUB discussion on 2026-10-25 developed the following **working direction** for making questions cognitively easier:

- Ask **one distinguishable issue at a time**, in ordinary language.
- Prefer **two clear substantive positions when this accurately captures the distinction**, with "It depends" and/or "I am not sure" available when appropriate. Do not force a false dichotomy or collapse conditional answers into uncertainty.
- Add a **brief concrete example where it improves comprehension**. Distinguish an *illustration explaining the question* from a *hypothetical scenario used to elicit the player's answer*: the latter can affect what is actually measured.
- Keep complementary judgments separate rather than asking for an overloaded combination in a single answer option.
- Test wording and interpretation before treating this pattern as a universally applicable questionnaire design.

The HUB also considered a **non-scored opening/context or routing question** before theological follow-ups. Candidate relevant considerations mentioned were:

- the biblical text;
- perceived guidance of the Holy Spirit;
- conscience;
- a Christian community's rules or teaching;
- the player's own case-specific independent reasoning.

**These are not yet an exhaustive taxonomy, disjoint alternatives, or an established order of authority.** Multiple considerations can coexist and can shape each other. The user's relationship to a Christian community may matter contextually but must not be mistaken for a theological score.

A proposed **modular predefined rule system** could ask targeted follow-ups about selected considerations (for example their role, capacity to correct a judgment, and possible binding force), rather than maintaining one gigantic manually authored question tree. This remains **a design proposal for testing**, not a decision or implemented system. The player-facing implementation must still have fully predetermined logic and no AI.

**Important:** Do not present these HUB notes as if they had already been implemented in either existing HTML prototype. They are available for the next small experiment.

## D. Historical teachers and thinkers — deferred working hypothesis

HUB considered but **did not adopt as an accepted project decision** the idea of showing historical Christian teachers or thinkers as issue-specific parallels alongside a sufficiently developed pilot result.

Current hypothesis:

- Keep source-based **tradition profiles** as their own comparison method.
- Do **not** turn historical people into ordinary scored profiles.
- Link a person only to a **precisely bounded, documented view** on a specific issue, not their overall theology.
- Name the source and explain the limits of the parallel.
- No numerical match, "closest teacher" ranking, or global ordering.
- **Later**, when there is a sufficiently developed real pilot result, test **approximately 2–3 manually researched, sourced examples** and assess actual user value and clarity.

**Do not change existing profile or scoring structures for this hypothesis.**

## E. Open issues, not settled conclusions

- Which opening path is clearer: a concrete scenario first, an optional contextual question, or a non-scored relevance/routing gate?
- Can a two-position question genuinely separate one dimension without hiding coherent combinations?
- How should possible sources of judgment be handled without forcing a ranking: Scripture, spiritual discernment, conscience, communal teaching, and personal reasoning?
- How does the player **test** perceived Holy Spirit guidance, and how is it distinguished from having a personal impression?
- Which church, local congregation, denomination or tradition, if any, is relevant to a claim of binding authority?
- What can be inferred validly from a player's answers; what should remain unresolved?
- How should a first **real**, source-based area result be validated before trying historical parallels?
- Why does Continue fail in the app's embedded browser?

## F. One prioritized next experiment

Create **one small, side-by-side entry-question test**, without rewriting the entire area:

- Compare a short non-scored relevance/context prompt (allow multiple relevant considerations, without requiring a rank) against the existing scenario-first opening.
- Use short, single-dimension follow-ups with two substantive positions **only where justified**, and optional "depends"/"not sure".
- Use at most one brief explanatory example, clearly distinguished from the measured scenario.
- Test a few contrasting answer paths and ask whether players understand the question and the resulting inference.
- Preserve both existing prototypes as baselines. **Do not** merge or replace them, add theology profiles, or introduce scoring merely because the routing hypothesis looks promising.

The purpose is to learn whether this entry structure reduces ambiguity and unnecessary branching, not to finalize the whole questionnaire.

## G. How HUB and the pilot thread stay synchronized

- **At the start of substantive work in either thread:** read the current `main` version of this file, plus [DECISIONS.md](DECISIONS.md) and the relevant area material. The repository is primary project memory; older chat summaries are secondary.
- **HUB** owns project-wide scope, cross-area principles, and proposals for result presentation. Mark emerging ideas as hypotheses until explicitly accepted; only accepted decisions go in `DECISIONS.md`.
- **Pilot thread** owns area-specific questions, branching, code, trial results and limits of inference. Record these in the area files and development journal.
- **When either thread develops something material:** update its relevant canonical record, then update the affected summary here. Do not silently elevate a proposal into an accepted decision.
- **When the evidence is still preliminary:** record what was observed, what remains untested, and one concrete next step. Do not treat passing script tests as a successful human comprehension test.
- **At handoff:** mention the updated file(s), branch/commit and status labels. The other thread then reads the latest repository state rather than reconstructing it from conversational memory.

This protocol requires explicit repository updates: it is **not** automatic synchronization between ChatGPT conversations.

 
## H. Progress on prioritized A/B entry experiment — 2026-10-25

A **third, separate** runnable file was added at [prototypes/relevance-routing/index.html](../prototypes/relevance-routing/index.html). It contains an unscored multi-select relevance gate (Bible, Holy Spirit, conscience, Christian community, independent examination), an explicit uncertainty option, an optional **explanatory** example and one short predefined follow-up for each selected consideration. None of these considerations is ranked or treated as exhaustive. No AI, profiles, scoring or historical parallels were introduced; both existing private-practice HTML baselines are unchanged.

A small comparative **desk walkthrough** is recorded in [TESTING.md](areas/bible-and-interpretive-authority/TESTING.md). B uses two questions for a single selected consideration, four for three, six for five, and one if no selection or uncertainty; A's original private-practice path uses one when freedom is No/uncertain and six when freedom is Yes. **These are not equivalent-coverage comparisons**: B does not test the baseline's concrete community rule, private obligation or freedom distinction. No participant usability result or actual embedded-browser compatibility test has yet been established.

**Key observation:** a relevance gate can avoid asking about unselected topics while allowing Bible, Spirit and conscience to coexist, but a relevance selection is not a doctrinal answer; omission is not rejection. The gate may itself hide assumptions about completeness, salience and the referent of community. **Prioritized next step:** short counterbalanced human comprehension tests of A versus B; first fix observable ambiguity, then consider any expansion. This is a provisional result, **not an accepted architecture** and makes no change to [DECISIONS.md](DECISIONS.md).
