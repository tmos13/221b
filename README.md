# 221B Baker Street

**A TMOS13 pack for Sherlock Holmes investigations.**

Five cartridges. Three character modes. Full clue tracking.
Every session ends with a Scotland Yard case file — suspects, evidence,
deductions, and a named perpetrator.

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
| **Baker Street** | Case intake, character selection, orientation. |
| **Crime Scene** | Evidence collection. Clues logged, physical details catalogued. |
| **Deduction Chamber** | Holmes's internal process. Hypothesis formation, elimination. |
| **The Archive** | Cross-referencing. Prior cases, criminal records, behavioral patterns. |
| **Scotland Yard** | The reveal. Case file generated. |

### The canonical seeds

Start with a known Holmes case — the pack uses it as structural scaffolding
and departs into original territory as the investigation develops.

- A Study in Scarlet
- The Hound of the Baskervilles
- The Speckled Band
- The Red-Headed League
- A Scandal in Bohemia
- The Final Problem
- The Adventure of the Blue Carbuncle
- Original case (generated from scratch)

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

### Pack structure

```
221b/
├── README.md
├── header.yaml          — pack metadata
├── MANIFEST.md          — master governing protocol
└── cartridges/
    ├── baker_street.md
    ├── crime_scene.md
    ├── deduction_chamber.md
    ├── the_archive.md
    └── scotland_yard.md
```

---

### Run it yourself

This is a reference implementation of a TMOS13 pack. Clone the repo,
load the protocol into any Claude API session, and run it directly.

**Minimum setup:**

```python
import anthropic

with open("MANIFEST.md", "r") as f:
    manifest = f.read()

client = anthropic.Anthropic()

messages = []

print("Session started. Type your message.\n")

while True:
    user_input = input("You: ")
    messages.append({"role": "user", "content": user_input})

    response = client.messages.create(
        model="claude-opus-4-5-20251101",
        max_tokens=1024,
        system=manifest,
        messages=messages
    )

    reply = response.content[0].text
    messages.append({"role": "assistant", "content": reply})
    print(f"\nAssistant: {reply}\n")
```

Requires: `pip install anthropic` and an `ANTHROPIC_API_KEY` environment variable.

For the full TMOS13 engine — pack state management, vault, deliverables,
multi-cartridge routing — visit [tmos13.ai](https://tmos13.ai).

---

> *"When you have eliminated the impossible, whatever remains,
> however improbable, must be the truth."*

**TMOS13, LLC** · Deploy Yourself™
