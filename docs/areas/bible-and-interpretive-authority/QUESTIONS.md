# Draft question path: a private food practice

**Status:** Experimental working prototype (2026-10-25). Not an accepted question set or tradition comparison.

**Runnable file:** [`prototypes/private-practice/index.html`](../../../prototypes/private-practice/index.html). Download the file and open it in a browser; no server or build step is required.

## Scenario

The player imagines belonging to a Christian community that matters to them. The community says members must refrain from an ordinary food on one day of the week, even in private. Nobody observes or checks. Scripture is stipulated not to command or prohibit that particular food and day *directly*. The community's right to make the rule is deliberately **not** stipulated.

The fictional food is unnamed to avoid importing a particular denomination's fasting rule or a specific food taboo. The scenario may still be perceived as an indirect reference to real fasting disciplines; this needs human testing.

## Predefined question path

**Q1 — Freedom** (`freedom`)

> Apart from the community's rule, do you believe you would be free before God to eat the food on that day?

Yes → `authority`. No / Not sure → result with **no authority inference**.

**Q2 — Legitimate requirement** (`authority`)

> Even if eating it is otherwise permitted, could this community legitimately require its members to refrain in private?

Yes / No / It depends / Not sure → `conscience`.

**Q3 — Conscience** (`conscience`)

> If you knowingly ate it in private anyway, would breaking this rule itself be wrong before God?

Yes / No / It depends / Not sure → `scripture`.

**Q4 — Biblical grounds** (`scripture`)

> Could relevant biblical teaching about freedom or obedience help you settle or revise that answer?

Yes, possibly / No / Not sure → `community`.

**Q5 — Community authority as a ground** (`community`)

> Could better reasons for or against this community's authority to set such a rule help you settle or revise that answer?

Yes, possibly / No / Not sure → `apostolic`.

**Q6 — Apostolic origin as a ground** (`apostolic`)

> Could evidence that this practice came from the apostles help you settle or revise that answer?

Yes, possibly / No / Not sure → result.

All transitions and summaries are fixed in the browser file. No free-text interpretation, AI, external requests, profiles, or scores are used.

## What may be inferred

- `freedom=yes`: the player regards eating the food as permitted **apart from** the community's rule. This does not decide whether they should nevertheless refrain.
- `authority`: the player's stated judgment about the legitimacy of a **private community requirement**; it is **not** a direct measurement of what they would actually do.
- `conscience`: the player's stated judgment about whether **knowingly breaking the community rule itself** would be wrong before God; this does not establish *why*.
- If `authority=yes` and `conscience=no`, the two dimensions are distinct, not contradictory.
- If `authority=no` and `conscience=yes`, flag for further inquiry rather than diagnosing a contradiction; personal promises, motives, or other duties have not been explored.
- `depends` and `unsure` stay unresolved; they are not converted to a middle position or a score.
- The last three questions record **possible grounds for settling or revising** the conscience judgment. A "Yes, possibly" does **not** establish a sufficient condition, an ordering of sources, or a change of view.
- `freedom=no` or `freedom=unsure`: the prototype stops because it cannot isolate community authority from the player's other reasons for restriction.

## Not measured yet

The identity and ecclesial standing of the community; an explicit personal vow; whether the player would comply in fact; what exactly makes an obligation legitimate; the role of indirect biblical arguments; confidence; openness to alternatives; named tradition profiles; compatibility or weighting. The branch cannot be generalized to every Christian community or tradition.

**Next design check:** Have a person explain each question and the resulting summary in their own words before revising wording or broadening the scenario.

---

## Focused spiritual-guidance experiment (2026-10-25)

**Status:** A separate experimental branch of the same private-practice scenario. It does not replace the first prototype, change the profile model, or alter scoring.

**Runnable file:** [`prototypes/private-practice/spiritual-guidance.html`](../../../prototypes/private-practice/spiritual-guidance.html).

The first three question texts (freedom, community authority, conscience) are unchanged. Their routing differs:

- `freedom=yes` → authority → conscience → `spirit_seek`.
- `freedom=no` or `freedom=unsure` → `spirit_seek`, without inferences about authority or conscience.
- A judgment about freedom is therefore **not** a prerequisite for discussing spiritual guidance.

