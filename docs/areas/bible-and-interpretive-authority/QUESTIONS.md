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
