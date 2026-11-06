# Förder-Dolmetscher — Programme Corpus

Five Baden-Württemberg funding programmes curated for the PoC. Source data extracted from official XML exports
(Förderprogramm-Datenbank Baden-Württemberg) and manually verified against primary sources. Reproduced here
for non-commercial, educational reference only.

> **Status note:** Programme data reflects the state at time of PoC build (August–September 2026).
> Always verify against the current primary source before use. E-Lastenräder is confirmed closed
> (programme ended 31 December 2024); the other four programmes should be independently verified.

---

## 1. Landesinitiative III Marktwachstum Elektromobilität BW — E-Lastenräder

**Status: PROGRAMM BEENDET (closed 31 December 2024)**
**Source file:** `e-lastenraeder.xml`
**Role in PoC:** Retained as a data-integrity test case (stale data learning case)

### Metadata
- Förderart: Zuschuss
- Förderbereiche: Energieeffizienz/Erneuerbare Energien, Infrastruktur, Mobilität
- Fördergebiet: Baden-Württemberg
- Förderberechtigte: Unternehmen, Kommune, Verband/Vereinigung, Öffentliche Einrichtung
- Fördergeber: Land
- Datum der Ausstellung: 2020-05-26
- Ablaufdatum: (not in XML export — programme closure discovered via manual source check)

### Application links
- L-Bank Elektrolastenräder information: http://www.l-bank.de/elektrolastenrad
- Antrag auf Zuwendung (application form): https://www.l-bank.de/formularassistent/fh/antrag-auf-zuwendung-fur-elektrolastenrader-fur-den-gewerblichen-gemeinnutzigen-gemeinschaftlichen-oder-kommunalen-einsatz.html

### Contact
- L-Bank, Staatsbank für Baden-Württemberg
- E-Mail: elektromobilitaet@l-bank.de
- Telefon: 0721 1501750

### Key conditions (from programme text)
- Vehicles must be used for goods, materials or passenger transport in commercial, non-profit, community or municipal contexts
- Vehicles must be deployed in Baden-Württemberg for at least 3 years (or full leasing period, max 3 years)
- Private-use-only vehicles are excluded
- Funding: 25% of eligible acquisition costs, max EUR 2,500 per E-Lastenrad, max 20 vehicles per applicant
- Keine Kumulierung with Bundesprogramm Klimaschutzinitiative E-Lastenfahrräder in Wirtschaft und Kommunen

### PoC learning case
This programme was the original golden path. During final QA, a manual check of the primary source revealed
the programme had closed on 31 December 2024. The XML export used as the data source had not reflected
this closure status. The golden path was changed to Kulturinitiativen; E-Lastenräder was retained as a
negative/status test case demonstrating the data freshness requirement.

---

## 2. Förderung Klimaschutz-Plus

**Status: Active (verify independently — Ablaufdatum in export: 2025-09-05)**
**Source file:** `klimaschutz-plus.xml`
**PoC match tier:** Geringe Übereinstimmung

### Metadata
- Förderart: Zuschuss
- Förderbereiche: Energieeffizienz/Erneuerbare Energien, Infrastruktur, Smart Cities/Regionen
- Fördergebiet: Baden-Württemberg
- Förderberechtigte: Kommune, Verband/Vereinigung
- Fördergeber: Land
- Datum der Ausstellung: 2019-12-10

### Application links
- Baden-Württemberg information page: https://um.baden-wuerttemberg.de/de/presse-service/foerderprogramme/klima/klimaschutz-plus-fuer-kommunen
- L-Bank information: https://www.l-bank.de/produkte/finanzhilfen/klimaschutz-plus-2025.html

### Contact
- Landeskreditbank Baden-Württemberg (L-Bank)
- E-Mail: info@l-bank.de
- Telefon: +49 721 150-0

---

## 3. Förderung von Kulturinitiativen und soziokulturellen Zentren

**Status: Active (verify independently)**
**Source file:** `kulturinitiativen-und-soziokulturellen-zentren.xml`
**PoC match tier:** Starke Übereinstimmung — PRIMARY GOLDEN PATH

### Metadata
- Förderart: Zuschuss
- Förderbereiche: Kultur/Medien/Sport, Infrastruktur
- Fördergebiet: Baden-Württemberg
- Förderberechtigte: Kommune, Verband/Vereinigung
- Fördergeber: Land (Wissenschaftsministerium / LAKS)
- Datum der Ausstellung: 2019-11-26
- Rechtsgrundlage: Verwaltungsvorschrift des Wissenschaftsministeriums (5. Dezember 2017, Az.: 53-7903.81/620/10), zuletzt geändert 5. Dezember 2025

### Application links
- LAKS information: https://www.laks-bw.de/foerderung/landesfoerderung

### Contact
- Landesarbeitsgemeinschaft der Kulturinitiativen und soziokulturellen Zentren in Baden-Württemberg (LAKS) e.V.
- E-Mail: soziokultur@laks-bw.de
- Telefon: +49 721 470419-09

### Key conditions (from VwV)
- Zuwendungsempfänger: Kulturinitiativen und soziokulturelle Zentren in privater, freier und unabhängiger Trägerschaft, die gemeinnützig tätig sind
- Mindestens dreijährige nachgewiesene Tätigkeit (Abschnitt 4a)
- Kommunale Mitfinanzierung im Verhältnis 2:1 erforderlich (kommunale Mittel müssen in doppelter Höhe nachgewiesen werden) (Abschnitt 4)
- Spartenübergreifendes, für die Öffentlichkeit bestimmtes Programm mit Eigenveranstaltungen
- Antragsfrist: 31. Januar bei RP und LAKS
- Max. Förderhöhe: 350.000 EUR pro Förderjahr (institutionelle Förderung der laufenden Programmarbeit)
- Privatpersonen sind von der Förderung ausgeschlossen

### PoC requirement results (Kulturinitiativen golden path — Verein scenario)
- **Erfüllt:** Gemeinnütziger Verein ✓ | Spartenübergreifendes Programm ✓ (stated) | Kommunale Förderung bestätigt ✓
- **Unklar:** Mindestens 3 Jahre nachgewiesene Tätigkeit (not stated by user) | Kommunale Beteiligung genaues Verhältnis (confirmed but ratio unverified) | Antragsfrist (deadline known but timing not checked)
- **Fehlend:** (none in golden path scenario)

---

## 4. Sportförderrichtlinien Baden-Württemberg

**Status: Active (verify independently)**
**Source file:** (BaWü sports funding guidelines)
**PoC match tier:** Nicht priorisiert

---

## 5. Amateurmusik Baden-Württemberg

**Status: Active (verify independently)**
**Source file:** (BaWü amateur music funding)
**PoC match tier:** Geringe Übereinstimmung

---

## About the corpus

The PoC corpus was drawn from a broader dataset of 126 Baden-Württemberg funding programme records
extracted from the official Förderprogramm-Datenbank XML export. The five programmes above were selected
to give coverage across:

- Different Förderbereiche (mobility, climate, culture, sport, music)
- Different Förderberechtigte types (Verein, Kommune, Unternehmen)
- Different match tiers (to demonstrate the full range of output states)
- One closed programme (data integrity / freshness test case)

The 126-record overview CSV is not included in this repository but is referenced in the project log.
