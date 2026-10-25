# Development Journal

This journal records the path of the Christian Belief Explorer project: problems encountered, experiments tried, observations made, and the reasons behind changes in direction.

It is intentionally different from a changelog. The goal is to preserve enough of the design journey that a future contributor — or someone building a different project — can understand not only what the current design is, but why earlier approaches were changed or abandoned.

For current binding project decisions, see [DECISIONS.md](DECISIONS.md).

---

## 2026-10-20 — Pilot work begins with interpretive authority

The first pilot area was chosen as **Bible and Interpretive Authority**.

Two initial question ideas were used as a starting point:

1. What gives Christian teaching its authority?
2. Who has the right to resolve interpretive disagreement, and in what sense is that resolution binding?

The initial plan was to compare player answers with named, source-based tradition profiles using a compatibility table, possibly followed by a weighted average and a separate confidence measure.

At this point, exact profiles, weights, scoring rules, and the timing of profile-name disclosure were explicitly left open.

### Lessons imported from comparison research

A small survey of existing question-based religious or theological comparison tools produced several design constraints:

- a player's open position is not the same thing as missing profile data;
- missing profile data is not the same thing as documented internal diversity;
- percentages derived from different question sets do not become comparable merely by showing a coverage percentage;
- a person's substantive position, confidence in it, and attitude toward other positions should be kept separate;
- several complementary beliefs may need to be expressed at once;
- important differences should remain visible alongside any aggregate result.

These became constraints on later prototypes rather than a final scoring system.

---

## 2026-10-23 — Independent areas replace the idea of a global result

A structural decision was made that every game area is independent.

The project will not combine different areas into a single total score, tradition ranking, or verbal profile of the player.

### Why this mattered

A global result would suggest a degree of commensurability between theological areas that had not been established. Different areas may need different questions, profile coverage, weighting, and interpretation rules.

This decision allowed the pilot to focus on solving one area well rather than prematurely designing a universal scoring architecture.

---

## 2026-10-23 — From a fixed questionnaire toward predefined branching

A new idea was tested: perhaps only the opening question needs to be fixed, while later questions can be selected from a predefined question tree according to earlier answers.

The important constraint was that the follow-up questions are **authored in advance**. They are not generated dynamically by AI.

### Why this seemed promising

A fixed list of abstract questions tended to require too many distinctions inside individual answer options.

Branching offered another possibility:

- start with an understandable situation or broad question;
- identify what is still unclear in that particular player's answer;
- ask only the relevant predefined clarification;
- continue until the intended comparison point is sufficiently clear.

This also reduced pressure to force every player through distinctions that may not matter to their position.

### Status

Promising working direction, not yet a locked implementation rule.

---

## 2026-10-23 — The product goal is reframed more explicitly around self-understanding

During prototype discussion, an important emphasis became clearer:

The game is not primarily trying to discover the one theological box that perfectly contains the player.

Its more useful function is to help the player see their own thinking more clearly and then compare that thinking with established models.

### Consequence for result design

A useful result might say that the player:

- shares one feature with one profile;
- differs from it on another;
- resembles another profile elsewhere;
- has not yet formed a position on a third point.

That can be more informative than a single high compatibility percentage.

---

## 2026-10-23 — First small interactive prototype

A deliberately small prototype was built around one interpretive situation with at most a few follow-up questions.

It included:

- predefined branching;
- the ability to choose complementary answers;
- short feedback describing what had been inferred;
- the ability to correct that feedback;
- a small number of source-linked comparison points;
- example answer paths.

### Immediate observations

The working prototype exposed assumptions that were less obvious in abstract discussion.

Terms such as **church**, **tradition**, and **long-standing teaching** were too underspecified.

For example:

- Does "church" mean the universal church, a denomination, a local congregation, an institution, or a tradition?
- Does the player belong to the church being referenced?
- If not, why is that church a relevant authority or reference point?
- "Long-standing teaching" — whose teaching?

This produced a broader design insight:

**Branching may need to clarify the referent of a question before it clarifies the player's theological position.**

A contextual choice can therefore affect wording without itself being scored as a theological answer.

---

## 2026-10-23 — More personal wording is tested

Questions were reformulated in a more personal form, often using hypothetical situations:

