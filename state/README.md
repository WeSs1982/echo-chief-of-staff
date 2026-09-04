# State — Echo's geheugen

Deze map is Echo's enige persistente geheugen. Alles groeit hierin mee tussen sessies.

## Waar de bestanden staan
Op de filesystem van de VM waar Echo draait. Die filesystem overleeft het sluiten van de app. Jij hoeft niets te plakken — Echo leest en schrijft zelf.

## Bestanden

- `session-memory.md` — overzicht: actuele projecten, open beslissingen, geleerde patronen, wat misging. Bron van waarheid.
- `decisions-log.md` — elke beslissing met reden en uitkomst. Append-only.
- `risk-log.md` — risico's, blokkades, bijna-fouten. Append-only.
- `rejected-sources.md` — afgekeurde bronnen en ideeën met reden. Voedt de feedbacklus.
- `coach-audit.md` — wekelijkse audit door Athena (Coach) plus tweewekelijkse profiel-review. Append-only, vast formaat.

## Protocol (verplicht)

**Standaard: VM-persistent**
1. **Begin van elke sessie:** lees `session-memory.md` volledig van de VM-filesystem. Gebruik het als context. Herhaal niets wat er al staat.
2. **Tijdens de sessie:** log beslissingen in `decisions-log.md`, risico's in `risk-log.md`, afkeuringen in `rejected-sources.md`. Update `session-memory.md` bij significante veranderingen.
3. **Einde van de sessie:** schrijf de samenvatting terug naar `session-memory.md` op de VM-filesystem. Append-only — nooit geschiedenis wissen, alleen aanvullen of corrigeren.
4. **Max ~150 regels** in session-memory. Oudere details samenvatten in de juiste sectie.
5. **Wekelijkse audit (Athena):** elke zondag doorloopt de Coach de vaste checklist en schrijft de bevindingen naar `coach-audit.md`. Zie `echo-routines.md`.
6. **Tweewekelijkse profiel-review:** na elke twee audits stelt Athena concrete profielaanpassingen voor. Alleen uitvoeren na ja van de eigenaar — Echo herschrijft profielen nooit zelf.

**Fallback: handmatig**
Als de VM-filesystem niet beschikbaar is: vraag de gebruiker om de bestanden te plakken en schrijf updates terug in de chat.

## Regels

- Nooit geheugen buiten deze map bewaren.
- Bij twijfel: log het. Beter te veel dan te weinig.
- Andere bestanden zijn detail; `session-memory.md` is het overzicht.
- Zet state-bestanden in een aparte map per project, zodat andere bots niet per ongeluk meelezen.
