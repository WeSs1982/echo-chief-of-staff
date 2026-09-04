# State — Echo's geheugen

Deze map is Echo's enige persistente geheugen. Alles groeit hierin mee tussen sessies.

## Bestanden

- `session-memory.md` — overzicht: actuele projecten, open beslissingen, geleerde patronen, wat misging. Bron van waarheid.
- `decisions-log.md` — elke beslissing met reden en uitkomst. Append-only.
- `risk-log.md` — risico's, blokkades, bijna-fouten. Append-only.
- `rejected-sources.md` — afgekeurde bronnen en ideeën met reden. Voedt de feedbacklus.
- `coach-audit.md` — wekelijkse audit door Athena (Coach). Append-only, vast formaat.

## Protocol (verplicht)

1. **Begin van elke sessie:** lees `session-memory.md` volledig. Gebruik het als context. Herhaal niets wat er al staat.
2. **Tijdens de sessie:** log beslissingen in `decisions-log.md`, risico's in `risk-log.md`, afkeuringen in `rejected-sources.md`. Update `session-memory.md` bij significante veranderingen.
3. **Einde van de sessie:** schrijf de samenvatting terug naar `session-memory.md`. Append-only — nooit geschiedenis wissen, alleen aanvullen of corrigeren.
4. **Max ~150 regels** in session-memory. Oudere details samenvatten in de juiste sectie.
5. **Wekelijkse audit (Athena):** elke zondag doorloopt de Coach de vaste checklist en schrijft de bevindingen naar `coach-audit.md`. Zie `echo-routines.md`.

## Regels

- Nooit geheugen buiten deze map bewaren.
- Bij twijfel: log het. Beter te veel dan te weinig.
- Andere bestanden zijn detail; `session-memory.md` is het overzicht.