**SG1 — Seeking guidance** (`spirit_seek`)

> Would you seek the Holy Spirit's guidance in deciding how to respond to this rule?

Yes / No / Not sure → `spirit_weight`.

**SG2 — Possible weight of perceived guidance** (`spirit_weight`)

> Suppose you came to believe the Holy Spirit was guiding you toward a particular choice here. Would that affect your judgment about what to do?

Yes / No / It depends / Not sure. No → result; others → `spirit_check`. The scenario is hypothetical, not a claim of having actually received guidance.

**SG3 — Examining one's understanding** (`spirit_check`)

> If you were to rely on that sense of guidance, would you first examine whether you had understood it correctly?

Yes / No / It depends / Not sure → result.

### Interpretation boundaries

- Seeking guidance does not imply a claim to have received identifiable guidance or to have a direct inner prompting.
- Not seeking guidance in this specific scenario does not imply denying the Holy Spirit's existence, activity, or guidance through Scripture and other people.
- A hypothetical judgment that perceived guidance would matter does not imply that any impression is divine, reliable, or decisive.
- An answer about whether a person would examine their understanding does not specify the **method** or grounds for that examination. This remains open.
- `spirit_seek=no` with `spirit_weight=yes` can be coherent: a player might consider guidance that was not sought. `spirit_seek=yes` with `spirit_weight=no` can also be coherent: seeking guidance does not entail granting a particular impression independent force.
- "It depends" and "Not sure" are kept distinct and produce qualified summaries.
- Biblical teaching, prayer, community counsel, and tradition may contribute together. The new questions are **not** presented as a fourth source competing with Scripture, community or apostolic testimony.
- The original prototype's three *grounds for reconsidering* questions are not repeated in this focused test. Its result is therefore deliberately narrower, not a replacement for a complete authority account.

### Further wording tests

Do players understand "came to believe" as a hypothetical belief rather than an actual experience? Do they distinguish a prompting from guidance perceived through Scripture, prayer or trusted Christians? Does "examine whether you had understood it correctly" assume a private sensation or leave enough room for other forms of discernment? These uncertainties require comprehension tests before integration.

---

## Relevance-first parallel entry (B) — 2026-10-25

**Status:** Small routing experiment, not a replacement for either private-practice baseline. [Run the standalone B file](../../../prototypes/relevance-routing/index.html).

**Gate:** “When thinking through a Christian decision, which of these might matter to you? Select any number. This is about relevance, not ranking or agreement.” Selectable considerations: what the Bible says; guidance of the Holy Spirit; conscience; teaching or rules of a Christian community; independent examination of circumstances. An exclusive “I am not sure what would be relevant” option is provided; submitting with none selected is permitted and reported without inferring rejection. The optional “What does this mean? — Example” is *explanatory only* and not the measured scenario.

**Routing:** Every selected consideration leads to one distinct, predetermined follow-up asking a narrower question (possible effect of investigating biblical teaching; seeking guidance; importance of acting against settled conscience; possible effect of community teaching; importance of examining circumstances). Each has Yes / No / It depends / I am not sure. Unselected topics receive no follow-up. No selection or unknown yields a summary immediately. No profile, score, authority ranking or inference from skipped questions.

**Limit:** B's general decision context is *not* the baseline's stipulated private food rule. The B follow-ups probe different things (notably seeking guidance versus possible influence). Thus question counts are comparable as **interface load** only, not as equivalent theological coverage. The gateway can miss unrecognized considerations, and selection may reflect familiarity or salience rather than doctrinal commitment. A “No” follow-up does not mean the same thing as a topic being irrelevant. The conscience prompt may still depend on what “settled conscience” means to a respondent. “Christian community” remains referentially ambiguous. No actual human comprehension finding is claimed.

---


## B2 — Yes/No and a separate unsettled-view action (2026-10-25)

**Status: experimental; not accepted questionnaire architecture.** [Try B2](../../../prototypes/relevance-routing/yes-no-unsettled.html); [B baseline](../../../prototypes/relevance-routing/index.html) remains unchanged.

