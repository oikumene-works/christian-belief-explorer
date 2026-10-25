# Testing: private-practice prototype

**Status:** Browser smoke test completed; comprehension and blind testing not yet performed.

## Browser smoke test — 2026-10-25

A local, headless Chromium run with Playwright exercised the standalone HTML prototype. The scripted test runner was a development aid, not yet part of the repository.

All checks passed:

- `freedom=no`: stops without inferring authority or conscience.
- `freedom=unsure`: stops and preserves uncertainty.
- `authority=yes`, `conscience=no`: explicitly distinguishes a community's right to make rules from wrong before God.
- `authority=no`, `conscience=yes`: flags the combination for clarification, not automatic contradiction.
- Grounds answered Yes / No / Not sure: reports possible grounds and uncertainty without treating No as rejecting a source.
- Back, change an earlier answer: clears later answers so no obsolete inference survives.
- Start over, narrow screen, browser JavaScript: reset works; no horizontal overflow or uncaught script error observed.

These checks verify the **implemented paths**, not the theological validity or comprehensibility of the wording.

## Initial hands-on feedback from the project owner — 2026-10-25

- **Embedded-browser behavior:** The Continue button did not advance in the application's built-in browser. The same prototype worked throughout in an external browser. This is a reported environment-specific issue, not a diagnosed cause or a confirmed flaw in the question logic. Reproduction and console/security-policy inspection in the affected browser remain open. Using an external browser is a working alternative for now.
- **Missing consideration:** The owner noted that seeking the Holy Spirit's counsel and guidance in practical decisions is important and absent from the three proposed grounds for reconsideration (biblical teaching, community authority, apostolic origin). These three prompts must not be presented as exhaustive.
- **Distinction to investigate:** Seeking guidance through prayer, believing the Holy Spirit can guide a judgment, and believing one has received a particular prompting are not identical answers. Neither a reported prompting nor an appeal to Scripture or tradition automatically establishes how that judgment is tested or weighed. The same player may find several of these considerations relevant at once.
- **Status:** No question wording, transitions, interpretation rules, or accepted project decisions were changed as a result of this feedback. The design of any follow-up about spiritual guidance requires separate review.

## Human / blind tests needed

1. Before receiving the intended meaning, ask the tester what they understand by *free before God*, *legitimately require*, and *wrong before God*.
2. Ask whether they took *community* to mean their actual local church, denomination, a hypothetical group, or something else. The wording may still conflate these referents.
3. Test whether a private dietary rule really removes social pressure or whether loyalty, promises, or fear of being discovered still enter the answer.
4. Try answer paths with `depends` and `unsure`; ask which missing conditions matter. Avoid silently equating the two.
5. Ask whether biblical teaching, community authority, and apostolic origin are overlapping rather than competing grounds; a Yes does not show that a source is decisive.
6. Ask whether the player's own reasons unrelated to the rule make this scenario unsuitable despite `freedom=yes`.
7. Ask the tester to identify any reasonable answer not represented by the prototype.

## Constraints on interpreting test results

No real tradition profile or scripture interpretation has been validated against this prototype. The resulting text reports only the player's selected judgments. **Do not** assign a denomination or calculate a compatibility percentage from these responses.

---

## Focused spiritual-guidance experiment: browser checks — 2026-10-25

The separate `spiritual-guidance.html` file was exercised in headless Chromium with Playwright at a narrow 390px viewport. The testing environment blocked direct `file://` navigation with an administrator restriction, so the **same HTML bytes** were loaded into the test page using Playwright's `set_content` instead. This confirms browser-script and interaction behavior under that method, **not** file URL behavior or compatibility with the application's internal browser.

Checks passed:

- `freedom=no` → guidance questions, while omitting authority/conscience inferences;
- `freedom=yes`, `authority=yes`, `conscience=no` → distinct judgments retained;
- seeking guidance = No, hypothetical weight = Yes → answers coexist without an invented contradiction;
- seeking guidance = Yes, hypothetical weight = No → evaluation question skipped, without claiming the player rejects the Holy Spirit;
- `authority=no`, `conscience=yes` → unresolved combination flagged, not categorized as impossible;
- uncertain answers for freedom, seeking, weight and examination remain uncertain;
- Back, change an earlier answer, forward navigation and reset → later answers are cleared appropriately;
- no JavaScript page errors, external network requests or horizontal overflow in the tested session.

**Still open:** actual compatibility with the application's built-in browser, blind human testing, and whether the conditional examination question is semantically clear. No theological truth claims or source-level profile comparisons were validated.

---

## Parallel A/B entry experiment — 2026-10-25

**Prototype B:** [relevance-routing/index.html](../../../prototypes/relevance-routing/index.html). Existing A baseline files were not edited.

### Desk walkthrough matrix (predicted code paths, not user trials)

