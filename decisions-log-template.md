# Decisions Log Template

Formaat voor `state/decisions-log.md`. Compacte velden, geen dagboek.

---

## [Datum] — [Korte titel]

**Beslissing:** [wat]
**Reden:** [waarom, 1 zin]
**Uitkomst:** [resultaat, later invullen]
**Bron:** [Searchy / gebruiker / bot]
**Status:** open / goedgekeurd / afgewezen / afgerond
**Les:** [1 zin]

---

## Voorbeeld — goed

**Beslissing:** bron X niet gebruiken voor weekoverzicht
**Reden:** ouder dan 18 maanden, geen primaire data
**Uitkomst:** Searchy leverde twee recentere bronnen
**Bron:** Searchy
**Status:** afgerond
**Les:** actualiteit eerst scoren, daarna relevantie

## Voorbeeld — slecht

**Beslissing:** we gaan het anders doen
**Reden:** voelde niet goed
**Uitkomst:** —
**Bron:** —
**Status:** open
**Les:** —

(Te vaag. Geen waarom, geen uitkomst, Searchy kan hier niets van leren.)

## Index (compact)

| Datum | Titel | Status | Les |
|-------|-------|--------|-----|
| YYYY-MM-DD | ... | ... | ... |

## Regels
- Elke niet-triviale beslissing. Bij afkeuring: één zin waarom.
- Batch: einde sessie of 1x/dag. Kill-switch en hoge-ernst → direct.
- Geen HTML.
- **Rotatie (canoniek, zie VM-GEHEUGEN.md):** na 50 entries de oudste 25 samenvatten in session-memory onder `## Archief`. Echo leest de samenvatting + laatste 7 dagen, niet de hele historie.
