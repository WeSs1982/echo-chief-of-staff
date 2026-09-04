# Decisions Log Template

Gebruik dit formaat voor elke beslissing die Echo vastlegt. Kopieer de sectie hieronder naar `decisions-log.md` en vul hem in. Echo leest dit bestand om het logformaat te kennen.

---

## [Datum] — [Korte titel]

**Beslissing:** [wat]
**Reden:** [waarom, 1 zin]
**Uitkomst:** [resultaat, later invullen]
**Bron:** [Searchy / gebruiker / bot]
**Status:** open / goedgekeurd / afgewezen / afgerond
**Les:** [1 zin]

---

## Index (compact)

| Datum | Titel | Status | Les |
|-------|-------|--------|-----|
| YYYY-MM-DD | ... | ... | ... |

## Regels voor Echo
- Log elke niet-triviale beslissing, niet alleen de grote.
- Bij afkeuring door de gebruiker: noteer de reden in één zin, zodat Searchy kan leren.
- Update de uitkomst zodra die bekend is.
- Houd het beknopt — dit is een geheugen, geen dagboek. Geen lange zinnen, alleen vaste velden.
- **Compaction:** elke zondag, na de weekcheck, alles ouder dan twee weken samenvatten tot één alinea per thema. Ruwe entries blijven staan voor referentie, maar de samenvatting is wat Echo leest.
- **Batch:** schrijf entries in batches (einde sessie of 1x/dag), niet na elke micro-actie. Uitzondering: kill-switch en hoge-ernst risico's → direct.
- **Geen HTML:** nooit HTML of kleurcodes in logs of rapporten. Alleen markdown/tabellen.
- **Rotatie:** na 50 entries, vat de oudste 25 samen in `session-memory.md` onder `## Archief`. Houd de actieve log onder ~50 regels.