> If your interpretation of a biblical passage differed from how a Christian tradition meaningful to you had long understood it, what significance would that have for you?

The goal was to move from abstract doctrinal terminology toward the player's own act of judgment.

### Benefit

The player can respond to a recognizable situation without first mastering technical vocabulary.

### Risk

Personal scenarios can silently introduce assumptions of their own. The scenario must not decide in advance:

- what "church" means;
- whether the player belongs to one;
- whether a historical tradition is genuinely apostolic;
- whether disagreement is between two independent authorities.

This reinforced the need for careful concept handling.

---

## 2026-10-23 — A wording failure reveals mixed dimensions

One follow-up asked what ultimately resolves a conflict between an allegedly apostolic teaching and the player's own interpretation of Scripture.

An answer option initially combined two separate claims:

- that apostolic origin would not substantially change the teaching's weight;
- that the decisive issue would still be how well it could be justified from Scripture.

During live testing it became clear that the second claim could also be held by someone who gave apostolic tradition considerable weight.

### Lesson

If an answer option contains a reason that could equally belong to another option, the option may be mixing dimensions.

This became an early warning sign for later question design.

---

## 2026-10-23 — Blind testing process is prototyped

A single draft question was sent to a context-isolated temporary chat as a blind test.

The tester was instructed to:

1. explain what it thought the question meant before improving it;
2. identify ambiguous concepts;
3. identify hidden assumptions;
4. inspect each answer option for overlap and multiple claims;
5. identify missing reasonable positions;
6. state what could and could not safely be inferred from each answer.

Medium reasoning was used so that the tester would perform meaningful conceptual analysis without turning the task into a full independent theological reconstruction.

### What the blind test found

The central finding was that the question was mixing several different logical dimensions:

- What is the highest norm?
- Whose interpretation has authority?
- How should an apparent conflict be investigated?
- Who ultimately forms the player's personal conviction?

The test independently confirmed that combinations such as **Scripture as the highest norm + the individual still having to make a personal judgment** can be coherent.

It also identified a missing possibility:

- reconsider both the player's interpretation of Scripture **and** the claim that the competing teaching is genuinely apostolic, rather than granting automatic priority to either side.

Another missing possibility was that the disagreement may remain unresolved.

### Lesson

A single multi-select question can become too semantically broad even when multiple selection is allowed.

The next design direction became:

**one practical situation, followed by shorter questions that separate distinct dimensions.**

The blind-testing process itself was considered useful and worth repeating after future prototypes.

---

## 2026-10-25 — Concepts may need examples before definitions

The intended audience is not professional theologians.

This raised a usability question: should concepts such as apostolic tradition, binding teaching, or teaching authority be explained through definitions, practical examples, or both?

The current working direction is layered:

1. begin with an understandable situation;
2. ask the question in ordinary language;
3. provide an optional short explanation where a technical concept is unavoidable;
4. use a follow-up question only when the distinction becomes relevant.

### Why not definitions alone?

Definitions can turn the game into a theology textbook before the player has encountered the problem the term is meant to describe.

### Why not examples alone?

An example can silently narrow the concept or introduce a separate doctrinal controversy.

Examples therefore need to be concrete enough to understand but neutral enough not to dominate the measured issue.

---

## 2026-10-25 — Adiaphora used as a practical test case

An adiaphora-like scenario was tried to reduce interference from well-known doctrinal controversies.

The first example involved a tradition of standing during common prayer.

The scenario seemed useful at first because Scripture was stipulated not to command or forbid the posture.

### What failed

The player's response revealed a confound:

A member of almost any community may follow a publicly visible common practice simply for social coordination, courtesy, or peace — even while privately disagreeing with it.

Therefore, outward compliance does not reliably reveal whether the player believes the practice is religiously binding.

### Better test direction

A stronger example would concern a practice that:

- is observed privately;
- is not visible to other people;
- is not checked or enforced socially;
- still raises the question whether tradition or church authority binds the player's conscience.

A private dietary or devotional practice was proposed as a better prototype.

### General lesson

When testing authority or conscience, avoid scenarios where social conformity can explain the behavior equally well.

The prototype should isolate the theological variable as much as possible.

---

## 2026-10-25 — Short sequential questions preferred over overloaded answer options

