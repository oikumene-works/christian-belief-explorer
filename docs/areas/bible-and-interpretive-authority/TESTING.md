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

---

## Owner's first hands-on B2 impression — 2026-10-25

The owner tried the separate `yes-no-unsettled.html` prototype and reported: **“This feels like a better way to ask”** than the previous B response presentation. The owner did **not** visit every answer path. This is **one preliminary, subjective usability observation** about the response interface, not a complete-path test, a comparative usability study, or theological validation. No specific answer wording was reported as failing or as successfully resolving a conditional view. Retain B as the comparison baseline; keep the unsettled-vs-conditional distinction open. Discussion moves to HUB, which should read the updated `docs/CURRENT_STATE.md` before deciding any next step. No accepted project decision follows.

---

## One-question B2 doctrinal-authority stress test — 2026-10-25

**File:** [conscience-binding-authority.html](../../../prototypes/relevance-routing/conscience-binding-authority.html). The prior B/B2 and private-practice files were **not modified**.

### Implementation verification

Tested the exact HTML bytes in headless Chromium (Playwright, via `set_content`). After uploading to `main`, verified that the remote Git blob SHA `18893b1a934e4c9f8341f1ffa27b8feab579dfbb` equals the hash of the tested local file.

**Passed:** exactly Yes and No radio options; separate `unsettled` action; no forced answer; correct and distinct summaries for Yes, No, and unsettled; expandable explanatory example; change-answer preserving the earlier selection; changing Yes to No; reset clearing the answer; widths 320, 390, 768 px without horizontal overflow; no page script errors or network requests observed. This is a scripted browser behavior test, **not** a human comprehension test or a test of the app's embedded browser.

### Deliberate conceptual counterexamples (desk stress tests, not participant responses)

- **Conditional church authority:** a church may bind conscience only through specific authorized doctrinal decisions, not routine local advice. The overly broad question “Must one follow church teaching over one's reading?” fails. Restricting the actual question to whether such authority can **ever** exist permits Yes while leaving its conditions unmeasured.
- **Persuasive but not binding:** a player takes church teaching very seriously, but would not accept an interpretation as religiously obligatory while still unconvinced by it. The narrow answer can be No; No must not be expanded into “rejects church authority”.
- **External compliance without assent:** a player follows community discipline for membership or unity without accepting the interpretation as true. The question addresses religiously obligatory **assent**, not external behavior; No can coexist with compliance.
- **Conditionality based on later persuasion:** a player accepts the teaching once persuaded by textual arguments, but not *because of institutional authority during continuing disagreement*. The narrow answer is No.
- **Unsettled authority view:** separate `unsettled` route expresses lack of a settled position. It must not be used to capture a definite view with special conditions.

### Evaluation of the seven requested concerns

1. **Exact distinction:** the *possible existence* of church-teaching-based conscience duty to affirm an interpretation despite personal disagreement.
2. **Yes:** acknowledges at least one such possible instance; no claim of universal church authority.
3. **No:** denies that narrow duty under continuing disagreement; does not deny other forms of ecclesial authority or scriptural persuasion.
4. **Neither:** entails a named church, teaching, special conditions, doctrinal truth, actual conformity, or denominational identity.
5. **Settled conditional:** found in the desk test (limited formal decisions vs ordinary advice); it defeats the unbounded question but fits the *ever* formulation as Yes. The qualifying conditions remain invisible.
6. **Repair:** narrowed the measured duty (assent vs public compliance/advice) and quantifier (*ever*) rather than splitting into two questions. Test whether this narrowing is understood.
7. **Discrimination:** meaningful but coarse; it separates the categorical denial of such moral binding force from its possible existence. It does not separate narrow conditional affirmation from very broad affirmation. Whether it is *usefully* discriminating for ordinary respondents remains unverified.

**Still untested:** real-user ease; the meaning of “a Christian church”, “duty before God”, and “accept”; the effect of the optional explanatory example; whether “ever” is experienced as overly abstract; real embedded-browser compatibility. No independent theological validation was performed.

**Next step if the owner finds this intelligible:** perform a **blind wording/inference test in a separate Temporary Chat**, giving only the exact question and choices first, before exposing this intended interpretation. Ask the tester to paraphrase the question, locate hidden assumptions and settled conditional counterexamples, identify Yes/No inference limits, and suggest at most one targeted correction. Do not treat a positive blind review as participant validation or expand the whole questionnaire yet.


---

## Context-restricted normal-chat pretest of conscience-binding question — 2026-10-25

**Test type:** prompt-restricted AI pretest in a **normal ChatGPT conversation**, reasoning level **Medium**. The prompt instructed the reviewer to act as a first-time Christian respondent and not use outside sources or infer the author's purpose. However, because this was not a Temporary Chat, prior account/conversation context cannot be excluded. Treat the result as a useful pretest, **not as a clean blind test** and not as human usability evidence.

