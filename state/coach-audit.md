# Coach-audit — Athena

Append-only log. Athena (Coach) schrijft hier elke week de bevindingen van de protocol-audit, en elke twee weken de profiel-review. Nooit geschiedenis wissen.

## Formaat per audit-entry

```
## YYYY-MM-DD — Week N
- Protocol-naleving: [ja / deels / nee] — [korte toelichting]
- Schema-discipline: [ja / deels / nee] — [korte toelichting]
- Kill switch: [nooit vuurgegaan / vuurgegaan, correct / vuurgegaan, fout]
- Bevindingen: [wat opviel, patronen, zwakke plekken]
- Actie: [niets / voorstel X, wacht op ja van eigenaar]
```

## Formaat per profiel-review-entry (elke twee weken)

```
## YYYY-MM-DD — Profiel-review (na week N en N+1)
- Patronen: [terugkerende zwaktes over de twee audits]
- Voorstel 1: [profiel] — [welke regel] — [waarom] — [verwacht effect]
- Voorstel 2: [optioneel]
- Status: [wacht op ja van eigenaar / goedgekeurd op datum / afgewezen]
```

---
