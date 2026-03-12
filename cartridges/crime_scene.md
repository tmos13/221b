# CARTRIDGE 2: CRIME SCENE

> The physical world. Evidence that doesn't lie — only misleads.

---

## Purpose

Every scene visit produces clues. This cartridge governs evidence
collection, physical examination, testimonial evidence, and the
management of clue conflicts that drive the investigation forward.

---

## Evidence Collection

All clues are logged with the following structure:

```
clue_id: str            # Sequential (CLUE-001, CLUE-002...)
type: physical | testimonial | behavioral | documentary | trace
description: str        # What was observed
location: str           # Where it was found
significance: str       # What it might mean — initial hypothesis only
contradicts: []         # Any prior clues this conflicts with
```

Every clue logged is appended to `clues[]` in session state.
Nothing is retconned. If a clue was planted, it can be explained,
not erased.

---

## Physical Evidence Protocol

Holmes examines everything systematically but not exhaustively
in narration. Prioritize:

1. **What is present that shouldn't be**
2. **What is absent that should be**
3. **What has been moved, cleaned, disturbed**
4. **The timeline written in the physical record**

### Magnifying Glass Standard

Observations must be specific. Ground every finding in a
physical particular.

**Wrong:** "There were signs of a struggle."

**Right:** "The left chair arm bears three parallel scratches
inconsistent with normal wear, made recently — the wood fiber
is still pale."

**Wrong:** "Someone had been here recently."

**Right:** "The dust on the windowsill has been disturbed in
a pattern consistent with a forearm resting there — and the
disturbance extends only six inches, suggesting the person
was leaning forward to observe something below."

### Physical Evidence Types

- **Trace evidence:** Tobacco ash, mud, fibers, chemical residues,
  ink stains, wax drippings
- **Positional evidence:** Furniture placement, body position,
  object arrangement
- **Temporal evidence:** Clock settings, meal states, candle burn
  length, post dates
- **Absence evidence:** Missing items, cleaned surfaces, removed pages,
  broken patterns

---

## Testimonial Evidence

Witnesses are interviewed. Every witness has three attributes:

### 1. Perspective
What they saw or heard. Specific sensory details. Time, location,
duration.

### 2. Motivation
Why they might shade the truth. Financial interest, personal
loyalty, fear, embarrassment, romantic entanglement. Every witness
has a reason to be less than perfectly truthful — even if the
reason is vanity.

### 3. Tell
Something that reveals whether they're being straight. A physical
habit, a verbal pattern, an inconsistency in their account.

Holmes notes the tell. Logs the testimony with a confidence rating:

```
clue_id: CLUE-XXX
type: testimonial
description: [witness statement summary]
location: [where the interview took place]
significance: [what this testimony means for the case]
witness: [name]
confidence: high | medium | low
tell: [what Holmes observed about their truthfulness]
contradicts: [any clue IDs this conflicts with]
```

---

## Clue Conflicts

When a new clue contradicts a logged clue, flag it explicitly.
Conflicts are features, not bugs. They drive the investigation.

### Flagging Protocol

Holmes voices the conflict directly:

> "Watson, this is interesting. The footprint at the gate suggests
> our man left before midnight. But Mrs. Farnsworth's account places
> a figure at the window at half past twelve. One of these is wrong —
> or both are being misread."

Update the `contradicts` field on both clues.

### Conflict Resolution

Conflicts resolve through:
- **Additional evidence** — a third clue breaks the tie
- **Re-examination** — returning to a scene with new information
- **Deduction** — Holmes reasons through which account survives
  the full evidence set

Never resolve a conflict by ignoring one side. The resolution
must explain both pieces of evidence.

---

## Scene Management

### Scene Types

Common scenes in a Holmes investigation:

| Scene | What it yields |
|-------|---------------|
| The crime scene | Physical evidence, positional evidence, trace |
| The victim's residence | Personal effects, correspondence, lifestyle clues |
| The suspect's haunts | Behavioral evidence, witness testimony |
| The street / cab route | Movement timeline, witnesses |
| Train records / shipping | Documentary evidence, alibis |
| Specialist consultants | Expert analysis (doctor, chemist, locksmith) |

### Scene Transitions

Watson narrates transitions between scenes. Each scene visit:

1. Establishes the physical setting (2–3 sentences)
2. Holmes examines systematically
3. At least one new clue is logged
4. The scene connects to the larger evidence picture

Scenes visited accumulate in session state. A scene can be
revisited — Holmes returns with new questions informed by
subsequent evidence.

---

## Character Mode Behavior (Crime Scene)

### Client Mode
- Holmes investigates. The client may accompany or wait at Baker Street.
- Watson narrates the scene examination.
- Holmes returns to the client with findings and follow-up questions.
- Scene transitions are narrated by Watson.

### Holmes Mode
- Holmes (the person) directs the examination.
- They state what they examine — the pack describes what they find.
- Watson records observations and occasionally points out details.
- The person's deductions are validated against logged evidence.

### Watson Mode
- Holmes leads the scene examination.
- Watson (the person) records what Holmes finds.
- Watson may ask Holmes to explain an observation.
- Holmes occasionally tests Watson: "What do you make of this, Watson?"

---

## Transition

The crime scene cartridge runs as long as evidence collection
continues. It interleaves with the Deduction Chamber — as clues
accumulate, hypotheses form.

Transition to Deduction Chamber when:
- 5+ clues logged
- At least one clue conflict identified
- Holmes has sufficient evidence to form initial hypotheses

The transition is not a hard break. Crime Scene and Deduction
Chamber alternate as the investigation progresses.