### Main observations

- The reviewer paraphrased the intended core distinction substantially correctly: whether church teaching authority can create a duty before God to accept the church's interpretation despite the member's continuing, carefully considered disagreement.
- It independently noticed that **ever** means at least one possible case rather than universal obedience.
- The terms it found most interpretation-sensitive were **a Christian church**, **teaching authority**, **accept**, and **duty before God**.
- The strongest ambiguity was **accept**. The reviewer distinguished:
  - actually affirming the church's interpretation as correct; and
  - submitting to or complying with the church's decision while remaining internally unconvinced.
- It described a coherent settled position in which a believer may owe practical submission to church authority without owing internal assent. It was unsure whether this was a third answer or simply **No**, explicitly depending on the meaning of *accept*.
- It also identified a different possible condition: if a teaching binds only when it is true or scripturally correct, the binding ground may be the teaching's truth rather than the church's authority as such.
- Under the natural reading of **accept** as genuine assent, it judged **Yes / No** to be two meaningful opposing positions and chose **No** for itself.
- It judged the question **3/5** in difficulty: understandable in its main point, but requiring deliberate interpretation of *accept*.
- Its stated safe inferences from No closely matched the prototype's intended limits: No did not imply rejection of church teaching, tradition, communal rules, or the possibility of later persuasion.

### Interpretation

This pretest does **not** show that the question is human-readable or that binary response architecture is generally valid. The prompt explicitly asked the reviewer to search for hidden assumptions and settled non-binary positions, and normal-chat context cannot be ruled out.

### Same-chat clarification pass

The same reviewer was then given only the prototype's two short clarifications:

- **ever** = at least one possible case, not every church or every teaching;
- **accept** = treating the teaching as something one ought to affirm, not merely following a public rule or considering the argument.

The reviewer reported that the core meaning did not change but became clearer. The assent-versus-compliance ambiguity was resolved: practical submission without internal assent became **No**, not a third position. It could no longer identify a clearly settled third doctrinal position outside Yes/No/unsettled. Its answer remained **No**, while its difficulty rating fell from **3/5 to 2/5**. Remaining interpretive questions concerned *teaching authority*, *duty before God*, and what kind of church could possess such authority, but the reviewer said these now felt more like substantive theological issues than wording failures.

This is encouraging evidence about the clarification **within the same non-blind pretest**, not independent validation.

**Next step:** repeat both passes from scratch in one fresh **Temporary Chat** at Medium reasoning, without mentioning these normal-chat results. Preserve the first-pass response before supplying the clarification. Only after that clean replication should the result be treated as the project's actual AI blind test.

No accepted decision or scoring/profile change follows from this pretest.


---

## Clean Temporary Chat blind replication — 2026-10-25

**Test setup:** a fresh Temporary Chat at **Medium** reasoning with personalization disabled. The same two-pass prompt sequence was used: first the exact question with Yes / No / unsettled choices and no project explanation; then, in the same Temporary Chat, only the short definitions of **ever** and **accept** were added. No result from the earlier normal-chat pretest was disclosed.

### First pass

The reviewer again recovered the core intended distinction and independently read **ever** as an existential quantifier: one possible case is enough for Yes.

The same main ambiguity reappeared: **accept** could mean inward assent, public confession, practical compliance, or refraining from opposition. This generated the same apparently third settled position: practical submission to church order without an obligation to inwardly believe the interpretation true.

The reviewer judged Yes and No to be meaningful opposing positions **if the terms are fixed**, chose No for itself, and rated the question **3/5** in difficulty.

### Clarification pass

After receiving only the prototype's definitions:

- **ever** = at least one possible case, not every church or every teaching;
- **accept** = treating the teaching as something one ought to affirm, not merely following a public rule or considering the argument;

the reviewer moved the practical-submission-without-assent position clearly into **No**. It no longer found a clear settled third doctrinal position outside Yes / No / unsettled. It retained No and lowered difficulty to **2/5**.

Remaining uncertainty concerned **teaching authority**, **duty before God**, and which kind of church could possess such authority. The reviewer regarded these more as substantive theological questions than as blockers to answering.

### Methodological warning: self-created theological persona

The supposedly generic Christian respondent spontaneously declared a substantive starting profile before answering: Scripture as the basis of faith, respect for church teaching and tradition, and personal responsibility before God for belief. That is **not a neutral cross-Christian stance**. It likely influenced the reviewer's own No answer and possibly which ambiguities it emphasized.

Therefore:

