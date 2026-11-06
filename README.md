# Förder-Dolmetscher

**KI-gestützte Orientierungshilfe für Förderprogramme in Baden-Württemberg**
*An AI-assisted translation layer between project descriptions and public funding programmes.*

---

## What it is

Förder-Dolmetscher is a proof-of-concept decision-support tool that helps small organisations in
Baden-Württemberg — primarily registered associations (eingetragene Vereine), municipalities and small
businesses — navigate public funding programmes. Users describe their project in plain language; the tool
structures that input, matches it against a curated corpus of funding programme criteria, and surfaces
which programmes are worth pursuing, along with the specific requirements that are met, unclear, or missing.

Built as a course project during a WBS Training KI-Manager:in programme (September 2026), it received a
perfect score of 100/100 from the course evaluator.

## What it is not

- It does not make funding decisions or guarantee eligibility
- It does not replace official programme documentation or advice from a Förderberatung
- The HTML demonstration does not make live AI calls — all Layer 1–3 outputs were pre-generated and embedded
- The PoC covers five curated programmes only; it is not a comprehensive directory
- No live user pilot was conducted during the course timeframe

## How it works

The system uses a three-layer architecture:

**Layer 1 — Input structuring.** A user describes their project in free text and selects their legal form
(Rechtsform). An LLM structures this into typed fields (project type, location, target group, funding area)
and flags low-confidence items for human confirmation.

**Layer 2 — Programme matching.** Structured user input is compared against curated programme criteria.
Each programme receives a match tier (Starke Übereinstimmung, Geringe Übereinstimmung, etc.) derived from
deterministic rules applied to LLM-derived inputs.

**Layer 3 — Requirement explanation.** For each programme, the system explains which requirements are met
(erfüllt), unclear (unklar), or missing (fehlend), with evidence anchored to the user's stated information
and the original programme text (Förderrichtlinie).

A key architectural principle: **provenance governs what the system is allowed to claim.** User-stated
information, programme text, and AI suggestions are tracked separately. An AI suggestion alone cannot mark
a requirement as fulfilled. A conflict between user data and AI interpretation creates a blocking state that
must be resolved before proceeding.

## Repository structure

```
foerder-dolmetscher/
  README.md
  LICENSE
  poc/
    Foerder-Dolmetscher_PoC.html   — self-contained HTML demonstration (no live AI)
  prompts/
    prompts_v2.3.md                — full prompt pack, Layers 1–3
  data/
    programme-corpus.md            — five curated BaWü funding programmes with metadata
```

## The PoC scope

Five Baden-Württemberg funding programmes were curated for the PoC:

| Programme | Match tier | Notes |
|---|---|---|
| E-Lastenräder | — | Programm beendet; retained as data-integrity test case |
| Klimaschutz-Plus | Geringe Übereinstimmung | |
| Kulturinitiativen | Starke Übereinstimmung | Primary golden path |
| Sportförderrichtlinien | Nicht priorisiert | |
| Amateurmusik BW | Geringe Übereinstimmung | |

Source data: official Baden-Württemberg XML programme exports plus manual curation. See
[`data/programme-corpus.md`](data/programme-corpus.md) for full metadata and key conditions.

## Learning cases

**Stale official data.** The E-Lastenräder programme was validated against an official XML export before a
final manual check revealed the programme had closed on 31 December 2024. The export had not reflected this.
Response: changed the golden path, retained the closed programme as a negative test case, and identified
freshness checks and versioning as production requirements.
*Lesson: an authoritative source can still be operationally stale.*

**Absence is not confirmation.** An internal test initially marked a non-cumulative-funding condition as
fulfilled because the test user had never previously applied for funding. Team review identified this as a
logical error — absence of prior applications does not confirm absence of simultaneous ones. Result changed
to unklar.
*Lesson: missing information cannot be converted into confirmation.*

**Provenance became architecture.** What began as a colour-labelling system (which information came from
where) became a structural rule governing what the system was permitted to claim.
*Lesson: in an AI-assisted system, visual design decisions can have information-architecture consequences.*

## What I would build next

- A structured usability pilot comparing the existing RP BaWü funding page with Förder-Dolmetscher,
  measuring task completion, time-to-identification, and comprehension of key conditions
- Automated freshness checks and versioning for programme data
- Validation of the institutional adoption model through conversations with Kommunen, Verbände, and
  Förderberatungen
- Real workflow integration using no-code automation tools (n8n or Make) to replace the pre-run prompt
  outputs with a live three-layer pipeline

## Credits

Built by **Matt Miller** (concept, data curation, UX, HTML build, prompt engineering v2.2–v2.3) and
**Kunthanee Boekwaree** (agile PM, Projektarbeit, prompt engineering through v2.1) as part of the
WBS Training KI-Manager:in programme, Berlin, 2026.

## Licence

The HTML PoC and prompt pack are released under the [MIT Licence](LICENSE).
Programme source data originates from official Baden-Württemberg government sources and is reproduced here
for non-commercial, educational reference only.
