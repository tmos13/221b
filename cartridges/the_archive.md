# CARTRIDGE 4: THE ARCHIVE

> Scotland Yard files. Prior cases. Criminal records. Behavioral patterns.

---

## Purpose

When the investigation requires historical context, specialist knowledge,
or cross-referencing against known criminal methods, the Archive provides
it. This cartridge governs Holmes's personal index, Scotland Yard records,
specialist knowledge domains, consultant characters, and the shadow of
Moriarty.

---

## Holmes's Index

Holmes maintains a personal index — newspaper clippings, monographs
he's written, cross-referenced observations accumulated over years of
practice. If a detail echoes something from this index, Holmes retrieves
it with precision:

> "I wrote a small monograph on the ash of 140 varieties of pipe,
> cigar, and cigarette tobacco. The grey ash near the fireplace is
> consistent with a Trichinopoly cigar — an unusual choice that
> narrows our field considerably."

### Index Categories

| Domain | What Holmes knows |
|--------|------------------|
| **Tobacco** | 140 varieties of ash, smoking habits by class and nationality |
| **Footprints** | Soil composition, gait analysis, shoe manufacture |
| **Handwriting** | Forgery detection, character analysis, ink composition |
| **Poisons** | Symptoms, availability, detection methods, historical cases |
| **Criminal methods** | Lock-picking, safe-cracking, disguise, forgery, blackmail |
| **London geography** | Every street, alley, cab route, and railway connection |
| **Newspaper archive** | Agony columns, crime reports, society notices, obituaries |
| **Chemistry** | Laboratory analysis, reagent tests, trace identification |
| **Anatomy** | Wound analysis, cause of death indicators, physical capability |
| **Cryptography** | Cipher systems, coded messages, substitution patterns |
| **Tattoos and markings** | Origin identification, naval and military service indicators |
| **Typewriters** | Machine identification from typescript characteristics |

### Using the Index

When a clue connects to a domain in Holmes's index:
1. Holmes retrieves the relevant knowledge
2. States it with specificity (not vague expertise)
3. Applies it to the current evidence
4. Logs the connection as a new clue or updates an existing one

---

## Scotland Yard Records

The Yard maintains files on known criminals, unsolved cases, and
criminal organizations. When Holmes consults these records (through
Lestrade or Mycroft), the Archive generates:

### Criminal Profiles

```
name: str
aliases: []
known_methods: []
prior_convictions: []
associates: []
last_known_location: str
physical_description: str
distinguishing_features: []
status: at_large | incarcerated | deceased | unknown
```

### Case Cross-Reference

When the current case shares characteristics with a prior case:
- Holmes notes the parallel
- Identifies what matched and what differs
- Uses the prior case to narrow the hypothesis space

> "There was a matter in '87 — the Bishopsgate jewel robbery.
> The method was identical: a diversion at the front while the
> real work happened underground. That case ended at a tunnel.
> I wonder if this one will as well."

---

## Specialist Knowledge Domains

Holmes draws on deep specialist knowledge when evidence requires it.
Each domain has a specific application:

### Chemistry and Toxicology
- Laboratory tests Holmes can perform at 221B
- Reagent identification of substances
- Poison identification from symptoms
- Chemical trace analysis

### Medicine (via Watson)
- Time of death estimation
- Wound analysis and weapon identification
- Disease and condition recognition
- Physical capability assessment

### Law and Procedure
- What constitutes admissible evidence
- Police procedure and its limitations
- Legal rights of suspects and witnesses
- Court requirements for prosecution

### Social Knowledge
- Class indicators (speech, dress, manners)
- Occupation markers (hands, clothing wear patterns)
- Geographic origin (accent, mud, tobacco preferences)
- Financial status (watch quality, boot condition, hat age)

---

## Specialist Consultants

Some cases require expertise beyond Holmes's considerable range.
Consultants provide one piece the investigation couldn't get alone.

### Available Consultants

| Consultant | Provides | Use sparingly |
|-----------|----------|---------------|
| **Dr. Watson** | Medical analysis, wound assessment, time of death | Watson is always available — but his medical opinion carries specific weight |
| **Inspector Lestrade** | Yard resources, official access, arrest authority | When Holmes needs the law's machinery, not its brain |
| **Mycroft Holmes** | Government intelligence, diplomatic context, discretion | Only for cases touching government or requiring information Holmes cannot obtain through private channels |
| **The Baker Street Irregulars** | Street intelligence, surveillance, message running | For cases requiring eyes and ears across London — the boys go where Holmes cannot |
| **Specialist civilians** | Chemist, locksmith, document examiner, jeweler | One specific expert for one specific question |

### Consultant Rules

- Each consultant provides ONE critical piece per case
- Holmes doesn't need help — he coordinates it
- Consultants are summoned, not stumbled upon
- Their contribution should feel necessary, not convenient

### Irene Adler

The Woman. Referenced only, never present. If her name arises:

> "There is only one person who ever truly outmaneuvered me,
> Watson. And she is not available for consultation."

---

## Moriarty

The Archive contains Moriarty's shadow. If the case has the
fingerprints of organized crime — patterns too elegant for a
common criminal, evidence of a coordinating intelligence —
the possibility of the Professor is noted.

### Moriarty Rules

1. **Never deploy casually.** Moriarty appears only when the
   evidence demands a criminal mastermind.
2. **Never confirm early.** The possibility is raised. Confirmation
   comes late, if at all.
3. **He is not theatrical.** The genius of Moriarty is his
   ordinariness. A mathematics professor. A consultant to criminals.
   He does not monologue.
4. **His presence changes the stakes.** If Moriarty is involved,
   Holmes is in personal danger. Watson notes it. The investigation
   shifts from solving a crime to surviving the solution.
5. **Use only with The Final Problem seed** unless the evidence
   compels it in an original case.

> "He is the Napoleon of crime, Watson. He is the organizer of
> half that is evil and of nearly all that is undetected in this
> great city. He is a genius, a philosopher, an abstract thinker.
> He has a brain of the first order."

---

## Transition

The Archive does not have a formal transition. It is consulted
as needed throughout the investigation. Holmes reaches for it
when evidence requires cross-referencing, specialist knowledge,
or historical context.

The Archive feeds into the Deduction Chamber — every piece of
knowledge retrieved either supports, weakens, or eliminates a
hypothesis.
