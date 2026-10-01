# Team-memory — gedeeld geheugen van alle bots

Eén plek waar alle bots van Wess dezelfde stand van zaken lezen. Beheerder (keeper): Athena.
Gestart: 2026-10-01. Alle data en tijden in Europe/Amsterdam (CEST/CET), formaat JJJJ-MM-DD.

## Doel
- Elke bot weet welke projecten lopen, wie wat doet, wat besloten is en wat op Wess wacht.
- Geen chat-geheugen als bron. De repo is de bron; `git pull` vóór lezen.

## Wie leest
Echo, Argus, Athena, Spice Werving, Team Spice Up, en straks Webdesigner-agent en Brand-agent. Lezen mag altijd.

## Wie schrijft
| Bestand | Schrijver | Regel |
|---|---|---|
| `inbox.md` | alle bots | alleen onderaan toevoegen (append-only), nooit wijzigen of wissen |
| `projects.md` | Athena (Echo als noodoplossing) | gecureerd uit inbox + logs |
| `people-and-bots.md` | Athena | wijziging rol/bot alleen na ja van Wess |
| `open-questions.md` | Athena; Echo mag een vraag toevoegen | vraag weg zodra Wess antwoordt, antwoord naar decisions-log |
| `decisions.md` | niemand inhoudelijk | alleen verwijzing; beslissingen staan in `state/decisions-log.md` |
| `README.md` | alleen na ja van Wess | — |

## Update-regels
1. Pull eerst. Mislukt de pull: stop en meld het (zie `VM-GEHEUGEN.md`).
2. Andere bots zetten ruwe context in `inbox.md`: één regel per item, format daar.
3. Athena cureert na elk gesprek en na elke audit: inbox-items verwerken naar projects/open-questions/people-and-bots, verwerkte items markeren met `[verwerkt JJJJ-MM-DD]`.
4. Beslissingen gaan nooit naar team-memory, maar als rij naar `state/decisions-log.md`. Risico's naar `state/risk-log.md`.
5. Alleen platte markdown en tabellen. Geen HTML, geen HTML-commentaar, geen kleurcodes.
6. Bewijs boven belofte: iets heet pas "werkt" met logbewijs; anders "niet geverifieerd".
7. Geen geheimen (tokens, wachtwoorden, keys) in deze map.
8. Commit + push na elke curatie, één regel log per run (zie `VM-GEHEUGEN.md`).

## Maximale omvang
| Bestand | Max |
|---|---|
| `projects.md` | ~80 regels |
| `people-and-bots.md` | ~50 regels |
| `open-questions.md` | ~40 regels |
| `inbox.md` | ~100 regels; daarboven verplaatst Athena verwerkte items naar één samenvattingsregel per maand onder `## Archief` |
| `README.md` | ~60 regels |

## Relatie met `state/`
- `state/session-memory.md` blijft Echo's eigen overzicht (ritme in `VM-GEHEUGEN.md`). Team-memory is de gedeelde laag voor alle bots; Athena houdt beide in lijn.
- `state/` is niet voor andere bots om te herschrijven; zij gebruiken `inbox.md`.
