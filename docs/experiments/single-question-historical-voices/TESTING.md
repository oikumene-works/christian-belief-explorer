# Testing — single-question historical-voices prototype

**Status:** Static implementation checks completed. No real-browser interaction test, human comprehension test, or historical-card blind review has yet been completed.

## Prototype

- [`prototypes/single-question-historical-voices/index.html`](../../../prototypes/single-question-historical-voices/index.html)

## What was checked at creation

The locally generated HTML was checked before upload for:

- valid presence of the expected page title and core question/result containers;
- JavaScript syntax with `node --check`;
- the three answer states: `yes`, `no`, and `unsettled` in the predefined data;
- three historical voice records and answer-dependent ordering/relationship text;
- no answer storage or network request code in the prototype itself;
- source links opening only after the historical cards are rendered;
- responsive CSS rules for narrow screens.

These are static and source-level checks. They do not establish that every interaction works in an actual browser or that the wording is understood as intended.

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

- exercise Yes, No, unsettled, change-answer, and reset paths in a real browser and at narrow widths;
- conduct a blind semantic review of the question and historical-card claims;
- verify the cards directly against the cited primary passages;
- test the page with a small number of real respondents without asking them to simulate other theological positions;
- compare perceived value with the earlier tradition-profile direction.
