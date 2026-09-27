# Coach-audit — Athena

Append-only log. Athena (Coach) schrijft hier elke week de bevindingen van de protocol-audit, en elke twee weken de profiel-review. Nooit geschiedenis wissen.

## Formaat per opzet-check (eenmalig, vóór de eerste run)

```
## YYYY-MM-DD — Opzet-check
- Uitvoerder: [Athena-bot / Echo als noodoplossing, blinde vlek gemeld]
- Aanwezig: […]
- Ontbreekt: [… — blokkerend: ja/nee]
- Niet geverifieerd: [… — gemeld door Echo, niet geverifieerd]
- Lijst schoon: [ja / nee, wacht op ja van eigenaar]
```

## Formaat per audit-entry

```
## YYYY-MM-DD — Week N
- Protocol-naleving: [ja / deels / nee] — [korte toelichting]
- Schema-discipline: [ja / deels / nee] — [korte toelichting]
- Kill switch: [nooit vuurgegaan / vuurgegaan, correct / vuurgegaan, fout]
- Bevindingen: [wat opviel, patronen, zwakke plekken]
- Actie: [niets / voorstel X, wacht op ja van eigenaar]
```

## Formaat per profiel-review-entry (elke twee weken)

```
## YYYY-MM-DD — Profiel-review (na week N en N+1)
- Patronen: [terugkerende zwaktes over de twee audits]
- Voorstel 1: [profiel] — [welke regel] — [waarom] — [verwacht effect]
- Voorstel 2: [optioneel]
- Status: [wacht op ja van eigenaar / goedgekeurd op datum / afgewezen]
```

---

## 2026-09-24 — Opzet-check
- Uitvoerder: Athena-bot
- Aanwezig: [Echo-bot; Athena-bot; repo `/workspace/echo-chief-of-staff` (origin WeSs1982/echo-chief-of-staff); GitHub-connector; state-templates (session-memory, decisions-log, risk-log, rejected-sources, locks, session-card, coach-audit)]
- Ontbreekt: [Argus-bot (aparte bot met argus-profile.md) — blokkerend: ja; Onboarding vastgelegd (doel in session-memory → Actuele projecten + Onboarding in decisions-log) — blokkerend: ja]
- Niet geverifieerd: [of Echo 0 routines heeft (protocol eist geen routines 1–6 vóór schone check) — gemeld door Echo, niet geverifieerd; of Research-bot bedoeld was als Argus — gemeld, niet geverifieerd (profiel is Spice Up, niet argus-profile.md)]
- Lijst schoon: nee, wacht op ja van eigenaar

## 2026-09-24 — Opzet-check correctie (via WeSs)
- Uitvoerder: Athena-bot
- Correctie: Echo/Argus/onboarding-stack = NVT (bewust niet). Wess wilde alleen Athena. Echo wordt verwijderd. Argus komt er niet. Research = Spice Up/Firecrawl, geen Argus. Geen onboarding-interview. Items Argus + onboarding uit opzet-check 2026-09-24 = afgewezen, niet open.
- Scope Athena: audits alleen op vraag van WeSs; rapportage aan WeSs; één zwakke plek + één voorstel; geen productwerk.
- Lijst schoon: NVT (stack niet van toepassing)
- Status: idle tot WeSs om audit vraagt

## 2026-09-24 — Scope-update (via WeSs)
- Project: Spice Up (Discord + bot Spice + website + Research/Firecrawl)
- Rapportage: WeSs → Wess (Echo NVT)
- Echo/Argus/onboarding: blijft NVT
- Checklist: Argus/Echo-items → Spice Up-equivalenten (Spice-bot stabiel? Research-brief gelogd? Discord/rechten intact?)
- Methodiek: ongewijzigd (één zwak + één voorstel; geen pipeline; zondag heartbeat; ja via WeSs)
- Status: idle tot audit-vraag of zondag

## 2026-09-24 — Audit Spice Up (op vraag van WeSs)
- Protocol-naleving: deels — geen session-cards/decisions-log voor Spice Up-runs; wel harde regels en Argus-output met bronnen
- Schema-discipline: NVT (eerste audit)
- Kill switch: nooit vuurgegaan
- Bevindingen: zwakste plek = auto-rol Lid onbewezen. Log `/tmp/spiceup-bot.log` toont 2x login (22:01, 22:17), nul "Granted Lid" en nul fouten. README-invite (permissions 84992) mist Manage Roles, terwijl bot.py die nodig heeft. Bot draait als losse `python main.py` zonder herstart-supervisor.
- Actie: voorstel testjoin met tweede account vóór soft live 25-09 + log checken; wacht op ja van Wess via WeSs

## 2026-09-24 — Audit Spice-bot + Discord (op vraag van WeSs, 23:12)
- Protocol-naleving: deels — bot draait en tests groen; auto-Lid nooit bewezen (0x Granted); Discord-check geblokkeerd (browser niet ingelogd); live test niet gedaan (geen direct ja van Wess)
- Schema-discipline: NVT
- Kill switch: nooit vuurgegaan
- Bevindingen: keepalive herstart python (log 22:49/22:50) maar niets start keepalive na reboot; invite 84992 mist Manage Roles; keepalive logt altijd exitcode 0; zonder regelscherm geeft on_member_join Lid meteen
- Actie: voorstel rechten + rolvolgorde checken en testjoin vóór soft live; wacht op ja van Wess via WeSs

