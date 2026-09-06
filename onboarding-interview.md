# Onboarding-interview

Voer dit uit bij de eerste sessie met een nieuwe gebruiker, of zodra de gebruiker vraagt om ingesteld te worden. Eén vraag per keer, hooguit één follow-up per vraag.
Antwoorden gaan naar `state/decisions-log.md` onder "Onboarding". Het doel van de gebruiker gaat óók naar `state/session-memory.md` → Actuele projecten; daar haalt Argus zijn taken vandaan.
Vraag niet om mail- of agenda-toegang. Echo werkt zonder. Loopt een taak erop vast, dan vraagt hij er één keer om, met reden, en herhaalt dat niet.

## Spoorkeuze (allereerste vraag)
"Snelspoor of beginnerspoor? Snelspoor is vijf vragen zonder uitleg. Beginnerspoor is dezelfde vijf, met per vraag één zin waarom ik het vraag, plus maximaal drie optionele vragen."

## De vijf kernvragen
1. **Doel** — Waar wil je Echo voor inzetten?
   *(beginnerspoor: hieruit volgt wat Argus onderzoekt en wat bovenaan je prioriteitenlijst komt.)*
2. **Tijd** — Hoeveel uur per week heb je om te controleren en goed te keuren, en op welke momenten?
   *(bepaalt hoe vaak Echo je stoort en hoe lang hij op een ja mag wachten.)*
3. **Autonomie** — Wat mag Echo zelf beslissen, en waar houd je altijd de eindbeslissing?
   *(dit wordt de escalatiegrens; zonder dit vraagt Echo te veel of te weinig.)*
4. **Overzicht** — Wat wil je wekelijks terugzien: cijfers, status, of alleen de uitzonderingen?
   *(bepaalt de vorm van de wekelijkse samenvatting en wanneer je een melding krijgt.)*
5. **Tools en connectors** — Welke tools en connectors mag Echo gebruiken?
   *(zonder git-connector is er geen geheugen; de rest is optioneel.)*

## Drie optionele vragen (alleen beginnerspoor)
6. **Frustratie** — Wat is nu je grootste bottleneck?
7. **Tijdslot** — Welke dag en welk tijdstip past voor input en goedkeuringen?
8. **Automatiseren** — Wat wilde je al langer automatiseren maar kwam er nooit van?

## Namen (optioneel, laatste vraag)
"Standaard heten de bots Echo, Argus en Athena. Wil je ze anders noemen?" Geen antwoord = standaard.
Gekozen namen komen alleen in `state/session-memory.md` en in de aanspreekvorm. Hernoem nooit bestanden of verwijzingen in bestanden op basis van een gekozen naam.

## Terugkoppeling (verplicht, max vijf regels)
Vat samen: wat Echo denkt dat het doel is, wat hij zelfstandig mag, wat hij altijd vraagt. Wacht op bevestiging voor je verder gaat.

## Team voorstellen (nog niet aanmaken)
"Op basis hiervan stel ik Argus voor als researcher en Athena als auditor — wil je er iets bij?" Wacht op ja. Maak het team pas daarna aan.

## Verwachting (max vier regels, geen ja/nee-vraag)
Het team staat. Echo kent de gebruiker nog niet. De komende maand is inwerken: echte taken, afkeuren met een reden, kijken of het de volgende keer anders gaat.

## Git-ritme activeren
1. Vraag of de gebruiker een account heeft bij een git-remote naar keuze (opties: `VM-GEHEUGEN.md`). Bij nee: eerst aanmaken, wacht tot bevestigd.
2. Vraag of de git-connector actief is in de Grok Bot-instellingen. Bij nee: eerst activeren — zonder connector kan Echo niet pullen of pushen.
3. Clone de repo naar `/workspace/<repo-naam>` als die map er nog niet is. Bevestig: "Map staat klaar, pull/push werkt."

## Opzet-check door Athena (na teamaanmaak, vóór de eerste run)
- Athena vergelijkt wat Echo als doel heeft vastgelegd met wat er staat: welke bots bestaan, welke routines zijn aangemaakt, welke connectors zijn gekoppeld.
- Output: één lijst "aanwezig" / "ontbreekt", en per ontbrekend punt of het blokkerend is voor de eerste run.
- Athena past niets zelf aan. Ze toont het verschil en vraagt de eigenaar één keer om ja. Echo voert uit, Athena checkt opnieuw tot de lijst schoon is.
- Wat Athena niet zelf kan verifiëren, markeert ze als "gemeld door Echo, niet geverifieerd".
- Het resultaat is de eerste entry in `state/coach-audit.md`.

## Eerste run (afsluiting)
- Echo geeft Argus één kleine echte opzoekvraag via `taakbrief-template.md`.
- De gebruiker keurt één bron af met een reden.
- Zo ziet die in tien minuten een taakbrief ontstaan, een regel in `state/rejected-sources.md`, een regel in `state/decisions-log.md` en een session-card.
- Echo sluit af met de vraag om de eerste echte taak. De eerste wekelijkse Athena-audit komt de zondag erna.
