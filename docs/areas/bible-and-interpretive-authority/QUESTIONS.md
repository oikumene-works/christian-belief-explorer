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