| Input / interpretation | A: original private-practice | B: relevance-first |
| --- | --- | --- |
| Act not otherwise permitted (freedom=No) | 1 question then stop; no authority inference | 1 gate + 0–5 follow-ups, depending on selection; B does **not** test intrinsic freedom |
| Only Bible marked relevant | A reaches six questions only if freedom=Yes | B: 1 gate + 1 follow-up = 2 |
| Bible + Holy Spirit + conscience marked relevant | A original: six questions if freedom=Yes, but does not test seeking guidance | B: 1 + 3 = 4 |
| All five marked relevant | A original: six questions if freedom=Yes | B: 1 + 5 = 6; no reduction |
| Not sure about relevance / no topic selected | A has no directly equivalent gate | B: 1 gate and qualified summary; no rejected-topic inference |
| Community relevant, then No on its follow-up | A asks about a *particular private requirement* | B records only No on possible influence of community teaching; does not imply community authority is illegitimate |

**Important:** These are code-path / interpretive walkthroughs, **not empirical confirmation** that B saves time, is clearer, or covers the same theology. The A spiritual-guidance variant has a different route (up to six questions). No direct comparison of comprehension is yet available.

### Hypotheses and preliminary findings

1. **Redundant prompts:** B skips unselected follow-ups by construction, but it may create a *new* gate burden. B can be shorter (2 versus 6 on a selective path) or equally long (6 versus 6); A is shorter in its freedom=No early-exit path. These counts are not matched-content outcomes.
2. **Comprehension:** untested with people. B avoids an immediate hypothetical food case but “relevant” may be more abstract and less informative than the concrete A scenario.
3. **Hidden assumptions:** the five topics risk looking exhaustive; unknown and empty selection mean different things; the selection may measure salience/familiarity rather than meaningful relevance; “community” and “conscience” are underspecified.
4. **Coexistence:** multiple considerations can be selected simultaneously, including Bible and Spirit, without a hierarchy. This proves UI expressibility, not theological interpretation quality.
5. **Inference:** only topic selection and answers to the precisely worded follow-ups are reportable. No rejection from omission, superiority of one source, received guidance, actual conduct, binding community authority, or wrong-before-God judgment follows.

### Next empirical check

Ask 3–5 people to try A and B in counterbalanced order. For each, collect questions reached, perceived difficulty, their explanation of “relevant,” and whether the generated summary reflects their meaning. Specifically challenge a Bible+Spirit+community combination and an unselected-yet-important consideration. Test B with an external browser and separately the in-app embedded browser; the old Continue defect is unresolved. Revise wording/routing **after** observation, without expanding this into the entire area.

---


## B2 — binary follow-ups with separate unsettled action (2026-10-25)

**Baseline preserved:** `prototypes/relevance-routing/index.html`. **New file:** `prototypes/relevance-routing/yes-no-unsettled.html`. The two private-practice baselines also remain unchanged.

**Evidence:** The project owner's hands-on B feedback is that having “It depends” and “I am not sure” alongside ordinary substantive choices felt undesirable. This is direct feedback about B, **not** human evidence that B2 is easier.

**Static implementation checks passed at creation:** two substantive options are present, “It depends” removed from the B2 follow-up control, separate `unsettled` action exists, form submission requires an explicitly selected Yes/No, and the multi-select gate remains. No request or storage calls appear in the HTML source. **No automated real-browser or human B2 interaction test has yet been performed.** These checks do not establish browser compatibility or experiential ease.

### Predicted paths and interpretation stress tests (not observed users)

1. Bible only → gate + 1 Yes/No or unsettled follow-up → summary. A No denies the specific intention to examine an available passage, **not** Scripture's authority.
2. Bible + Spirit + community → three independent follow-ups. All may be Yes without being ranked or placed in opposition. A Spirit No does not deny the Spirit's guidance in general.
3. Community Yes + conscience No → these narrowly worded answers can coexist; cannot establish legitimate community requirements or conscience-binding force.
4. Conscience unsettled → explicit unsettled summary, never mapped to No.
5. All five selected → six steps, just as in B; fewer visible radio alternatives is **not** fewer questions.
6. No items/unknown gate → qualified summary, no assumption that omitted considerations are rejected.
7. A respondent whose honest answer is “sometimes, under particular conditions” may find **both** Yes/No and “no settled view” inaccurate. This is a *conditional settled position*, not uncertainty. B2 currently has no dedicated representation; do not reinterpret such an answer.

**Assessment:** A lighter-looking interface is mechanically plausible but remains **untested** for comprehension and effort. The narrower formulations reduce overclaiming but also measure something different from some B questions. In particular, asking whether someone would *consider* community advice cannot answer whether they would *obey* a binding teaching. For conditional answers, first test whether an explicit circumstance can narrow the question; if not, split a specific dimension rather than forcing binary choice.

**Next step:** have the owner try B and B2 on the same selections, paying particular attention to an honestly conditional answer and the perceived meaning of the separate unsettled button. Record exact question and missing condition. Test Back/edit/reset and mobile/embedded-browser behavior before claiming operational parity.
