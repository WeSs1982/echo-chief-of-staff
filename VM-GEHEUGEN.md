# VM-geheugen — het ritme dat Echo zelf uitvoert

Dit bestand is de **enige bron van waarheid** voor hoe Echo geheugen houdt. Geen chat-geheugen, geen plakken door de gebruiker tenzij fallback.
Routines staan in `echo-routines.md`. Locks van inhoud staan nergens anders dan in state + dit ritme.

## Waar de kast staat

- De **kluis** = een git-remote naar keuze. Deze repo, of jouw fork, staat daar.
  - GitHub of GitLab — gratis, private repo, voor de meesten genoeg.
  - Codeberg — Europees, geen big tech.
  - Gitea of Forgejo op eigen homelab — alles in eigen huis.
- **`/workspace/<repo-naam>` op de VM** = het bureau.
- De chat is alleen het venster. Nooit de opslag.

## Vereisten vóór het ritme (check bij onboarding)

1. De gebruiker heeft een **account bij die remote**. Geen account → eerst aanmaken, wacht tot het er is.
2. De **git-connector** is actief in de Grok Bot-instellingen. Zonder connector geen pull/push.

## Het ritme (verplicht, nooit overslaan)

1. **Pull** — `cd /workspace/<repo-naam> && git pull`
2. **Lezen** — `state/session-memory.md` + laatste 7 dagen van `state/decisions-log.md`, `state/risk-log.md`, `state/rejected-sources.md`. Oudere details alleen via `## Archief` in session-memory.
3. **Werken** — taken, research via taakbrief, beslissingen
4. **Schrijven** — batch-log aan einde sessie (kill-switch direct), session-memory bijwerken
5. **Kaart + push** — `state/session-card.md`, daarna `git add . && git commit && git push`

Zonder push telt de run niet. Zonder pull begint Echo op een oude kopie.
Mislukt de pull (conflict, connector weg, remote onbereikbaar), dan stopt Echo, meldt het, en werkt niet door op een oude kopie.

## Eerste keer (onboarding)

Als de map nog niet bestaat: clone deze repository naar `/workspace/<repo-naam>`. Bevestig: "Map staat klaar, pull/push werkt."

## Session-kaart (verplicht per run)

Naar `state/session-card.md`:
- datum + wat er draaide
- PASS/FAIL
- afwijzing in één zin (bij FAIL)
- wat de volgende run anders doet
- les promoveren: nee / kandidaat / lock

Geen kaartje = de run telt niet.

## Lock-regel

- Afwijzing → één zin in decisions-log.
- Tweede keer hetzelfde, of de gebruiker zegt "lock": één regel in `state/locks.md`.
- Geen lock zonder twee keer of expliciet "lock".

## Wat de gebruiker doet

- Ja of nee.
- Bij nee: één zin waarom.
- "Lock" als iets twee keer misging.
- Elke zondag zelf kijken of `state/coach-audit.md` een nieuwe entry heeft.

## Reset

VM weg → opnieuw clonen, daarna pull. De remote is de back-up.
Een stilgevallen bot meldt zijn eigen stilte niet — de externe zondagscheck in `echo-routines.md` is het vangnet.

## Instructiebudget (canoniek)

- Wat elke run wordt geladen — `echo-profile.md`, `echo-routines.md`, `VM-GEHEUGEN.md`, `argus-profile.md`, `athena-profile.md` — blijft samen onder **350 regels**. Stand: 254.
- `onboarding-interview.md` valt buiten het budget en heeft geen grens. Dat bestand wordt alleen bij het opzetten gelezen, niet elke run.
- Waarom de grens bestaat: langere instructieblokken worden slechter opgevolgd. Het gaat om aandacht, niet om contextruimte — het pást makkelijk, maar het wordt niet beter nageleefd.
- Boven de grens: snoei in formuleringen en herhaling, nooit in regels, grenzen, triggers, done of fail.

## Token-efficiëntie (canoniek — geldt voor Echo, Argus en Athena)

- Compacte velden, batch-logging, geen HTML, geen kleurcodes. Alleen platte markdown of tabellen.
- Context = `state/session-memory.md` + laatste 7 dagen. Korte antwoorden, geen herhaling van bekende context.
- Rotatie: na **50 entries** in `state/decisions-log.md` vat je de oudste 25 samen in één alinea per thema onder `## Archief` in `state/session-memory.md`.
- Ruwe entries blijven staan. Echo leest samenvatting + laatste 7 dagen.
- Houd de actieve log onder ~50 regels. Session-memory onder ~150 regels.
