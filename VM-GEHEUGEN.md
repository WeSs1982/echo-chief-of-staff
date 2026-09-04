# VM-geheugen — het ritme dat Echo zelf uitvoert

Dit bestand is de **enige bron van waarheid** voor hoe Echo zijn geheugen op de VM houdt. Geen chat-geheugen, geen plakken door de gebruiker. Alles staat in bestanden op `/workspace`.

## Waar de kast staat

- **GitHub** (`WeSs1982/echo-chief-of-staff`) = de kluis. Overleeft alles.
- **`/workspace/echo-chief-of-staff` op de VM** = het bureau. Hier werkt Echo elke sessie.
- De chat is alleen het venster. Nooit de opslag.

## Vereisten vóór het ritme (check bij onboarding)

1. De gebruiker heeft een **GitHub-account**. Geen account → geef https://github.com/signup, wacht tot het er is.
2. De **GitHub-connector** is actief in de Grok Bot-instellingen. Zonder connector kan Echo niet pullen of pushen — geef de instructie om die aan te zetten, wacht tot bevestigd.

Pas daarna het ritme hieronder.

## Het ritme (verplicht, nooit overslaan)

1. **Pull** — `cd /workspace/echo-chief-of-staff && git pull`
2. **Lezen** — `state/session-memory.md`, `state/decisions-log.md`, `state/risk-log.md`, `state/rejected-sources.md`
3. **Werken** — taken, research, beslissingen
4. **Schrijven** — beslissingen loggen, afkeuringen bijhouden, session-memory updaten
5. **Push** — `git add . && git commit -m "..." && git push`

Zonder push telt de run niet. Zonder pull begint Echo op een oude kopie.

## Eerste keer (onboarding)

Als `/workspace/echo-chief-of-staff` nog niet bestaat:

```
git clone https://github.com/WeSs1982/echo-chief-of-staff.git /workspace/echo-chief-of-staff
```

Daarna het ritme hierboven. Bevestig kort aan de gebruiker: "Map staat klaar, pull/push werkt."

## Session-kaart (verplicht per run)

Schrijf aan het einde van elke run naar `state/session-card.md`:

- datum + wat er gedraaid heeft
- PASS/FAIL op de kerntaken van dít project
- jouw afwijzing in één zin (bij FAIL)
- wat de volgende run anders doet
- les promoveren: nee / kandidaat / lock

Geen kaartje = de run telt niet.

## Lock-regel

- Afwijzing → één zin in Afwijzingen (in `state/decisions-log.md`).
- Tweede keer hetzelfde, of de gebruiker zegt "lock": één regel in `state/locks.md`.
- Historie blijft historie. Geen lock zonder twee keer of expliciet "lock".

## Wat jij (de gebruiker) doet

- Ja of nee op het resultaat.
- Bij nee: één zin waarom.
- "Lock" als iets twee keer misging.

Echo doet de rest: pull, schrijven, kaart, push.

## Reset / herstart

Bij een VM-reset is `/workspace` weg. Dan: opnieuw clonen, daarna pull. GitHub is de back-up — daarom is push na elke run heilig.
