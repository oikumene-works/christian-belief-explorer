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