The public-practice prototype also showed that several positions can coexist:

- a congregation may have the right to set a common practice;
- the player may willingly comply for the sake of common order;
- the player may still deny that the practice binds the conscience before God.

Trying to represent all of this through long multi-select answer options quickly became linguistically unstable.

### Current working hypothesis

When an answer option needs several clauses to be precise, split the issue into shorter sequential questions.

For example, separately ask:

1. May the community set a practice?
2. Should the player follow it in the relevant context?
3. Does the practice bind the conscience before God?

This is not yet a final questionnaire architecture, but it is the most promising direction produced by the current prototype cycle.

---

## 2026-10-25 — Canonical repository and development record

The project was moved into its own public repository under Oikumene Works:

`oikumene-works/christian-belief-explorer`

Documentation is to be written in English.

Two complementary records are maintained:

- **DECISIONS.md** — current accepted decisions and their reasons;
- **DEVELOPMENT_JOURNAL.md** — the design journey, including failed experiments and why direction changed.

### Why preserve failed approaches?

A final specification alone would hide much of the project's useful knowledge.

For example, a future contributor might reasonably propose a public worship-practice question without knowing that the same idea had already been tested and found to confound theological obligation with ordinary social conformity.

The journal is therefore intended to preserve the chain:

**idea → prototype → experience → observation → revised direction**

rather than only the cleaned-up final result.

---

## 2026-10-25 — CC0-1.0 chosen for original repository material

CC0 1.0 Universal was chosen for original material in the repository.

The intention is to let other people reuse, modify, redistribute, and build on the project's original work as freely as possible.

Third-party source material remains subject to its own rights.

---

## 2026-10-25 — First runnable private-practice prototype

A standalone, English-language HTML prototype was added at `prototypes/private-practice/index.html`. It uses a hypothetical dietary rule observed privately, not the earlier public standing-during-prayer example. No one checks compliance. The scenario does not assume that the community has legitimate authority to issue the rule.

The initial question asks whether the player regards the practice as permitted **apart from** the community's rule. No and unsure answers terminate this narrow branch without an authority inference, because the supposedly optional act may not be optional to that player.

When the player regards the act as permitted in itself, separate short questions ask (1) whether the community may legitimately require it and (2) whether knowingly breaking that rule would itself be wrong before God. The result can describe these as different judgments. The reverse combination is flagged for further inquiry, not treated as a logical contradiction.

Three additional, separate questions test whether biblical teaching, better grounds for community authority, or evidence of apostolic origin could help settle or revise the conscience judgment. These are **possibilities**, not ranked sources, conclusive grounds, or profile scores.

### What was actually tested

A local headless Chromium smoke test passed early-stop paths, two cross-cutting authority/conscience combinations, ground reporting, back/edit/reset behavior, and narrow-screen rendering. See the area-specific `TESTING.md`. No blind human comprehension test or source-based theological validation has yet been run.

### Remaining risk

A fictional private food restriction may still evoke real fasting traditions. The word *community* remains underspecified in relation to denomination, local congregation, or personal membership. Personal promises and indirect scriptural grounds are not yet modeled.

This is a prototype result rather than a new accepted theological classification or final question architecture.

---

## 2026-10-25 — Hands-on feedback: embedded browser and spiritual guidance

The project owner reported that the prototype's Continue button did not respond in the application's built-in browser, although the entire flow worked in an external browser. This is a compatibility observation; the underlying cause has not been determined.

The exercise also revealed a **content gap**: in practical decisions, the player may seek the Holy Spirit's counsel and guidance. The prototype's three questions about what might settle or revise a judgment mention biblical teaching, community authority, and apostolic origin but not spiritual discernment. Their coverage must not be mistaken for a complete account of Christian decision-making.

A possible future question path should distinguish (1) seeking guidance, (2) believing a particular guidance was received, and (3) deciding how to test or weigh it. These may coexist with attention to Scripture, tradition, and community; do not force them into a single-choice contest without justification. This is an observation and design proposal, not a question revision or settled doctrine.

The owner also raised a **project-level possibility** of showing historically documented Christian teachers or thinkers who expressed a similar view on a specific issue, rather than trying to find a single matching tradition. Its scope and evidence standards belong in a separate product-level discussion; no profile model was changed here.

