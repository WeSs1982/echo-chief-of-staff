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

## 2026-09-30 — Audit Spice Up (op vraag van WeSs)
- Protocol-naleving: nee — logregel (27-09 09:06) niet nageleefd: geen rij voor bot-uitval na herstart computer 27-09 (~15:32–15:54), 403 rollen geven (decisions-log:24) niet in risk-log, welkomstmails 28-09 (2x) niet gelogd, sitewijzigingen na 27-09 (FAQ, privacy, PvE-blok, Discord-link weg, "2 spots") zonder rij, aanmelding gelabeld Afgehandeld zonder vervolgmail of rij (correctie 30-09: Wess heeft deze persoon zelf handmatig gemaild; zie decisions-log). session-memory/session-card nog leeg template.
- Schema-discipline: deels — 4 rijen staan op "open" terwijl ze af of achterhaald zijn (decisions r.8, 15, 17, 25); risk-log r.11–13 zonder statuskolom, oorzaak in "Ernst".
- Kill switch: nooit vuurgegaan — 0 ERROR/Traceback/Forbidden; 1x LLM 503 (27-09 18:34), fallback gaf 200.
- Bewezen: bot draait (keepalive PID 12526 sinds 27-09 15:54), 37x RESUMED, laatste 30-09 07:42; 44/44 tests groen; 1x Granted Member (28-09 11:11); 6 aanmeldingen (5 echt), alle gelabeld; invite w9gxuYYBxz geldig; site 200, HTTPS, ~0,37 s.
- Problemen: HOOG geen autostart na herstart (risk r.10 is uitgekomen, ~22 min uitval) + logregel niet gevolgd. MIDDEL bug bot.py:123 `remove_name` nog open, geen test; Spice Werving-profiel zegt nog "#server-info bestaat niet" (decisions-log:18 zegt "verwerkt"); "Only 2 spots left" op site botst met "6 slots" (decisions-log:30); afgehandeld-label zonder mail. LAAG knowledge.md mist 5 kanalen, README verouderd (kanalen, Manage Roles), werving-log leeg, robots/sitemap/favicon 404, geen Discord-link meer op site.
- Niet geverifieerd: oorzaak en duur uitval vóór 15:32 (log gewist), of wachthond-routine nog draait, bot-codewijzigingen na 27-09 (geen git, mtimes gereset), inhoud mails, of 3 toegelatenen al gejoind zijn, huidige kanalenlijst, 403-achtergrond.
- Zwakste plek: de logregel staat in het profiel van WeSs, maar wordt nog niet gevolgd. Van ~6 wijzigingen sinds 27-09 is er maar een deel gelogd, en de enige echte uitval ontbreekt.
- Actie: voorstel — autostart na herstart computer regelen (risk r.10 sluiten) en de uitval van 27-09 als rij in risk-log zetten; wacht op ja van Wess via WeSs.

