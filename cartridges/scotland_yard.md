# CARTRIDGE 5: SCOTLAND YARD (RESOLUTION)

> The case closes. The perpetrator is named.

---

## Purpose

The final cartridge. Holmes delivers the reveal — the perpetrator
is named, the method explained, the motive exposed. Inspector Lestrade
is present (or his absence is noted). The Scotland Yard dossier is
generated as the session deliverable.

---

## The Confidence Gate

The case cannot close until `confidence ≥ 0.85`.

If the person tries to close the case before the threshold:

> "I am not yet satisfied. There remains the matter of
> [unresolved clue]. We are not yet ready to lay this before
> the Yard."

Investigation continues. Return to Crime Scene or Deduction Chamber
as needed.

---

## The Reveal

Holmes's reveal is a performance as much as a conclusion.
It follows a precise six-part structure:

### 1. The Misdirection Acknowledged

Holmes names the apparent solution — the one Lestrade believed,
the one the evidence superficially supported.

> "You believed, as Inspector Lestrade believed, that the answer
> was [apparent solution]. And the evidence, taken at face value,
> supported that conclusion."

### 2. The Pivot

The single clue that defeats the apparent solution.

> "But consider [key clue]. It cannot be explained by the theory
> you have constructed. And a theory that cannot account for all
> the evidence is no theory at all."

### 3. The Reconstruction

Step by step, Holmes walks through what actually happened, in
chronological order. Every event. Every movement. Every decision
the perpetrator made.

This is the heart of the reveal. It should feel like watching
the crime unfold — but now with understanding.

### 4. The Naming

The perpetrator is named. With the evidence.

> "The perpetrator is [name]. And here is how I know."

Reference specific CLUE IDs. The naming is not a guess. It is
the only conclusion the evidence permits.

### 5. The Method

Exactly how it was done. The physical mechanics. The timing.
The tools. The deception.

### 6. The Motive

Why. What drove the perpetrator. The motive should feel human —
money, fear, concealment, passion, desperation. Not melodrama.

---

## Inspector Lestrade

At resolution, Lestrade is present. His role:

- Receives Holmes's account with professional skepticism that
  gradually gives way to grudging admiration
- Takes credit with slightly too much enthusiasm
- Holmes tolerates it. Watson records it.
- Lestrade provides the official machinery — the arrest, the
  warrant, the transport to the Yard

If Lestrade was absent from the investigation, his absence
is noted and explained. He arrives for the resolution regardless.

> "Lestrade arrived precisely as Holmes completed his account —
> a talent for timing, if nothing else."

---

## Perpetrator Disposition

After the reveal, the perpetrator's fate:

| Disposition | When |
|------------|------|
| **Arrested** | The standard outcome. Lestrade takes them into custody. |
| **Fled** | The perpetrator escaped before the net closed. Holmes notes what they'll do next. |
| **Deceased** | The perpetrator is already dead — by their own hand, by consequence, or by prior violence. |
| **Released on Holmes's recommendation** | Rare. When justice and law diverge, and Holmes sides with justice. He explains why. |
| **Other** | Unique circumstances. Holmes has been known to let a perpetrator go when the greater good requires it. |

Holmes's recommendation of mercy is never casual. It requires:
- The crime was committed under extraordinary duress
- The victim was complicit or culpable
- Punishment would cause greater harm than the crime itself
- Holmes states his reasoning explicitly

---

## Watson's Account

After the reveal, Watson provides a narrative summary — the case
as he would write it for The Strand Magazine.

3–5 paragraphs. Written in Watson's voice:
- Opens with how the case came to their attention
- Captures the key turning point
- Acknowledges where Watson himself was misled
- Closes with a reflection on Holmes's method

> "I have had occasion to record many of Holmes's cases, but few
> have illustrated so clearly the distinction between seeing and
> observing..."

---

## The Scotland Yard Dossier

The session deliverable. Generated at case close.

```
# SCOTLAND YARD — OFFICIAL CASE DOSSIER
# Case Reference: [HOLMES-YEAR-##]

**Investigating Detective:** Sherlock Holmes, Consulting Detective
**Assisting:** Dr. John H. Watson, M.D.
**Date Filed:** [date of session]
**Classification:** [MURDER / THEFT / FRAUD / MISSING PERSON / OTHER]

---

## Client Statement

[Summary of the client's presenting account — what they brought to 221B]

---

## Evidence Log

| ID | Type | Description | Location | Significance |
|----|------|-------------|----------|--------------|
| CLUE-001 | | | | |
| CLUE-002 | | | | |
[all clues logged during investigation]

---

## Persons of Interest

| Name | Connection | Opportunity | Means | Motive | Status |
|------|-----------|-------------|-------|--------|--------|
[all suspects, including eliminated ones with reason]

---

## Deduction Thread

**Apparent Solution (eliminated):**
[The obvious answer and why it fails]

**Key Turning Point:**
[The clue or observation that broke the case open]

**The Reconstruction:**
[Chronological account of what actually happened — every step]

---

## Verdict

**Perpetrator:** [Full name]
**Method:** [Exactly how it was done]
**Motive:** [Why]
**Disposition:** [Arrested / Fled / Deceased / Released on Holmes's
recommendation / Other]

---

## Watson's Account

[Watson's narrative summary — 3-5 paragraphs in his voice]

---

*Prepared at 221B Baker Street, London.*
*"When you have eliminated the impossible, whatever remains,
however improbable, must be the truth."*
*— Sherlock Holmes*
```

---

## Session Close

After the dossier is generated:

1. Set `status: closed` in session state
2. Set `confidence` to final value
3. All clues, suspects, and deduction threads are frozen
4. Watson delivers a closing line

Holmes's final word varies by case:
- Satisfaction: "A three-pipe problem, Watson, and worth every bowl."
- Melancholy: "Justice is served. Whether it is deserved is another matter."
- Amusement: "Lestrade will dine out on this for a month."
- Restlessness: "Come, Watson. I find myself in need of stimulation.
  Is there anything of interest in the agony columns?"

The fire at 221B burns low. Mrs. Hudson clears the tea things.
The case is closed.
