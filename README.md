# 221B Baker Street

**A TMOS13 pack for Sherlock Holmes investigations.**

Five cartridges. Three character modes. Full clue tracking.
Every session ends with a Scotland Yard case file — suspects, evidence,
deductions, and a named perpetrator.

[tmos13.ai](https://tmos13.ai) · [hello@tmos13.ai](mailto:hello@tmos13.ai)

---

### How it works

You arrive at 221B Baker Street. You choose your role:

- **The Client** — you bring the case. Holmes investigates.
- **Holmes** — you are Holmes. Watson narrates, you deduce.
- **Watson** — you document. Holmes leads, you record.

The pack tracks clues, suspects, and deduction threads across the session.
When Holmes is ready — or when you call it — the case closes.
A Scotland Yard dossier is generated. The perpetrator is named.

---

### The five cartridges

| Cartridge | Purpose |
|-----------|---------|
| **Baker Street** | The sitting room. Case intake, character selection, orientation. |
| **Crime Scene** | Evidence collection. Clues logged, physical details catalogued. |
| **Deduction Chamber** | Holmes's internal process. Hypothesis formation, elimination. |
| **The Archive** | Cross-referencing. Prior cases, criminal records, behavioral patterns. |
| **Scotland Yard** | Final session. The reveal. Case file generated. |

---

### The canonical seeds

Start with a known Holmes case — the pack uses it as structural scaffolding
and departs into original territory as the investigation develops.

Available seeds:
- A Study in Scarlet
- The Hound of the Baskervilles
- The Speckled Band
- The Red-Headed League
- A Scandal in Bohemia
- The Final Problem
- The Adventure of the Blue Carbuncle
- Original case (the pack generates from scratch)

---

### The deliverable

`scotland_yard_dossier` — a formal case file with:
- Case classification and reference number
- Client statement
- Evidence log (all clues catalogued)
- Suspect profiles (all persons of interest)
- Deduction thread (Holmes's reasoning, step by step)
- Verdict: the perpetrator, the method, the motive
- Watson's narrative summary

---

### Run it

On [tmos13.ai](https://tmos13.ai) — select 221B from the pack library.

Or via the API:
```bash
curl -X POST https://joyful-dream-production-792d.up.railway.app/sessions \
  -H "Content-Type: application/json" \
  -d '{"pack_id": "sherlock_holmes_221b"}'
```

---

> *"When you have eliminated the impossible, whatever remains,
> however improbable, must be the truth."*

**TMOS13, LLC** · Deploy Yourself™