---


## 2026-10-25 — A separate experiment isolates spiritual discernment

The pilot now has a second runnable HTML variant, `prototypes/private-practice/spiritual-guidance.html`. The original private-practice path is preserved as a baseline. The new variant keeps the initial freedom, community authority and conscience question texts but asks three distinct follow-ups about (1) seeking the Holy Spirit's guidance, (2) the hypothetical significance of believing guidance had been received, and (3) examining one's understanding before relying on it.

The new path does not treat the Spirit as an alternative in an exclusive contest against Scripture or tradition. Nor does a hypothetical question claim that the player has actually received an impression. When freedom is denied or uncertain, it still asks about guidance but avoids inference about community authority. The old questions about possible biblical, community and apostolic grounds were left in the baseline rather than combined with this narrowly scoped experiment.

### What was tested and what was not

A headless Chromium / Playwright script passed branching, contradictory-looking but potentially coherent combinations, summary, editing, reset and mobile-width checks. The test environment prevented file URL navigation, so the exact HTML bytes were injected into a page. This does not reproduce or resolve the previously reported in-app Continue-button failure.

Human comprehension testing, the ways a player examines perceived guidance, and the role of guidance via Scripture, prayer and others remain unresolved. See `QUESTIONS.md` and `TESTING.md`.

---

## 2026-10-25 — HUB handoff: historical parallels remain a deferred hypothesis

The HUB discussion did **not** adopt a project decision about including historical Christian teachers or thinkers in player results. The working hypothesis is to retain tradition profiles as a distinct comparison method, while a possible historical parallel would:

- concern one **specific documented view**, not the teacher's theology as a whole;
- identify a named source and explain the exact scope and limitations of the comparison;
- not turn historical people into ordinary scored profiles;
- not produce a score or a "closest teacher" ranking.

Once the pilot has its first sufficiently developed real result, a **manual trial with approximately two or three sourced historical parallels** may assess whether they improve understanding and whether the limits are clear. Until then, this is deferred. No profile or scoring structures are changed.

---

## 2026-10-25 — Cross-thread handoff reconciles HUB and pilot status

The project-wide HUB and the area-specific pilot had diverged in their **working conversation state**: the repository contained two tested private-practice HTML variants, while the HUB had more recently explored simpler short questions, optional clarifying examples, a possible unscored relevance/context entry gate, and modular predefined routing. These refinements had not yet been implemented or accepted as final architecture.

A shared [CURRENT_STATE.md](CURRENT_STATE.md) was added to distinguish **accepted decisions**, **implemented pilot experiments**, **HUB working directions** and **open questions**. The latest HUB hypothesis about issue-specific, unscored historical-teacher parallels remains deferred; tradition-profile and scoring structures were not changed.

The file defines an explicit handoff practice between the two threads: read current repository records first; update the appropriate canonical file after a material new finding; then refresh the shared snapshot. Chat conversations are not automatically synchronized.

No change to the accepted decisions, question code, profiles, or scoring system was made by this documentation update.

---

## Current position after this journal entry

The project has not yet settled the final question architecture or scoring method.

The most promising design direction currently combines:

- independent game areas;
- predefined rather than AI-generated branching;
- practical situations before unnecessary abstraction;
- short follow-up questions that separate logical dimensions;
- explicit handling of ambiguous theological terms;
- feedback that helps the player inspect their own thinking;
- named, source-based tradition profiles used as comparison models;
- blind testing of question wording and inference rules;
- small working prototypes before larger implementation commitments.

The original private-practice prototype and the separate spiritual-guidance experiment are documented in `docs/areas/bible-and-interpretive-authority/QUESTIONS.md` and `TESTING.md`. The proposed terms, source-based profiles, scoring method and historical parallels remain open; experimental files are not accepted decisions.

---

## 2026-10-25 — A doctrinal-authority stress test of B2's Yes/No presentation

After the owner reported that B2's Yes/No with a separate unsettled-view action felt better than B's parallel “It depends” and “I am not sure”, the next experiment deliberately used a substantively discriminating doctrine-of-authority question rather than another low-stakes question about seeking advice.

