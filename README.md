# Echo — Chief of Staff Agent met Decisions Log

Echo is een chief-of-staff agent die niet alleen taken uitvoert, maar elke beslissing vastlegt met reden én uitkomst. Geen leeg template — een bewoond logboek dat leert.

Gebouwd op echte lessen, niet op theorie. Geschikt voor Grok Bot (SuperGrok / Cursor). Model-agnostisch in opzet: de structuur werkt overal waar een agent routines en geheugen kan bijhouden.

## Waarom dit anders is
- **Decisions-log met reden + uitkomst** — de meeste agents onthouden alleen wat ze deden. Echo onthoudt waarom, wat afgewezen werd, en of het klopte.
- **Feedbacklus** — elke afkeuring krijgt een korte reden, zodat de agent leert in plaats van hetzelfde te herhalen.
- **Kill switch** — stopt de keten bij fouten, lege pool of verlopen keys, en meldt het meteen.
- **Stille-bot detectie** — als een bot niets oplevert, is dat een signaal van ontbrekende toegang, geen stilte.
- **Drie routines** — wekelijkse samenvatting, dagelijkse prioriteiten, risico-log.
- **Repo-trigger** — zeg "ik heb de repo aangepast, check het", en Echo leest, bevestigt en past toe.

## Wat erin zit
- `echo-profile.md` — het profiel: missie, grenzen, escalatie-regel.
- `echo-routines.md` — de routines met tijden en ingangsdata.
- `decisions-log-template.md` — het logformaat (reden + uitkomst + index).
- `lessons-template.md` — hoe beslissingen regels worden.
- `risk-log-template.md` — plekken waar de keten kan breken.
- `LICENSE` — MIT, gratis te gebruiken en aan te passen.

## Snel starten
1. Maak een nieuwe Grok Bot en plak `echo-profile.md` als system prompt.
2. Sla `echo-routines.md` op als routines-bestand.
3. Maak `decisions-log.md`, `lessons.md` en `risk-log.md` aan op basis van de templates.
4. Koppel je mail en agenda als je die wilt laten beheren.
5. Zeg: "Check de repo en activeer de routines."

## Tags
chief-of-staff, agent-memory, decision-log, grok-bot, ai-agent, workflow-automation, lessons-learned, feedback-loop

## Licentie
MIT — gratis, geen kosten, geen abonnement vereist om te gebruiken.
