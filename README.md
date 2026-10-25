# Christian Belief Explorer

Christian Belief Explorer is an experimental, question-based tool for helping Christians examine their own beliefs and compare them with named, source-based Christian tradition profiles.

The project is being developed by Oikumene Works.

## Purpose

The primary purpose is not to assign every player to one perfectly matching theological category.

Instead, the tool should help a player:

- make their own thinking more explicit;
- notice distinctions, tensions, uncertainties, and combinations within that thinking;
- compare those views with established Christian models and traditions;
- see meaningful similarities and differences without hiding them behind a single label.

A useful result may therefore be a clearer understanding of the player's own position even when no tradition profile is an exact match.

## Structure of the game

The game is divided into independent areas.

Each area has its own:

- questions and branching logic;
- comparison profiles;
- scoring or comparison rules;
- result presentation.

Results from separate areas are **not** combined into:

- an overall score;
- a global tradition ranking;
- a combined verbal personality or theological profile.

An area can be completed independently.

## First pilot area

The first pilot area is:

**Bible and Interpretive Authority**

Its purpose is to explore questions such as:

- what gives Christian teaching authority;
- how Scripture, tradition, church authority, and personal interpretation relate;
- who, if anyone, may resolve interpretive disagreement;
- what kind of decision is binding, for whom, and in what sense.

The pilot is still in an early design and prototyping phase.

See:

- [Pilot area overview](docs/areas/bible-and-interpretive-authority/README.md)
- [Original private-practice prototype (download and open locally)](prototypes/private-practice/index.html)
- [Focused spiritual-guidance experiment (download and open locally)](prototypes/private-practice/spiritual-guidance.html)
- [Project decisions](docs/DECISIONS.md)
- [Development journal](docs/DEVELOPMENT_JOURNAL.md)

## Design principles currently established

### Predefined game logic

The player-facing game is intended to work with predefined questions, answer options, profiles, and comparison rules in the browser.

AI is not required during gameplay.

Branching questions may be used, but the questions and branching rules are authored in advance rather than generated dynamically.

### Exploration before classification

The game should first help the player understand their own thinking.

Tradition profiles are comparison models, not boxes into which every player must fit.

### Preserve meaningful distinctions

The design must distinguish, where relevant, between things such as:

- a player's own stated position;
- uncertainty about that position;
- openness toward other positions;
- missing information in a comparison profile;
- documented diversity within a tradition.

A single compatibility number must not erase important differences.

### Prototype before scaling

The project deliberately uses small working prototypes before larger design commitments.

A prototype is used to expose hidden assumptions, ambiguous language, missing answer paths, and problems in the comparison model before the system is expanded.

### Accessible language

The intended audience is ordinary users, not professional theologians.

Technical concepts should therefore be avoided where possible, explained when necessary, and tested through concrete situations when that improves understanding.

## Documentation

The repository documentation is written in English.

Development discussion may take place in Finnish, but repository content, including draft player-facing wording and prototypes, is written in English.

The documentation is intended to preserve both:

1. the current state of the design; and
2. the reasoning and experiments that led to it.

## License

Unless otherwise noted, original material in this repository is dedicated to the public domain under [CC0 1.0 Universal](LICENSE).

Third-party material remains subject to its original rights and licenses.
