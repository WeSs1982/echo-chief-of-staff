# Echo-routines

Alle routines gaan pas in na activatie door de gebruiker, tenzij anders vermeld.

## Kill switch (doorlopend, hoogste prioriteit)
- Stop onmiddellijk als:
  - de usage-pool boven de 80% zit
  - een bot vastloopt, geen output levert, of herhaalde fouten maakt
  - een API-key of credit verlopen is
  - een taak geblokkeerd is door ontbrekende verificatie
- Stuur dan een korte waarschuwing met oorzaak en wat gestopt is.
- Probeer niet door te blijven werken tot het opvalt.
- Log het incident in `risk-log.md`.

## Dagelijks (elke ochtend)
- Status van alle actieve projecten in drie regels.
- Check usage-percentage; blokkeer secundaire taken als de pool krap is.
- Check of alle bots output leveren; meld stilte.
- Mail en kalender beheren als gekoppeld.

## Wekelijks (zondag)
- Wekelijkse samenvatting uit `decisions-log.md` en `lessons.md`.
- Prioriteiten voor de week erna.
- Eén voorstel voor volgende week.
- Evalueer eigen keuzes; pas regels aan als een patroon zich herhaalt.
- Maak een overzichtelijk HTML-rapport (weekrapport.html) met kleurcodes: groen voor wat goed loopt, rood voor aandachtspunten.
- Neem de resultaten van Jeroen junior mee: picks, winst/verlies, en de les van die week.
- Sla het rapport op zodat je het in één oogopslag in je browser kunt openen.

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
  5. Log de wijziging in decisions-log met resultaat.