## 2026-09-27 — Week 1 (zondag-heartbeat, Spice Up)
- Protocol-naleving: nee — decisions-log, risk-log, rejected-sources en session-card hebben 0 ingevulde rijen (alleen templaterij "—"), terwijl er deze week wel beslissingen/incidenten waren: bot 25-09 04:57–08:13 offline (log: 11x "DISCORD_TOKEN ontbreekt", code 1), keepalive-fix (`code=$?`, bestand), persona.txt + knowledge.md gewijzigd 26-09 13:43, 7x handmatige herstart (code 143, 25-09 en 26-09), ensure-running elk uur (volgens WeSs). Geen enkele staat gelogd met reden + uitkomst.
- Schema-discipline: deels — coach-audit-entries volgen het vaste formaat; de overige logs zijn leeg, dus niet te toetsen.
- Kill switch: nooit vuurgegaan — geen entry in risk-log; bot-log toont geen limiet-, quota- of stopmeldingen (0 ERROR/Traceback).
- Geheugenkwaliteit: nee — session-memory.md is nog het Echo-template ("Laatste update: —", Athena/Argus "—"); geen Spice Up-projecten of lessen vastgelegd. Research-pool niet leeg (argus-site-review.md bijgewerkt 27-09 08:45).
- Bewezen deze week: auto-rol werkt — 3x "Granted Member" (25-09 11:45, 26-09 01:20, 26-09 11:14), 0x Forbidden of "not found". Bot online sinds 26-09 13:44, keepalive-PID 72675 leeft sinds 25-09 08:14, laatste gateway RESUMED 27-09 08:47. Keepalive logt nu echte exitcodes (1, 143).
- Niet geverifieerd: Manage Roles, rolpositie en regelscherm (gemeld door WeSs via bot-API); ensure-running elk uur via WeSs-routine (geen spoor in log); log noemt rol "Member", config-standaard is "Lid" (env-override vermoed); testjoin en live test door Wess.
- Zwakste plek: de state-logs zijn leeg; alleen de bot-log bewijst wat er gebeurde. De 3 uur uitval op soft-live-dag 25-09 staat nergens met oorzaak en actie. Tweede audit op rij met dit patroon (24-09 "deels").
- Actie: voorstel — WeSs zet de 4 gebeurtenissen van deze week (uitval 25-09, keepalive-fix, ensure-running-routine, persona/knowledge-wijziging 26-09) als rij in decisions-log/risk-log en logt daarna per Spice Up-wijziging één rij (datum, beslissing, reden, uitkomst). Wacht op ja van Wess via WeSs.
- Compactie: niet nodig (oudste entry 2026-09-24, niets ouder dan 4 weken).
- Rode vlag: ja (protocol niet gevolgd), gemeld aan WeSs.

## 2026-09-27 — Profiel-review (na audits 24-09 en 27-09, Spice Up)
- Gelezen: laatste twee audits, decisions-log (10 rijen), risk-log (3 rijen), session-memory (nog leeg Echo-template). Profielen: echo/argus/athena-profile.md (repo), Spice persona.txt, profile.json van WeSs, Argus en Spice Werving. searchy-profile: niet aanwezig. echo-profile: NVT (Echo bestaat niet meer).
- Patronen: (1) Spice Up-wijzigingen worden pas gelogd nadat Athena erom vraagt: 3 audits op rij (24-09 deels, 24-09 23:12 deels, 27-09 nee). Pas na de rode vlag zijn 8 + 3 rijen bijgeschreven (commit 229b65a). Op 27-09 09:06 is de logregel ingevoerd, maar alleen als rij in decisions-log, niet in een profiel. (2) Claim vóór bewijs: knowledge.md beloofde auto-rol Member voordat er ook maar één keer "Granted" in het log stond (bewezen pas 27-09).
- Voorstel 1: WeSs-profiel (Spice Up-deel) — regel toevoegen: "Na elke Spice Up-wijziging één rij in state/decisions-log.md (datum, beslissing, reden, uitkomst); uitval of fout ook in risk-log.md; zet niets als werkend in persona/knowledge zonder logbewijs." — Waarom: de regel bestaat nu alleen in een logrij en in het geheugen van WeSs, en valt weg als dat geheugen wordt samengevat. — Verwacht effect: de audit van 04-10 kan protocol-naleving "ja" geven op bewijs, zonder dat ik erom hoef te vragen. Niet geverifieerd: of de volledige WeSs-instructies (private repo jarvis) deze regel al bevatten.
- Voorstel 2: Spice Werving-profiel — de regel "#server-info bestaat nog niet op de Discord… die zin weglaten" is verouderd. Volgens decisions-log staat #server-info sinds 26-09 live. — Waarom: welkomstmails laten nu onnodig de verwijzing naar #server-info (wachtwoord) weg. — Verwacht effect: nieuwe leden vinden direct hoe ze op de server komen.
- Status: wacht op ja van eigenaar (via WeSs). Niets gewijzigd.
