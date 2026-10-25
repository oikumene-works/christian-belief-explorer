# Bible and Interpretive Authority

**Status:** First pilot area — early design and prototyping

This area explores how a player understands the authority of Scripture, tradition, church teaching, interpretive decisions, and personal judgment.

It is the first area used to develop the general mechanics of Christian Belief Explorer.

## Current purpose

The pilot should help a player clarify questions such as:

- What gives Christian teaching authority?
- What role does Scripture play as a norm?
- What weight should historical or apostolic tradition have?
- What role may church teaching or church authority have?
- Who, if anyone, may make a binding interpretive decision?
- What does "binding" mean: common practice, doctrinal assent, conscience, or something else?
- What happens when the player's own interpretation appears to conflict with an established teaching?
- Can some disagreements remain unresolved?

The goal is not to force these questions into one binary axis.

## Current design direction

The most promising approach so far is:

1. begin with a practical, understandable situation;
2. use ordinary language;
3. ask a short question about one dimension;
4. select a predefined follow-up when clarification is needed;
5. keep distinct dimensions separate rather than embedding them in one long answer option;
6. show the player what has been inferred before using that inference in tradition comparison;
7. compare the resulting view with named, source-based profiles.

This is still a working direction rather than a final architecture.

## Important findings already established by prototyping

### The referent of "church" cannot be assumed

"Church" may mean:

- the universal church;
- a denomination;
- a local congregation;
- an institution or teaching office;
- a Christian tradition.

The player's relationship to that referent also matters.

A contextual question may therefore be needed before a theological answer can be interpreted.

### Public compliance is not the same as conscience-level obligation

A prototype involving standing during common prayer was found to be a poor test of internal authority.

A player may follow a visible communal practice for order, courtesy, or social reasons while denying that the practice is religiously binding.

Future scenarios testing conscience or authority should prefer private behavior that other people do not observe or enforce.

### Different logical questions must be separated

One draft question mixed:

- the highest norm;
- the authority of an interpreter;
- the method of investigating conflict;
- the person who ultimately forms a conviction.

Blind testing showed that these can coexist in combinations and should not automatically be treated as competing answers.

### Personal judgment is ambiguous

A statement such as "I must ultimately decide for myself what interpretation I accept" may mean either:

- the unavoidable personal responsibility to form one's own conviction; or
- a stronger claim that no external authority can bind the individual against that conviction.

These must not be treated as the same position.

## First runnable prototype

A narrow [private-practice prototype](../../../prototypes/private-practice/index.html) now explores a fictional dietary rule that nobody can observe or check. Download its standalone HTML file and open it in a browser. It uses predefined questions and browser-only logic; no AI, score, tradition comparison, or external service is involved.

This remains a baseline experiment, not an accepted questionnaire.

A second [spiritual-guidance experiment](../../../prototypes/private-practice/spiritual-guidance.html) retains the same private-practice scenario and core distinctions, then tests three short questions about seeking the Holy Spirit's guidance, the possible weight of a believed guidance, and examining one's understanding of it. The original prototype remains unchanged for comparison. This second experiment temporarily leaves aside the original three questions about biblical, communal, and apostolic grounds; it does not replace or rank them.

Both experiments are documented in [QUESTIONS.md](QUESTIONS.md), with behavior checks and unresolved questions in [TESTING.md](TESTING.md). Neither is a final questionnaire or an accepted tradition-profile model.

## Pilot documentation

- [QUESTIONS.md](QUESTIONS.md) — the currently tested question path, answer options, routing, and inference limits;
- [TESTING.md](TESTING.md) — smoke checks, candidate blind tests, and caveats.

Still planned: `TERMS.md` (controlled vocabulary), `PROFILES.md` (source-based comparisons), and `SCORING.md` (comparison rules). These should not be treated as settled or implemented.

## Current open questions

Among the major unresolved issues are:

- the exact opening question or scenario;
- how much contextual information should be collected before theological questions;
- when a concept should be explained versus demonstrated through an example;
- the final structure of branching;
- the exact set of comparison profiles;
- the scoring/comparison model;
- whether and when profile names should be visible;
- how to represent documented internal variation within traditions;
- how to present aggregate compatibility without hiding important differences.

## Project-wide references

- [Current state and cross-thread handoff](../../CURRENT_STATE.md)
- [Project README](../../../README.md)
- [Decisions](../../DECISIONS.md)
- [Development Journal](../../DEVELOPMENT_JOURNAL.md)

 
## Parallel relevance-first entry experiment (2026-10-25)

A separate [relevance-routing prototype](../../../prototypes/relevance-routing/index.html) tests a single unscored multi-select consideration gate followed by one predefined follow-up per selected consideration. It preserves multiple relevant considerations and explicitly limits inference. This is an A/B entry experiment, **not** a replacement of either private-practice baseline or evidence that routing is easier for human respondents. See [QUESTIONS.md](QUESTIONS.md) and [TESTING.md](TESTING.md) for the design and initial walkthrough matrix.

---


## B2: two positions and a separate unsettled-view control

A [separate B2 prototype](../../../prototypes/relevance-routing/yes-no-unsettled.html) tests **Yes/No** as the two substantive follow-up choices, with a separate action for having no settled view. It keeps multi-select relevance routing while narrowing follow-up wording. [The original B](../../../prototypes/relevance-routing/index.html) and both private-practice variants are unchanged. This experiment does not settle how a *definite conditional* position should be recorded. Details and interpretation limits are in [QUESTIONS.md](QUESTIONS.md) and [TESTING.md](TESTING.md).

---

## B2 stress test: conscience-binding interpretation

A [separate one-question prototype](../../../prototypes/relevance-routing/conscience-binding-authority.html) now tests whether **any** church teaching authority can impose an obligation before God to accept a scriptural interpretation despite continued personal disagreement. It uses **Yes / No** and a separate **unsettled-view** action, with an optional explanatory example. The existential wording captures one settled-conditional view without making a universal claim, but leaves qualifying conditions unresolved. Local Chromium interaction checks passed; **human comprehension and blind testing have not occurred**. See [QUESTIONS.md](QUESTIONS.md) and [TESTING.md](TESTING.md). All prior B/B2 and private-practice baselines are preserved.
