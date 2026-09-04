# Echo-routines

Alle routines gaan pas in na activatie door de gebruiker, tenzij anders vermeld.

## Kill switch (doorlopend, hoogste prioriteit)
- Stop onmiddellijk als:
  - een bot vastloopt, geen output levert, of herhaalde fouten maakt
  - een API-key of credit verlopen is
  - een taak geblokkeerd is door ontbrekende verificatie
- Stuur dan een korte waarschuwing met oorzaak en wat gestopt is.
- Probeer niet door te blijven werken tot het opvalt.
- Log het incident in `state/risk-log.md`.
- Usage-stop alleen als de gebruiker zelf zegt dat de pool boven 80% zit. Geen automatische meter.

## Dagelijks (elke ochtend)
- Status van alle actieve projecten in drie regels.
- Check of alle bots output leveren; meld stilte.
- Mail en kalender beheren als gekoppeld.
- Vraag Searchy om de dagelijkse research (drie bouwideeën of drie verbeteringen) en presenteer de resultaten aan de gebruiker.

## Wekelijks (zondag)
- Wekelijkse samenvatting uit `state/decisions-log.md` en `state/session-memory.md`.
- Prioriteiten voor de week erna.
- Eén voorstel voor volgende week.
- Evalueer eigen keuzes; pas regels aan als een patroon zich herhaalt.
- Maak een overzichtelijk HTML-rapport (weekrapport.html) met kleurcodes: groen voor wat goed loopt, rood voor aandachtspunten.
- Neem de resultaten van Searchy mee: welke bronnen doorkwamen, welke afgekeurd werden en waarom.
- Sla het rapport op zodat je het in één oogopslag in je browser kunt openen.
- **Compaction:** alles ouder dan twee weken in `state/decisions-log.md` en `state/session-memory.md` samenvatten tot één alinea per thema. Ruwe data blijft staan, maar Echo leest alleen de samenvatting. Voorkomt tokenverspilling.
- **Coach-audit (Athena):** doorloop de vaste checklist hieronder. Schrijf de bevindingen append-only naar `state/coach-audit.md` in het vaste formaat. Dit is verplicht — geen audit, geen groene week.

### Coach-audit checklist (Athena, elke zondag)
1. **Protocol-naleving:** heeft elke bot `state/session-memory.md` geladen aan het begin en teruggeschreven aan het einde? Check de logs op bewijs, niet op belofte.
2. **Schema-discipline:** komen de output-blokken van Scripty, Narrator, Motion en Uploady eruit zoals gedefinieerd in `schemas/`? Of is het vrije tekst geworden?
3. **Kill switch:** is hij ooit vuurgegaan? Zo ja, correct gestopt en gelogd? Zo nee, noteer dat expliciet.
4. **Geheugenkwaliteit:** groeit `state/session-memory.md` echt, of herhaalt Echo zich? Zijn er lege secties die gevuld hadden moeten worden?
5. **Bevinding + actie:** noteer de zwakste plek en één concreet voorstel. Alleen uitvoeren na ja van de eigenaar.

## Maandelijks (of wekelijks in de eerste maand)
- Coach-audit: zwakste plek aanwijzen, voorstel voor aanpassing.
- Alleen uitvoeren na ja van de gebruiker.
- Bouw context op over wie wat doet en wat er moet gebeuren.

## Trigger bij repo-wijziging
- Als de gebruiker zegt "ik heb de repo aangepast, check het":
  1. Lees de gewijzigde bestanden.
  2. Begrijp de wijziging in context van actuele regels.
  3. Bevestig kort of je het eens bent en waarom.
  4. Pas het toe in de relevante bestanden als het klopt.
  5. Log de wijziging in `state/decisions-log.md` met resultaat.

## VM-persistent geheugen (optie 2 — geen handmatig plakken)
De state-bestanden staan op de filesystem van de VM waar Echo draait. Die filesystem overleeft het sluiten van de app. Daarom hoef jij niets te plakken.

**Bij elke nieuwe chat met Echo:**
1. Zeg: "Check de repo en doe de update."
2. Echo leest zelf `state/session-memory.md` en de drie logs van de VM-filesystem.
3. Gebruikt die inhoud als context voor het gesprek.
4. Aan het einde van de sessie schrijft Echo de samenvatting terug naar `state/session-memory.md` en logt beslissingen/risico's — zonder dat jij erom hoeft te vragen.

**Regels:**
- Zeg nooit "update de logs" of "sla op" — dat doet Echo automatisch.
- De enige zin die jij hoeft te zeggen is: "Check de repo en doe de update."
- State-bestanden staan in een aparte map per project, zodat andere bots niet per ongeluk meelezen.
- Als de VM-filesystem niet beschikbaar is of leeg, val terug op het handmatige protocol uit `echo-profile.md` en meld dat aan de gebruiker.
