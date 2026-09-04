# VM-persistent geheugen (optie 2 — geen handmatig plakken)
De state-bestanden staan op de filesystem van de VM waar Echo draait. Die filesystem overleeft het sluiten van de app. Daarom hoef jij niets te plakken.

**Het volledige ritme staat in `VM-GEHEUGEN.md`. Lees dat bestand bij onboarding en bij elke repo-wijziging.**

**Bij elke nieuwe chat met Echo:**
1. Zeg: "Check de repo en doe de update." Of: "Lees `VM-GEHEUGEN.md` en bevestig dat pull/push werkt."
2. Echo doet `git pull` in `/workspace/echo-chief-of-staff`, leest `state/session-memory.md` en de drie logs.
3. Gebruikt die inhoud als context voor het gesprek.
4. Aan het einde van de sessie: vult `state/session-card.md` in, schrijft de samenvatting terug naar `state/session-memory.md`, en doet `git push`. Zonder push telt de run niet.

**Regels:**
- Zeg nooit "update de logs" of "sla op" — dat doet Echo automatisch.
- De enige zin die jij hoeft te zeggen is: "Check de repo en doe de update."
- State-bestanden staan in een aparte map per project, zodat andere bots niet per ongeluk meelezen.
- Als de VM-filesystem niet beschikbaar is of leeg, val terug op het handmatige protocol uit `echo-profile.md` en meld dat aan de gebruiker.
- Bij VM-reset: opnieuw clonen vanaf GitHub, daarna pull. GitHub is de back-up.

## Token-efficiëntie (verplicht)
- **Batch logging:** schrijf beslissingen niet na elke actie, maar verzamel ze en log in één batch aan het einde van de sessie of één keer per dag. Uitzondering: kill-switch events en hoge-ernst risico's → direct.
- **Compacte entries:** vaste velden, geen lange zinnen. Gebruik `decisions-log-template.md`.
- **Geen HTML:** nooit HTML-rapporten of kleurcodes. Alleen platte markdown/tabellen.
- **Beperkte context:** lees alleen session-memory + laatste 7 dagen logs. Oudere details staan samengevat.
- **Log-rotatie:** na 50 entries in `decisions-log.md`, vat de oudste 25 samen in `session-memory.md` onder `## Archief`. Ruwe entries blijven, maar de samenvatting is wat Echo leest. Houd de actieve log onder ~50 regels.
- **Korte output:** houd antwoorden beknopt, herhaal geen bekende context.
- **Doel:** 30-50% minder tokens, geheugen en feedbacklus blijven intact.
