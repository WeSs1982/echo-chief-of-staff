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
