# Single-question historical-voices concept experiment

**Status:** Working concept, source-feasibility check, and first runnable prototype. Not an accepted product architecture or questionnaire decision.

**Date:** 2026-11-18

## Product hypothesis

The experience may be organized as independent question units rather than as a cumulative tradition-matching game.

Each unit would contain:

1. one self-contained theological question;
2. the smallest response structure that faithfully represents the relevant formed positions;
3. a bounded statement of what the player's answer means;
4. a curated set of source-based Christian historical voices addressing the same issue or a closely bounded equivalent issue;
5. explicit limits on each historical parallel.

Question units would be available in any order. An answer in one unit would not alter another unit, create a cumulative score, or contribute to a combined theological identity profile.

This is a working hypothesis for prototyping, not yet an accepted project decision.

## First runnable prototype

- [Open the standalone prototype](../../../prototypes/single-question-historical-voices/index.html)
- [Testing status](TESTING.md)

The prototype asks one question, records **Yes**, **No**, or **no settled view**, and then shows the same three historical voices to every player. The selected answer changes only their order and the short relationship explanation. No score, tradition label, cumulative state, or historical-person profile is created.

Historical names are hidden until after the player answers.

## Plain-language player question

The earlier research wording used terms such as *teaching authority*, *duty before God*, and *accept*. The player-facing prototype replaces that wording with ordinary language:

> Suppose you have studied a Bible passage carefully and still think your church explains it wrongly. Could there ever be a case where God expects you to accept your church’s explanation as right because the church has the responsibility to teach its members?

A visible clarification says that *accept as right* means believing one ought to affirm the explanation, not merely following a shared rule, keeping quiet, or listening seriously to the church's reasons.

This wording is itself experimental. It must be tested with people who do not know theological terminology.

## Research formulation behind the question

> Can a Christian church's teaching authority ever make it a duty before God for one of its members to accept the church's interpretation of Scripture, even if that member has carefully considered the biblical text and still disagrees?

Research clarifications:

- **Ever** means at least one possible case, not every church or every teaching.
- **Accept** means treating the teaching as something one ought to affirm, not merely following a public rule or considering the argument.

## Source-feasibility result

The question appears suitable for a first concept prototype because at least three historically significant voices can be connected to the issue from primary texts without presenting them as complete theological profiles.

The relationship is not equally direct in every case. The prototype distinguishes a strong parallel from a qualified or context-limited one.

### Thomas Aquinas — strong affirmative parallel

In *Summa Theologiae* II-II, question 5, article 3, Aquinas describes the teaching of the Church as an "infallible and Divine rule" proceeding from divine truth manifested in Scripture. He says that a person adhering to the Church as that rule assents to whatever the Church teaches rather than selecting articles by personal judgment.

**Relation to the prototype question:** strong affirmative parallel to the possibility that ecclesial teaching authority can require assent.

**Limit:** Aquinas is discussing faith, heresy, and articles of faith, not every interpretation, local rule, sermon, or institutional statement.

Primary text:

- https://www.newadvent.org/summa/3005.htm
- https://www.ccel.org/a/aquinas/summa/SS/SS005.html

### John Calvin — real but defeasible prior weight

In *Institutes of the Christian Religion* IV.9.8, Calvin rejects treating councils as automatically decisive, but he also rejects dismissing them at will. A council's decision should have weight as a prior judgment, while the matter must still be tested by Scripture. He gives Scripture the highest place.

**Relation to the prototype question:** a qualified historical position between treating ecclesial judgment as independently decisive and treating it as having no special standing.

**Limit:** Calvin's passage concerns the authority and examination of councils. It does not directly answer every aspect of the prototype's language about an individual member's duty to assent while remaining personally unconvinced.

Primary text:

- https://ccel.org/ccel/calvin/institutes.vi.x.html

### Martin Luther — strong negative parallel in a concrete conflict

In his account of the Diet of Worms, Luther says he cannot recant unless convinced by Scripture or evident reason, because popes and councils can err and his conscience is bound by the Word of God.

**Relation to the prototype question:** strong negative parallel to the claim that ecclesial authority alone can require assent against a continuing scripturally grounded judgment.

**Limit:** this is a statement made in a specific controversy and proceeding. It must not be expanded into a complete account of Luther's doctrine of church, ministry, councils, confessions, or obedience.

Primary-source presentation:

- https://germanhistorydocs.org/en/from-the-reformations-to-the-thirty-years-war-1500-1648/ghdi:document-4371

## Editorial model implemented

All players see the same curated historical voices after answering. The player's answer may change the ordering and the short relationship label, but opposing voices are not hidden.

Each card contains:

- name, period, and context;
- the bounded historical view;
- relationship to the player's answer: similar, different, or partly parallel;
- the most important limit of the comparison;
- a primary-source link.

The prototype does not use percentages, "closest thinker," or language implying similarity in overall theology.

## What this experiment tests

The prototype should test whether:

- the main question is understandable without theological vocabulary;
- one question already feels like a complete and worthwhile experience;
- historical voices improve self-understanding rather than merely confirm the chosen answer;
- the limits of issue-specific comparison are understandable;
- famous names overshadow the actual view and reasoning;
- the research effort required for one unit is proportionate to the user value;
- the concept remains useful when no historical voice matches the player exactly;
- the experience makes another independent question appealing.

## Next step

The project owner should try their own genuine answer path and assess the question, answer summary, historical cards, comparison limits, and overall value. Do not add cumulative scoring, tradition profiles, cross-question state, a historical-person database, or additional question units before evaluating this first end-to-end experience.
