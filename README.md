# Echo + Searchy — Chief of Staff met Researcher en Feedbacklus

Echo is een chief-of-staff agent die niet alleen taken uitvoert, maar elke beslissing vastlegt met reden én uitkomst. Geen leeg template — een bewoond logboek dat leert.

Gebouwd op echte lessen, niet op theorie. Geschikt voor Grok Bot (SuperGrok / Cursor). Model-agnostisch in opzet.

## Waarom dit anders is
- **Decisions-log met reden + uitkomst** — waarom, wat afgewezen werd, en of het klopte.
- **Feedbacklus** — elke afkeuring krijgt een korte reden. Searchy past bronnenkeuze daarop aan.
- **Kill switch** — trigger, stop, melding, unlock. Zie `echo-routines.md`.
- **Stille-bot** — geen output in 7 dagen terwijl werk verwacht werd = rood, geen “stilte = het werkt”.
- **Research-bot** — Searchy met bron-kwaliteitsscore. Taken ná onboarding uit session-memory, niet uit vaste side-hustle-routines.
- **Drie kernroutines** — dagelijkse prioriteiten, wekelijkse samenvatting (markdown, geen HTML), risico-log check. Plus Athena-audit.
- **Token-efficiënt** — compacte logs, batching, geen HTML-slurpers, rotatie na 50 entries.
- **Repo-trigger** — “check de repo en doe de update”.
- **VM-persistent geheugen** — één wet: `VM-GEHEUGEN.md`.
- **Athena** — auditor-profiel + heartbeat. Geen audit in 8 dagen = protocol-falen.

## Wat erin zit
- `echo-profile.md` — wie Echo is (rol). Niet het runbook.
- `echo-routines.md` — rooster: trigger, input, output, done, fail.
- `athena-profile.md` — auditor. Echo speelt deze rol tenzij je een aparte Coach-bot zet.
- `searchy-profile.md` — researcher. Taken uit session-memory.
- `taakbrief-template.md` — verplicht bij elke delegatie.
- `decisions-log-template.md` — logformaat + voorbeeld goed/slecht.
- `VM-GEHEUGEN.md` — enige bron van waarheid voor pull/werk/kaart/push en rotatie.
- `onboarding-interview.md` — vijf vragen, daarna GitHub-account en connector.
- `state/` — persistent geheugen.

## Snel starten
1. Nieuwe Grok Bot: plak `echo-profile.md` als system prompt.
2. Tweede bot: plak `searchy-profile.md`.
3. Gebruik `echo-routines.md` als routines-bestand.
4. Koppel Firecrawl of Exa aan Searchy (gratis tier volstaat).
5. **Vereist:** GitHub-account (https://github.com/signup) én GitHub-connector in Grok Bot.
6. Eerste prompt (pas de clone-URL aan als je een fork gebruikt):

   Je bent Echo, mijn chief of staff. Clone deze repo naar /workspace/<repo-naam> als die map er nog niet is, en doe een pull. Lees VM-GEHEUGEN.md en onboarding-interview.md. Voer het onboarding-interview uit — één vraag per keer. Wacht op mijn antwoorden. Check GitHub-account en connector. Geen push en geen routines vóór onboarding klaar is.

7. Bevestig eenmaal dat Athena mag auditen. Daarna: heartbeat op zondag. Geen audit in 8 dagen = rood.

## Licentie
MIT — gratis te gebruiken en aan te passen.