B2 retains B's five-item, unscored, multi-select relevance gate and optional explanatory example. Each selected topic leads to one short follow-up with **Yes / No** as the only substantive answer options and a visually separate **“I don't have a settled view on this”** button. This records `unsettled` distinctly from `no`; no choice is forced. The gate's own relevance uncertainty option is unchanged.

To prevent a false inference from a narrow Yes/No answer, B2 tests only actions/considerations in the player's decision process:
- Bible: would examine a relevant Bible passage if available (not its decisive authority);
- Spirit: would deliberately seek guidance (not claim to receive it);
- conscience: would be concerned if an action conflicted with settled conscience (not judge the act objectively wrong);
- community: would consider advice from a community important to them (not grant binding jurisdiction);
- circumstances: would independently examine relevant circumstances (not reject outside help).

These are deliberate **changes in measured wording**, not merely new button labels. Conditional answers and unsettled positions must not be silently converted to No. A No means only a negative answer to the particular narrow prompt; no skipped topic is classified as rejected. “Would you” may still hide differences between habitual and hypothetical behavior, and some respondents may have a conditional settled view rather than *no* settled view. These remain targeted test failures to look for before committing to binary responses.

---

## B2 doctrinal-authority stress test — 2026-10-25

**Status:** One-question exploratory probe, not an adopted question or profile. [Standalone HTML](../../../prototypes/relevance-routing/conscience-binding-authority.html). Original [B](../../../prototypes/relevance-routing/index.html), [B2](../../../prototypes/relevance-routing/yes-no-unsettled.html), and both private-practice variants are preserved.

**Intended discriminating distinction:** Can an ecclesial body possess teaching authority which, **in at least one legitimate case**, creates a duty before God to accept its interpretation of Scripture **despite a member's continued sincere disagreement after considering the text**? This is different from regarding church teaching as persuasive evidence, considering advice, complying publicly for order, or accepting an interpretation once personally convinced by biblical arguments.

**Exact measured question:**

> Can a Christian church’s teaching authority ever make it a duty before God for one of its members to accept the church’s interpretation of Scripture, even if that member has carefully considered the biblical text and still disagrees?

**Controls:** substantive **Yes / No**; separate smaller **“I don't have a settled view on this”** action (recorded as `unsettled`, never No). One optional “What does this mean? — Example” is explicitly explanatory, not a particular church or doctrine that the player is asked to judge. The always-visible note defines *ever* as *at least one possible case* and *accept* as something one ought to affirm, not mere outward compliance. This is a self-contained question **without the B2 relevance gate**: the experiment changes the measured content, not the B/B2 baseline files.

### Interpretive limits

- **Yes:** the player considers **some case** of conscience-binding ecclesial interpretation possible despite the member's still-divergent reading. Yes does **not** claim that all churches, pronouncements, or subjects have this force, or identify the conditions.
- **No:** the player denies **this specific conscience-binding duty grounded in church teaching authority despite continued dissent**. No does **not** deny church guidance, historical testimony, the authority of Scripture, public membership rules, or becoming convinced by the church's biblical reasoning.
- **Unsettled:** no settled position on this specific possibility; not a No, not a “conditional yes”.
- **None:** the answer alone determines which church, teaching office, doctrinal act, or condition qualifies; truth of any teaching; actual conformity; relative ultimate norm; whether a person can sincerely will intellectual assent; or a tradition identity.

### Settled-conditional counterexample and proposed repair

A plausible coherent position is: **some properly authorized, formal doctrinal decisions are conscience-binding, but an ordinary local pastor's interpretation or congregational advice is not**. An unqualified “Must you follow the church rather than your own interpretation?” forces this view into a misleading Yes or No. In the new question, **ever** allows a truthful Yes without asserting universal binding force. This solves only the **existence** distinction; it does not measure *which* conditions qualify. Another coherent position gives church teaching serious, perhaps mandatory, **consideration** without requiring **assent** against an unconvinced reading; this corresponds to No on the narrowly defined duty, not to wholesale rejection of church authority.

A split into separate questions about a church's formal competence and the binding effect of a particular decision remains possible **if** blind testing finds the existential question too abstract or insufficiently discriminating. Do not split or add “It depends” automatically. Residual ambiguity about *church*, *authority*, *accept*, and whether a moral duty to assent is intelligible must be tested without priming the respondent.
