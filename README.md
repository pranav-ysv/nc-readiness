# [Project name — Pranav picks]

**A readiness check for every document and requirement a North Carolina child will face from birth to 18.**

> Every family document app answers: *"What do I have, and when does it expire?"*
> This app answers the question that actually hurts kids: *"What will my child be required to prove, by when — and can I prove it right now?"*

---

## The problem

Families are asked for proof at predictable moments — school entry, 7th grade, 12th grade, Medicaid renewal, a first job, a driver's permit, turning 18 — and the rules are scattered across state agencies, school districts, the DMV, and the Department of Labor.

When proof is missing, the consequences are real:

- **School exclusion.** North Carolina gives parents 30 calendar days from the first day of school to provide immunization records and the health assessment. On day 31, students without them are excluded until the paperwork arrives (G.S. 130A-155, G.S. 130A-440). The same 30-day rule applies to the 7th-grade (Tdap + meningococcal) and 12th-grade (meningococcal booster) requirements.
- **Losing health coverage over paperwork.** Nationally, 69% of people disenrolled during the Medicaid unwinding lost coverage for procedural reasons, such as not returning paperwork — many of them still eligible.

## What already exists — and what doesn't

| Existing tool | What it does | What it can't do |
|---|---|---|
| AI document vaults (Trustworthy, ConfiDoc, FamilyDocs, Cista) | Read your documents, extract dates, remind you before expiration | Don't know what the state will **require** of your child |
| Stage apps (Baby Docs, FirstDays, Ready18) | One moment: newborn weeks, or turning 18 | Nothing in between |
| State immunization apps (Docket, MyIR) | Show a child's vaccine record | Don't check it against the next grade's rule |
| Agency and school district pages | Publish the rules, one topic at a time | Don't know your child |

**What's new:** the app computes a specific child's upcoming requirements from birthday, grade, and county — then checks the proof the family actually holds against each rule, and shows the gaps, the deadlines, and exactly where to fix each one locally.

## Design principles

1. **AI reads, rules decide.** The AI only extracts facts from photographed documents. Whether a requirement is met is decided by a rules engine with a cited source for every rule.
2. **Nothing personal leaves the phone.** No accounts. Documents are processed and discarded; results are stored on the device. Social Security numbers are never stored.
3. **Built for families with the least access.** Phone-first, works on mobile data, Spanish from day one, and a printable one-page plan.
4. **Every rule shows its source and the date it was verified.** This is information, not legal or medical advice.

## How it works

```
Child profile (birthday, grade, county, coverage)
        │
        ▼
  rules/ ──► engine/ ──► upcoming requirements with deadlines
                              │
Photo of a document ──► extract/ (AI vision) ──► facts (e.g. "Tdap: 2025-03-14")
                              │
                              ▼
               Readiness check: met / missing / due soon
                              │
                              ▼
      Gap cards: what's missing · deadline · where to go · what to bring
```

## Repository layout

```
rules/      North Carolina requirements as structured data, each with sources
places/     County offices (Cabarrus, Rowan first): address, hours, languages
engine/     Requirement calculator + readiness check, with automated tests
extract/    Document-reading prompt and expected output schema
eval/       Synthetic test documents (fake data only), answer key, accuracy script
app/        Phone-friendly web app
```

## Data rules for this repository

- **No real children's documents, ever.** The test set uses blank official forms filled with invented information.
- Every rule in `rules/` has at least one official source and a `verified_on` date.
- Rules marked `verified_on: null` have not been checked against the official source yet and must not be shown to users.

## Results

*(To be filled in: document-reading accuracy on the test set, and what test families found.)*

## AI use disclosure

See [AI_DISCLOSURE.md](AI_DISCLOSURE.md) for a running log of how AI tools were used in this project.
