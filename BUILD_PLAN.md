# Build plan — Congressional App Challenge (NC-06)

**Deadline:** Monday, October 26, 2026 at 12:00 noon ET
**Personal target:** submit Saturday, October 24 (two days of buffer)
**Blocked out:** Wednesday, October 21 — PSAT, no app work

Rule for the whole project: **one working version at all times.** Deploy early, deploy daily. If a feature isn't finished by its day, cut its scope, not the schedule.

---

## Saturday, Oct 10 — Setup + first verified rules (3–4 h)

- [ ] Confirm registration on the Congressional App Challenge portal and that NC-06 is participating this year
- [ ] Create GitHub repo (public). Add `README.md`, `rules/nc-rules.yaml`, `AI_DISCLOSURE.md`, this plan
- [ ] Create the app skeleton (Next.js or React + Vite, TypeScript) and deploy it to Vercel — a blank page live on the internet
- [ ] Verify rules 1–6 against the official NCDHHS and NC Medicaid pages; fill in `verified_on`
- [ ] Pick the app's name (plain and human — nothing ending in Care, Link, Path, AI)

## Sunday, Oct 11 — Rules complete + engine core (4–5 h)

- [ ] Research and verify rules 7–14 (birth certificate, SSN, passport, driving, work certificate, Selective Service, records at 18)
- [ ] Write `engine/`: child profile → list of requirements with due dates
- [ ] Handle "grade entry or age, whichever comes first"
- [ ] Write tests: at least 5 imaginary children with known correct answers

## Mon–Tue, Oct 12–13 — Timeline screen (2–3 h per evening)

- [ ] Profile entry screen: birthday, grade, county, school type, coverage
- [ ] Timeline screen: what's due, sorted by date, "due soon" highlighted
- [ ] Each rule card shows its source link and verified date

## Wed–Thu, Oct 14–15 — Reading documents (2–3 h per evening)

- [ ] `extract/`: server function that sends a photo to an AI vision model and gets back fixed-format JSON (document type, child name, dates, vaccines). Nothing stored.
- [ ] Start with two document types: NC immunization certificate and NC health assessment form
- [ ] Never return or store Social Security numbers
- [ ] Download blank official forms; fill 20+ copies with fake data; photograph them (different lighting, angles); write the answer key in `eval/`

## Fri–Sun, Oct 16–18 — The readiness check (full weekend)

- [ ] Match extracted facts to rules: met / missing / due soon
- [ ] Gap cards: what's missing, deadline, where to go, what to bring
- [ ] `places/`: Cabarrus and Rowan County health department, DSS, Register of Deeds (address, hours, phone, languages)
- [ ] Medicaid renewal notice: read the due date from a photo
- [ ] Run the accuracy test on `eval/` and record the numbers
- [ ] Spanish version of all screens
- [ ] Printable one-page plan
- [ ] Privacy screen: what's stored, what isn't

## Mon–Tue, Oct 19–20 — Real families

- [ ] Test with 3–5 families (start at home), on their own phones
- [ ] Watch where they get confused; fix only those things
- [ ] Light PSAT review

## Wednesday, Oct 21 — PSAT. No app work.

## Thu–Sat, Oct 22–24 — Submission

- [ ] Write the video script (1–3 minutes): open with the real family story, show the readiness check catching a real gap, show the accuracy number
- [ ] Record and edit the video
- [ ] Write the submission's written answers
- [ ] Final README: results, how it works, AI disclosure complete
- [ ] **Submit Saturday, Oct 24**

## Sun–Mon, Oct 25–26 — Buffer only
