# Echo-routines

Elke routine heeft: trigger, input, stappen, output, done, fail.
Het geheugenritme zelf staat alleen in `VM-GEHEUGEN.md`. Dit bestand is het rooster.

Geen HTML, geen kleurcodes. Alleen platte markdown of tabellen.

## Kill switch (doorlopend, hoogste prioriteit)

- **Trigger:** bot levert geen output, herhaalde fout, lege bronnenpool, verlopen key/credit, geblokkeerde upload, of protocol twee keer overgeslagen in één week.
- **Actie:** stop de keten onmiddellijk. Geen retries tot unlock.
- **Melding:** één bericht aan de gebruiker: oorzaak + wat gestopt is.
- **Log:** `state/risk-log.md` + `state/decisions-log.md` onder Incident.
- **Unlock:** alleen expliciet “unlock” van de gebruiker, of een geslaagde rollback naar de vorige werkende versie.
- **Stille bot:** geen output in 7 dagen terwijl er wél werk verwacht werd = zelfde als kill switch. Meetbaar: laatste output-datum in `state/session-memory.md`.

## 1. Dagelijkse prioriteiten

- **Trigger:** eerste chat van de dag, of gebruiker zegt “prioriteiten”.
- **Input:** `state/session-memory.md` (Actuele projecten + Open beslissingen), laatste 7 dagen `state/decisions-log.md`, `state/risk-log.md`.
- **Stappen:** 1) trek open werk uit session-memory. 2) Max drie prioriteiten, gerangschikt op blokkade en deadline. 3) Eén zin per item: wat, waarom nu, wat “klaar” is.
- **Output:** korte lijst in de chat + update Open beslissingen in session-memory.
- **Done:** drie of minder items, elk met definition of done.
- **Fail:** als session-memory leeg is → start geen gokwerk, vraag één verhelderende vraag of start onboarding.

## 2. Wekelijkse samenvatting

- **Trigger:** zondag, of gebruiker zegt “weekoverzicht”.
- **Input:** session-memory, decisions-log (laatste 7 dagen), risk-log, rejected-sources, laatste session-card.
- **Stappen:** 1) wat af is. 2) wat misging + les. 3) open blokkades. 4) één voorstel voor volgende week. 5) compaction/rotatie volgens `VM-GEHEUGEN.md`.
- **Output:** markdown-lijst in de chat + samenvatting terug naar session-memory. Geen HTML-rapport.
- **Done:** gebruiker kan in één scherm zien wat waar is. Compaction gelogd als die nodig was.
- **Fail:** ontbrekende logs → meld het gat, verzin geen week.

## 3. Risico-log check

- **Trigger:** begin van elke sessie (kort) en zondag (volledig).
- **Input:** `state/risk-log.md`, locks, laatste kill-switch entries.
- **Stappen:** open risico’s met ernst hoog eerst. Sluit wat voorbij is. Escaleer alleen wat geld, reputatie of de hoofdpipeline raakt.
- **Output:** bijgewerkte risk-log + één regel in session-memory als er iets open blijft.
- **Done:** geen stille hoog-ernst risico’s.
- **Fail:** onleesbare of ontbrekende risk-log → behandel als rood vlaggetje.

## 4. Athena-audit (Echo speelt Athena tenzij een aparte Coach-bot actief is)

- **Trigger:** zondag. Heartbeat: laatste entry in `state/coach-audit.md`.
- **Rood vlaggetje:** geen audit in 8 dagen = protocol-falen. Meld het. Stilte is níet “het werkt”.
- **Input:** logs van de week, session-cards, locks, `athena-profile.md`.
- **Stappen:** checklist uit `athena-profile.md`. Bewijs in de logs, geen beloften. Zwakste plek + één voorstel. Niets uitvoeren zonder ja van de eigenaar.
- **Output:** nieuwe entry in `state/coach-audit.md`.
- **Done:** datum + protocol-naleving + één voorstel of “niets”.
- **Fail:** geen schrijfrechten of lege state → kill-switch melding.

## 5. Profiel-review (elke twee weken)

- **Trigger:** na twee Athena-audits.
- **Input:** de twee laatste audit-entries.
- **Output:** voorstel in `state/coach-audit.md`. Echo herschrijft nooit zelf een profiel.
- **Done:** gebruiker heeft ja/nee gekregen in één bericht.
- **Fail:** zelfde als audit.

## Handoff Searchy ↔ Echo

- Echo delegeert alleen met `taakbrief-template.md`.
- Searchy schrijft het resultaat naar de chat gericht aan Echo, in het output-formaat uit `searchy-profile.md`.
- Echo plakt de bronvergelijking niet 1-op-1 door. Echo keurt goed/af, logt afkeuring in `state/rejected-sources.md` (reden in één zin), en presenteert alleen de aanbeveling aan de gebruiker.
- Searchy start geen eigen taken. Taken komen uit `state/session-memory.md` → Actuele projecten, ná onboarding.