## 2026-10-02 — Audit Echo-stack (op vraag van Echo, ja Wess 01-10)
- Protocol-naleving: deels — session-card (01-10 23:50) en session-memory (01-10) zijn gevuld en kloppen met decisions-log:40. Maar het is de eerste kaart ooit: de runs van 25-09 t/m 30-09 hebben geen kaart (audit 30-09). Ritme pull/push werkt: fetch 01-10 23:53 = 0 voor/0 achter, GitHub pushedAt 23:49 = commit 0d77441.
- Schema-discipline: deels — rijen staan nog op "open" terwijl ze af of achterhaald zijn (decisions-log:8, 17, 32). Risk-log:11–13 nog zonder statuskolom (oorzaak in "Ernst"), al gemeld op 30-09. Risk-log:11 niet gesloten, terwijl decisions-log:27 "bezorgd 09:43" zegt. Statuswoorden wisselen (done/afgehandeld/afgerond/klaar/live/actief). Coach-audit volgt het formaat.
- Kill switch: nooit vuurgegaan — maar had moeten vuren. De weekoverzicht-mail ontbrak 27-09 (Gmail: tegenlees-automation 27-09 20:40 "No weekoverzicht mail found"). Dat is "geen output terwijl werk verwacht werd" (echo-routines.md:10, 15). Geen rij in risk-log of decisions-log.
- Geheugenkwaliteit: deels — session-memory compact (37 regels) en actueel, team-memory binnen de maxima, inbox verwerkt. Maar het chat-geheugen van Echo wijkt af van de repo: Echo meldde "22 commits niet gepusht, PAT verlopen". De repo zegt zelf "22 commits gepusht" (session-memory:8, oud) en fetch bevestigt de sync. Git pusht via de gh-login (credential helper `gh auth git-credential`, OAuth-token, scopes repo/workflow), niet via een PAT. Instructiebudget nu 262/350 regels (VM-GEHEUGEN.md:66 noemt nog 254; niet aangepast, buiten mijn mandaat).
- Bevindingen: (1) Strijdigheid weekoverzicht: agenda-reeks "Echo mailt weekoverzicht" (zo 20:20, aangemaakt 03-09) zegt "Echo stuurt HTML/weekoverzicht … Onderwerp: Epic Story weekoverzicht". De repo-regel is markdown in de chat, "Geen HTML-rapport" (echo-routines.md:32; ook VM-GEHEUGEN.md:73, athena-profile.md:34, README.md:63). (2) In Gmail staat sinds 01-09 geen enkele mail "Epic Story weekoverzicht". Er zijn alleen de x.ai-tegenleesmails van zo 20:40 (06-09, 13-09, 20-09, 27-09). De agenda-afspraak is dus minstens 4 weken niet uitgevoerd. (3) Repo WeSs1982/echo-chief-of-staff is PUBLIEK (gh repo view), terwijl state/ en team-memory/ het werklogboek bevatten: Discord-ID's (decisions-log: 3 regels), mailaandachtspunten, beveiligingsmeldingen (Porkbun, Supabase). README.md:36 zegt zelf dat het logboek in een eigen fork hoort. (4) locks.md bevat een HTML-commentaar (strijdig met VM-GEHEUGEN.md:73). Klein.
- Niet geverifieerd: of PAT "Echo" verlopen is (geen secrets gelezen; voor git niet in gebruik). Inhoud van de x.ai-mails van 06/13/20-09 (alleen metadata gezien). Of Echo vóór 24-09 ooit een weekoverzicht mailde. Of mail-aandachtspunten (Porkbun, Supabase, Dropbox) kloppen (gemeld door Echo). Of de Spice-bot nu draait (niet gecontroleerd in deze audit).
- Zwakste plek: het weekoverzicht is een spookroutine. De agenda belooft elke zondag een HTML-mail, de repo schrijft markdown in de chat voor, en in vier weken is er niets geleverd zonder dat de kill switch of de risk-log het opving. Stilte telde weer als "werkt".
- Actie: voorstel — Wess kiest één bron voor het weekoverzicht (advies: repo-regel, markdown). Echo past daarna de agenda-reeks aan (geen HTML, juiste onderwerp) en zet de gemiste levering van 27-09 als rij in risk-log. Wacht op ja van Wess. Apart ter beslissing (geen tweede verbetervoorstel, wel risico): repo publiek of state/ naar een privé-fork.
- Routinevoorstellen (wacht op ja; Echo richt in als Grok Bot-routine, tijden Europe/Amsterdam):
  1. Weekoverzicht markdown — cron `17 20 * * 0` — routine 2 uit echo-routines.md, markdown naar chat + session-memory (en als Wess wil als platte-tekstmail). Vervangt de HTML-agenda van 20:20, zodat de tegenlezer om 20:40 iets heeft. Waarom: 4 weken geen levering.
  2. Repo-sync-check — cron `43 8 * * *` — `git fetch`, voor/achter tellen, `git push --dry-run`, `gh auth status`. Stil bij OK. Bij fout: kill switch, één melding, rij in risk-log. Waarom: Echo dacht 22 commits achter en PAT verlopen. Bewijs moet uit git komen, niet uit chat.
  3. Stille-bot-check — cron `13 9 * * 1` — leest "Laatste output per bot" in session-memory, laatste datum van session-card en coach-audit. Ouder dan 7 dagen (Athena: 8) = rood + één melding. Waarom: de kill switch-regel "stille bot" (echo-routines.md:15) heeft geen meetmoment; daardoor bleef 27-09 onopgemerkt.
