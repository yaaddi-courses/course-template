# Voice and personality

Makes concrete what `AUTHORING.md` already gestures at ("write like a person
who wants you to learn this, not a spec sheet"). Pulled from this repo's own
best existing cards where possible — every "on-brand" example below is
real, shipped content; every "off-brand" counter-example is a constructed
contrast showing the failure mode, not a real card that needs fixing.

## The tone in one line

**Precise and complete like a good textbook, phrased so anyone can actually
follow it.** Correctness and thoroughness first — but never so dense,
jargon-heavy, or passive that a genuine beginner loses the thread. Never
cutesy either way.

## The two failure modes this guards against

**Too casual** — accurate but breezy, skipping precision for a chatty tone.
Reads like a friend's paraphrase, not something you could rely on as a
reference.
**Too dense** — accurate and thorough, but so jargon-stacked or passively
phrased that a beginner can't parse it even once. This is the one a real
textbook falls into, and the one to avoid.

The target sits between them: complete and precise (the textbook virtue
worth keeping) without the impenetrable phrasing (the textbook failure mode
worth dropping).

## On-brand vs. off-brand

**Explaining a mechanism**
- ✅ *"A movable label that points at one specific commit — not a copy of
  your files."* (git glossary — `Branch`) — precise about what it IS
  (a label, not a copy) and what it points at, in one plain sentence.
- ❌ *"Branches are basically like magic timelines for your code! 🌳✨"*
  (too casual — the metaphor doesn't actually say what a branch IS, and
  nothing here is precise enough to rely on)
- ❌ *"A branch constitutes a mutable reference object associated with a
  specific commit node within the directed acyclic graph comprising the
  repository's commit history."* (too dense — technically more precise, but
  buries the actual mechanism under vocabulary a beginner has no way to
  parse on a first pass)

**Explaining a gotcha**
- ✅ *"assert is a plain Python keyword, not something special to pytest,
  that a test uses to..."* (testing-with-pytest glossary — `Assert`) —
  corrects a real, common misconception up front, precisely, in plain words.
- ❌ *"pytest's assert thing is basically just a check, don't overthink
  it."* (too casual — "basically just a check" is imprecise enough to
  actively mislead: it drops the actual correction being made)

**A card's explanation field**
- ✅ *"You never write the type when creating a variable — Python figures
  it out from the value, and it can even change later."* (python-basics) —
  states the mechanism precisely (what changes, when) without jargon.
- ❌ *"Python's dynamic typing paradigm entails that variable type binding
  occurs at runtime via the object's own type metadata, as opposed to
  static declaration."* (too dense — same fact, but "paradigm," "type
  binding," and "metadata" are unexplained jargon stacked on a beginner
  who hasn't been taught any of them yet)

## What this rules out specifically

- No mascot voice, no forced enthusiasm ("Great job, superstar!"), no emoji
  substituting for an actual explanation.
- No unexplained jargon introduced without being taught first — precision
  means naming the mechanism correctly, not name-dropping vocabulary a
  beginner hasn't earned yet (see `tools/check_key_term_usage.py` in the
  `yaaddi-courses` catalog repo, which checks this mechanically for
  glossary terms).
- No hedging or vagueness in the name of sounding approachable ("basically,"
  "kind of," "sort of") where a precise word is available and just as easy
  to read.
- No throat-clearing ("it is important to note that," "it should be
  mentioned that") — say the thing directly, the way a well-edited textbook
  would, not a first draft of one.
