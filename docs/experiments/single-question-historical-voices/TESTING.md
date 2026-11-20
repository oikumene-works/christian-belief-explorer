# Testing — single-question historical-voices prototype

**Status:** Source checks and a headless Chromium interaction test completed. No human comprehension test or historical-card blind review has yet been completed.

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

## First hands-on test

The project owner should use only their own genuine answer path and then assess:

1. Is the main question understandable without theological vocabulary?
2. Does the answer summary describe the chosen position without overclaiming?
3. Do the historical cards add understanding beyond the answer itself?
4. Are the limits of each comparison sufficiently prominent?
5. Do famous names overshadow the actual view and reasoning?
6. Does the unit feel complete enough to make another independent question appealing?

## Later checks

Before treating this as a viable product direction:

- open the committed file directly in an ordinary external browser and check the three paths;
- conduct a blind semantic review of the question and historical-card claims;
- verify the cards directly against the cited primary passages;
- test the page with a small number of real respondents without asking them to simulate other theological positions;
- compare perceived value with the earlier tradition-profile direction.
