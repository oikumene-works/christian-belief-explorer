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