- use the blind review primarily for **semantic interpretation, response coverage, and inference limits**;
- do not treat the model's own Yes/No choice as evidence about how a generic Christian would answer;
- future blind prompts should avoid inviting the model to invent one representative Christian theology. Prefer a role such as “first-time respondent evaluating what the wording permits” and separate semantic coverage testing from simulated substantive answering.

### Status

The Temporary Chat replication strengthens the specific wording finding: the **accept = assent, not compliance** clarification repeatedly removes the main apparent third-position problem in this test. It does **not** validate the question with humans, establish a neutral Christian respondent model, or justify a general binary-question architecture.

No accepted decision follows.

---

## Test battery — Case B: three settled positions and one conditional follow-up (2026-10-25)

**File:** [case-b-tradition-presumption.html](../../../prototypes/relevance-routing/case-b-tradition-presumption.html).
**Status:** working, scripted logic test passed; **no** human or independent blind semantic test.

### Explicit stance-case matrix — conceptual, not simulated owner answers

| Formed stance | Route | Safe reading |
| --- | --- | --- |
| Intergenerational agreement by itself settles the reading | \`decisive\` | Independent decisive weight in this narrow comparison |
| Agreement counts as evidence and can be outweighed by individual biblical study | \`rebuttable → yes\` | Revisable preference; such personal study may sometimes suffice |
| Agreement gives a real preference, but individual study alone never suffices to displace it | \`rebuttable → no\` | Revisable preference, additional condition unknown |
| Agreement adds no independent interpretive preference; examine the teachers' arguments | \`none\` | No independent weight from agreement itself |
| Explicitly undecided about the significance of such agreement | \`unsettled\` | No formed view, **not** a negative stance |
| Firmly conditional on *apostolic authenticity* or a specific formal decision, rather than duration or agreement alone | \`unrepresented\` if none fits | **Design gap**, never an uncertain or negative answer |

**Stress-test judgments:**

1. **Uncovered formed position:** yes, one is plausible when a respondent needs facts about apostolic authenticity, scale of consensus, or formally asserted authority. The diagnostic route prevents forced selection but does not characterize that position. Completeness is **not established**.
2. **Multiple fit:** the wording attempts to make decisive / defeasible / zero *independent interpretive weight* exclusive. However a player who applies different principles to different biblical topics may still identify with more than one at the general level; the context may require more specification. Do not classify such a player without further testing.
3. **Substantive third:** \`rebuttable\` supplies a positive but defeasible reason. It is neither decisiveness nor zero independent weight, so it is not an “It depends” substitute for poor grammar.
4. **Unsettled misuse:** separate \`unsettled\` and \`unrepresented\` states at both stages; neither is forced into \`none\` or \`no\`.
5. **Follow-up precision:** \`rebuttable → yes/no\` addresses whether one *particular* condition—independently supported personal biblical study—can ever suffice. It intentionally does not assert a complete list of defeating conditions.
6. **Inference:** all result texts report only the selected kind/strength of interpretive weight and the single sufficiency condition; they avoid denomination, binding church power, particular interpretation, and truth claims.
7. **Theological discrimination:** still meaningful as a normative interpretive difference, but this is a **coarse** three-level model. It cannot prove that the same three levels fit every context.

**Possible hidden dimension to watch:** “many Christian teachers across generations” can mean merely numerical agreement, continuous reception, or apostolic succession. Q1 asks only about agreement across generations; actual users may import a different status claim. It must not be silently reinterpreted as binding magisterial authority.

### Actual automated checks

Executed the **exact committed JavaScript** with a minimal simulated DOM harness in a JavaScript runtime (not a graphical browser). Script compiled. **17 checks passed** covering: all three main radio choices; refusal to submit without a choice; distinct \`decisive\` and \`none\` inferences; both first-question escape controls; binary follow-up; two distinct qualified results; both follow-up escape controls; Back from result to follow-up and from follow-up to main; no stale follow-up inference after changing the main answer; reset; no network/storage APIs in the source. Fetched \`main\` content blob SHA at testing: \`8ddcef97770e35241c3f5bca6551cbad8e2471c6\`.

**Not tested:** real Chromium display, keyboard/screen-reader semantics, embedded-browser compatibility, live user comprehension, cross-Christian completeness, and external blind semantic critique. The mock-DOM test validates only the specific scripted interactions, not rendering.

### Next small check

Let the owner try **their own actual path only** and report whether any answer misstates their formed position or whether the follow-up is burdensome. Do **not** ask the owner to simulate other Christian views. Then, if still promising, use a **separate Temporary Chat** for a context-free semantic/coverage test (no invented generic-Christian persona), and later real respondents with varying backgrounds. A failed coverage case warrants refining the question or separating dimensions **before** building a longer tree.
