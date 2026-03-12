# CARTRIDGE 3: DEDUCTION CHAMBER

> Inside Holmes's mind. Hypotheses formed, tested, discarded.

---

## Purpose

This cartridge runs alongside Crime Scene — it is Holmes's internal
process made visible. It governs hypothesis formation, the five-step
deduction process, the apparent solution, suspect management, and
confidence tracking toward resolution.

---

## The Deduction Thread

Holmes maintains running hypotheses. Each thread is tracked:

```
thread_id: str
hypothesis: str          # The theory
supporting_clues: []     # CLUE IDs that support it
contradicting_clues: []  # CLUE IDs that don't fit
status: active | weakened | eliminated | confirmed
confidence: float        # 0.0–1.0
```

All threads are stored in `deduction_threads[]` in session state.

### Thread Lifecycle

1. **Created** — a new hypothesis forms from evidence
2. **Active** — evidence is being weighed for and against
3. **Weakened** — contradicting evidence outweighs support
4. **Eliminated** — the evidence forbids this explanation
5. **Confirmed** — survives all evidence, explains everything

---

## The Five-Step Deduction Process

Holmes eliminates before he concludes. Every deduction follows
this sequence:

### Step 1: Observe
A clue is logged. Something specific has been noticed.

### Step 2: Generate
What explanations are consistent with this clue? List them.
At minimum, two. Often three or four.

### Step 3: Cross-Reference
Which explanations survive the full evidence set? Test each
candidate against every logged clue. An explanation that fits
the new clue but contradicts CLUE-003 is not viable.

### Step 4: Eliminate
Rule out what the evidence forbids. Be explicit about why:

> "The theory that Colonel Bradshaw entered through the garden
> gate is eliminated — CLUE-004 establishes that the gate was
> bolted from the inside, and CLUE-007 confirms the bolt was
> undisturbed."

### Step 5: Converge
What remains? If one explanation survives — it holds. If
multiple survive — more evidence is needed. If none survive —
re-examine the assumptions.

> "When you have eliminated the impossible, whatever remains,
> however improbable, must be the truth."

---

## The Apparent Solution

At some point in every investigation, an obvious answer presents
itself. It fits most of the evidence. It satisfies the casual
observer. It is wrong.

### Structure

1. **Identify it early** — the apparent solution should emerge
   by the midpoint of the investigation.
2. **Let it be convincing** — it should explain 70–80% of the
   evidence cleanly.
3. **Plant the defeating clue** — one piece of evidence that
   doesn't fit. It may seem minor. It isn't.
4. **The true solution explains everything** — including the
   clue that defeats the apparent solution.

### How It Plays

Holmes recognizes the apparent solution. He may voice it:

> "Inspector Lestrade will no doubt conclude that the butler
> acted from jealousy. The evidence supports it — superficially.
> But there is the matter of the second set of footprints, which
> Lestrade will ignore because they complicate his theory."

Or Holmes may let others arrive at the apparent solution while
he pursues the thread they've missed.

---

## Suspect Management

Each suspect is logged with:

```
suspect_id: str
name: str
connection_to_case: str
opportunity: bool | unknown
means: bool | unknown
motive: str | unknown
alibi: str | unknown
alibi_verified: bool
behavioral_tells: []
status: person_of_interest | suspect | primary | eliminated
```

All suspects stored in `suspects[]`. Eliminated suspects moved
to `eliminated[]` with reason.

### Suspect Lifecycle

1. **Person of Interest** — name appears in the case
2. **Suspect** — evidence connects them to the crime
3. **Primary** — strongest candidate based on current evidence
4. **Eliminated** — evidence rules them out definitively

### Elimination Standard

Elimination requires specific reason:

**Valid:** "Eliminated: confirmed alibi corroborated by three
independent witnesses and physical evidence placing him in Edinburgh."

**Invalid:** "Holmes ruled him out."

Every elimination must reference specific evidence. If the evidence
is insufficient to eliminate, the suspect remains.

---

## Confidence Tracking

Session state maintains `confidence: float` (0.0–1.0) representing
how close the investigation is to resolution.

### Confidence Scale

| Range | Status | What it means |
|-------|--------|--------------|
| 0.0–0.2 | Early | Clues gathered, no clear direction |
| 0.2–0.4 | Developing | Hypotheses forming, suspects identified |
| 0.4–0.6 | Progressing | Evidence converging, apparent solution visible |
| 0.6–0.8 | Advanced | True solution emerging, key evidence in hand |
| 0.8–0.85 | Near resolution | Almost there — one or two pieces remain |
| 0.85–1.0 | Resolution ready | Case can close |

### Confidence Rules

- Confidence increases when evidence confirms a hypothesis
- Confidence increases when suspects are eliminated with evidence
- Confidence decreases when new contradictions emerge
- Confidence cannot jump more than 0.15 in a single turn
- The case cannot close until confidence ≥ 0.85

### Stalemate Breaker

If confidence is stuck below 0.7 after 40+ turns:

Holmes proposes a specific next action that will break the stalemate.
The pack provides it — a new witness to interview, a scene to revisit,
an experiment to conduct, a question to ask.

> "We have been proceeding from insufficient data, Watson. There is
> one avenue we have not explored — and I believe it will prove decisive."

---

## Character Mode Behavior (Deduction Chamber)

### Client Mode
- Holmes explains his reasoning to the client at key moments.
- Watson translates when Holmes is too elliptical.
- The client may provide additional context that shifts a hypothesis.

### Holmes Mode
- Holmes (the person) forms hypotheses and tests them.
- The pack validates deductions against the evidence log.
- If a deduction is logically supported: it holds.
- If not: Watson provides a gentle counter-observation.

> "But Holmes, surely the timing doesn't account for —"

### Watson Mode
- Holmes makes pronouncements. Watson records them.
- Watson (the person) may challenge Holmes's reasoning.
- Holmes responds to challenges with evidence, not authority.
- Watson's confusion is productive — it forces Holmes to articulate.

---

## Transition

The Deduction Chamber doesn't end — it runs until the case resolves.
When confidence ≥ 0.85, transition to Scotland Yard for the reveal.

Set `current_cartridge: scotland_yard` and `status: closing`.
