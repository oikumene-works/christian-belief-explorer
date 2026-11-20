# Testing — single-question historical-voices prototype

**Status:** Source checks, a headless Chromium interaction test, and the project owner's first hands-on concept test have been completed. No independent human comprehension test or historical-card blind review has yet been completed.

## Prototype

- [`prototypes/single-question-historical-voices/index.html`](../../../prototypes/single-question-historical-voices/index.html)

## Source-level checks

The locally generated HTML was checked before upload for:

- valid presence of the expected page title and core question/result containers;
- JavaScript syntax with `node --check`;
- the three answer states: `yes`, `no`, and `unsettled` in the predefined data;
- three historical voice records and answer-dependent ordering/relationship text;
- no answer storage or automatic network request code in the prototype itself;
- source links rendered only with the historical cards;
- responsive CSS rules for narrow screens.

## Headless Chromium interaction check — 2026-11-20

The exact locally generated HTML bytes were exercised in Chromium through Playwright at widths **320, 390, 768, and 1200 px**.

Direct `file://` navigation was blocked by the test environment's administrator policy. The same HTML bytes were therefore loaded with Playwright's `set_content`. This verifies the page logic and rendering under that method, not direct local-file navigation or compatibility with ChatGPT's embedded browser.

The following checks passed at every tested width:

- initial question view shown and result view hidden;
- Continue disabled before a substantive answer;
- Yes path displays the correct answer summary and orders the cards Aquinas → Calvin → Luther;
- Change answer permits a switch to No;
- No path orders the cards Luther → Calvin → Aquinas;
- Start over clears the selected answer and disables Continue again;
- unsettled path displays its distinct summary and orders the cards Calvin → Aquinas → Luther;
- exactly three source links are rendered with the cards;
- no horizontal overflow;
- no page-script errors;
- no automatic external network requests before a source link is clicked.

This does not establish that the wording is understood as intended or that the historical comparisons are editorially sound.

## Plain-language question under test

> Suppose you have studied a Bible passage carefully and still think your church explains it wrongly. Could there ever be a case where God expects you to accept your church’s explanation as right because the church has the responsibility to teach its members?

The question deliberately avoids terms such as *teaching authority*, *binding conscience*, and *assent*. A short visible clarification distinguishes accepting an explanation as right from merely following a rule, remaining silent, or listening seriously to the church's reasons.

## Historical voices shown

All answer paths show the same three bounded source cards:

- Thomas Aquinas — strong affirmative parallel;
- John Calvin — qualified or defeasible prior weight;
- Martin Luther at Worms — strong negative parallel in one concrete conflict.

The selected answer changes only their order and short relationship labels. It does not hide opposing voices or calculate a score.

## First hands-on test by the project owner — 2026-11-20

The owner used the prototype through their own genuine answer path and reported that the single-question historical-voices format was **much better** for the purpose originally intended for the project.

The owner identified three closely related kinds of value:

1. clarifying one's own thinking;
2. comparing it with how other Christians have thought;
3. potentially stimulating more deliberate, rational reflection on matters of faith.

This is the first direct product-fit observation that the historical-voices concept serves the owner's original aim better than the cumulative tradition-comparison direction.

### Interpretation limits

- This is one person's first-hand response to one question unit.
- It does not establish that every question will support equally useful historical sourcing.
- It does not establish comprehension or value for other respondents.
- It does not yet show whether the effect comes mainly from the historical material, the independent-question structure, the absence of scoring, or their combination.

The observation is nevertheless stronger than a preference for visual presentation: it concerns alignment between the prototype and the intended purpose of the project.

## Next concept check

Do not keep polishing only this first question. Build a **second independent question unit from a substantially different topic** and with a different historical-source shape.

The second unit should test whether the value generalizes when:

- the response structure is not necessarily Yes/No;
- the historical voices do not form such a neat affirmative / qualified / negative trio;
- no famous historical name is an exact match for the player's answer;
- the source material comes from a different theological topic or period distribution.

If the owner again experiences the unit as useful for clarifying and stimulating thought, the case for making independent historical-question units the project's primary product direction becomes much stronger.

## Later checks

Before treating this as a viable product direction:

- open the committed file directly in an ordinary external browser and check the three paths;
- conduct a blind semantic review of the question and historical-card claims;
- verify the cards directly against the cited primary passages;
- test the page with a small number of real respondents without asking them to simulate other theological positions;
- compare perceived value with the earlier tradition-profile direction.