An initial natural formulation — whether church interpretation should bind a believer against their own — was found insufficient: someone can coherently distinguish binding, properly authorized doctrinal determinations from local teaching or advice, while having a **settled** position rather than being uncertain. More importantly, outward obedience, serious consideration, and a duty to **assent before God** are not interchangeable.

The resulting [single-question prototype](../prototypes/relevance-routing/conscience-binding-authority.html) asks if ecclesial teaching authority can **ever** impose that narrower duty even while an informed member continues to disagree. This repairs the categorical Yes/No failure for a limited-authority position (Yes means *at least one case*), but loses information about which conditions govern that case. No concerns only this duty, not all ecclesial influence.

A browser-script check passed for Yes, No, unsettled, editing/reset, and narrow layouts. Theological interpretation is still a **desk hypothesis**, not a blind human finding. This is a specific example of the loop **small prototype → predicted edge case → narrowed wording → test before expansion**. Keep the earlier variants intact, and use a separate Temporary Chat for the next blind question analysis if the owner wants to proceed. No accepted project decision was made.


---

## 2026-10-25 — Normal-chat pretest isolates assent versus compliance as the main wording risk

The one-question conscience-binding authority prototype was given a prompt-restricted review at Medium reasoning. The prompt attempted to simulate a first-time Christian respondent and withheld the project's purpose, intended inference, explanatory text, and comparison model. The test was accidentally run in a **normal ChatGPT conversation rather than Temporary Chat**, so prior context cannot be excluded. It is therefore a pretest, not the clean blind test originally intended.

The review largely reconstructed the intended issue, including the importance of **ever** as an existential rather than universal claim. Its main difficulty was the word **accept**. It independently distinguished between:

- a duty to **assent** to the church's interpretation as something one ought to affirm; and
- a duty to **submit or comply** in practice while remaining internally unconvinced.

That distinction generated an apparently third settled position only while *accept* remained ambiguous. Under the intended assent reading, the reviewer itself recognized that practical submission without assent can still answer **No** to the narrow question.

This was useful because the prototype already attempts to draw exactly that boundary in its explanatory text. In a second pass in the **same normal chat**, the reviewer was given the prototype's short definitions of *ever* and *accept*. It then classified practical submission without assent as **No**, found no clear settled third position outside Yes/No/unsettled, kept its own No answer, and lowered its difficulty rating from **3/5 to 2/5**. The clarification therefore behaved as intended in this pretest.

The review also surfaced a second conceptual boundary: a person may think a church teaching binds when it is genuinely true or scriptural, while denying that **institutional authority itself** creates the duty during continuing disagreement. This remains compatible with No on the current narrow formulation.

The test is neither human evidence nor a clean blind AI result and does not justify adopting Yes/No as a general questionnaire rule. Repeat the two-pass test from scratch in a fresh Temporary Chat before relying on the finding. It remains a useful semantic pretest in the project's prototype → observation → correction loop.


---

## 2026-10-25 — Temporary Chat replication confirms the wording effect but exposes persona bias

The two-pass conscience-binding question test was repeated correctly in a fresh Temporary Chat at Medium reasoning with personalization disabled.

The semantic result replicated the earlier normal-chat pretest closely. Before clarification, **accept** could be read as either inward assent or practical submission, producing an apparent settled third position. After the short definitions of **ever** and **accept**, practical submission without assent fell clearly under **No**, no equally clear third doctrinal position remained, and the reviewer's difficulty rating again dropped from **3/5 to 2/5**.

This makes the local wording result more credible: in this question, the binary distinction appears to work better once *accept* is explicitly restricted to assent rather than compliance.

The clean replication also revealed a new methodological problem. Asked to act as an ordinary Christian respondent, the model immediately invented a particular theological baseline: Scripture as the foundation of faith, appreciation of church teaching and tradition, and strong personal responsibility before God. That profile is not representative of all Christian traditions and may bias both the selected answer and the interpretation of authority.

Future AI blind tests should therefore distinguish two tasks:

1. **semantic stress testing** — what does the wording permit, exclude, or leave ambiguous?
2. **substantive simulated answering** — which requires an explicitly defined persona if used at all.

Do not treat an unconstrained model's self-selected Christian persona as a neutral human-Christian baseline. The project still needs human comprehension testing.
