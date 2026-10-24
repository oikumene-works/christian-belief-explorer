# Bible and Interpretive Authority

**Status:** First pilot area — early design and prototyping

This area explores how a player understands the authority of Scripture, tradition, church teaching, interpretive decisions, and personal judgment.

It is the first area used to develop the general mechanics of Christian Belief Explorer.

## Current purpose

The pilot should help a player clarify questions such as:

- What gives Christian teaching authority?
- What role does Scripture play as a norm?
- What weight should historical or apostolic tradition have?
- What role may church teaching or church authority have?
- Who, if anyone, may make a binding interpretive decision?
- What does "binding" mean: common practice, doctrinal assent, conscience, or something else?
- What happens when the player's own interpretation appears to conflict with an established teaching?
- Can some disagreements remain unresolved?

The goal is not to force these questions into one binary axis.

## Current design direction

The most promising approach so far is:

1. begin with a practical, understandable situation;
2. use ordinary language;
3. ask a short question about one dimension;
4. select a predefined follow-up when clarification is needed;
5. keep distinct dimensions separate rather than embedding them in one long answer option;
6. show the player what has been inferred before using that inference in tradition comparison;
7. compare the resulting view with named, source-based profiles.

This is still a working direction rather than a final architecture.

## Important findings already established by prototyping

### The referent of "church" cannot be assumed

"Church" may mean:

- the universal church;
- a denomination;
- a local congregation;
- an institution or teaching office;
- a Christian tradition.

The player's relationship to that referent also matters.

A contextual question may therefore be needed before a theological answer can be interpreted.

### Public compliance is not the same as conscience-level obligation

A prototype involving standing during common prayer was found to be a poor test of internal authority.

A player may follow a visible communal practice for order, courtesy, or social reasons while denying that the practice is religiously binding.

Future scenarios testing conscience or authority should prefer private behavior that other people do not observe or enforce.

### Different logical questions must be separated

One draft question mixed:

- the highest norm;
- the authority of an interpreter;
- the method of investigating conflict;
- the person who ultimately forms a conviction.

Blind testing showed that these can coexist in combinations and should not automatically be treated as competing answers.

### Personal judgment is ambiguous

A statement such as "I must ultimately decide for myself what interpretation I accept" may mean either:

- the unavoidable personal responsibility to form one's own conviction; or
- a stronger claim that no external authority can bind the individual against that conviction.

These must not be treated as the same position.

## Planned pilot documentation

The following files will be added and maintained as the pilot develops:

- `TERMS.md` — concepts whose meaning needs explicit control or explanation;
- `QUESTIONS.md` — question paths, answer options, and their status;
- `PROFILES.md` — named, source-based comparison profiles and their scope;
- `SCORING.md` — inference, compatibility, weighting, and result logic;
- `TESTING.md` — prototypes, blind tests, test cases, and findings.

## Current open questions

Among the major unresolved issues are:

- the exact opening question or scenario;
- how much contextual information should be collected before theological questions;
- when a concept should be explained versus demonstrated through an example;
- the final structure of branching;
- the exact set of comparison profiles;
- the scoring/comparison model;
- whether and when profile names should be visible;
- how to represent documented internal variation within traditions;
- how to present aggregate compatibility without hiding important differences.

## Project-wide references

- [Project README](../../../README.md)
- [Decisions](../../DECISIONS.md)
- [Development Journal](../../DEVELOPMENT_JOURNAL.md)
