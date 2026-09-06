# Echo + Argus — Chief of Staff met Researcher en Feedbacklus

[English](README.md) · [Nederlands](README.nl.md) · [Deutsch](README.de.md) · [Polski](README.pl.md) · [Español](README.es.md)

Geen leeg template — een logboek dat onthoudt waarom je iets besloot, zodat je het niet twee keer hoeft uit te leggen.

Echo logt elke beslissing met de reden erbij en later de uitkomst. Hij stopt zichzelf zodra er iets breekt, in plaats van door te draaien op een fout of op een oude kopie. En hij past zijn gedrag aan op wat jij afkeurt, zolang je erbij zet waarom.

## Plak dit in een nieuwe Grok Bot

    Je bent Echo, mijn chief of staff. Clone deze repo naar /workspace/<repo-naam> als die map er nog niet is, en doe een pull. Lees echo-profile.md, echo-routines.md, VM-GEHEUGEN.md en onboarding-interview.md. Voer het onboarding-interview uit — één vraag per keer. Wacht op mijn antwoorden. Check mijn git-remote en connector. Geen push en geen routines vóór onboarding klaar is en de opzet-check schoon is.

Vereist is alleen git — maar fork deze repo eerst en gebruik de URL van je eigen fork, want je logboek staat in `state/`, binnen de repo.

Begint zonder toegang tot je mail of agenda. Vraagt daar pas om als een taak het nodig heeft.

Echo maakt de andere bots niet. Nadat hij het team voorstelt en jij ja zegt, maak jij twee extra Grok Bots en plak je `argus-profile.md` en `athena-profile.md` als system prompt.

## Wat je krijgt

Wat je krijgt is een basis, geen afgewerkt systeem. Echo kent je nog niet. Reken op een maand inwerken: geef hem echte taken, keur af met een reden, en kijk of hij het de volgende keer anders doet. Dat is waar het logboek voor is. Als je die maand doet, heb je daarna een chief of staff die op jou is afgestemd. Als je het niet doet, blijft het een template.

## Woordenlijst

- **Kaart** — session-card: één briefje per run met PASS/FAIL en wat de volgende keer anders gaat. Geen kaart = de run telt niet.
- **Lock** — een regel die vastligt omdat iets twee keer misging, of omdat jij "lock" zei.
- **Taakbrief** — het formulier waarmee Echo delegeert: doel, niet-doel, input, done, deadline, escalatie.
- **Heartbeat** — het bewijs dat een bot nog leeft: een entry op de verwachte dag. Stilte is geen bewijs.
- **Rood** — protocol-falen. Er wordt gemeld en gestopt, niet stilletjes doorgewerkt.
- **Kluis / bureau** — de kluis is je git-remote, het bureau is de werkmap op de VM.
- **Rotatie** — oude logregels worden samengevat zodra de log te lang wordt.
- **Compaction** — hetzelfde voor het geheugen: samenvatten in plaats van alles blijven meeslepen.

## Snel starten

1. **Fork deze repo eerst.** Je logboek staat in `state/`, binnen de repo — dus het hoort in jouw eigen kluis, niet in die van iemand anders. Gebruik hieronder overal de URL van jouw fork.
2. **Vereist:** een git-remote naar keuze plus de git-connector in Grok Bot. Verder niets.
3. Nieuwe Grok Bot: plak de prompt hierboven als eerste bericht, met de clone-URL van jouw fork.
4. Beantwoord de onboardingvragen. Aan het eind stelt Echo Argus (researcher) en Athena (auditor) voor — Echo maakt ze niet aan, dus jij maakt zelf twee extra Grok Bots, met `argus-profile.md` en `athena-profile.md` als system prompt. Athena hoort in een aparte bot: eentje die zichzelf auditeert heeft een blinde vlek.
5. Athena doet de opzet-check. Geen routines tot die lijst schoon is. Daarna samen één kleine eerste run, en vanaf dan de heartbeat op zondag. Geen audit in 8 dagen = rood.

## Later toevoegen

- **Firecrawl of Exa** voor Argus — scherpere bronvergelijking. Het werkt ook zonder; Argus gebruikt dan wat Grok Bot zelf kan.
- **Mail- of agenda-toegang** — alleen als een taak er echt op vastloopt. Echo vraagt er dan één keer om, met reden.

## De kluis is een git-remote naar keuze

- **GitHub of GitLab** — gratis, private repo, voor de meesten genoeg.
- **Codeberg** — Europees, geen big tech.
- **Gitea of Forgejo op je eigen homelab** — alles in eigen huis.

Nog geen account? [github.com/signup](https://github.com/signup) is de snelste optie.

## Waarom dit anders is

- **Decisions-log met reden + uitkomst** — waarom, wat afgewezen werd, en of het klopte.
- **Feedbacklus** — elke afkeuring krijgt een korte reden. Argus past bronnenkeuze daarop aan.
- **Kill switch** — trigger, stop, melding, unlock. Zie `echo-routines.md`.
- **Stille-bot** — geen output in 7 dagen terwijl werk verwacht werd = rood, geen "stilte = het werkt".
- **Pull-fout = stop** — mislukt de pull, dan werkt Echo niet door op een oude kopie.
- **Research-bot** — Argus met bron-kwaliteitsscore. Taken ná onboarding uit session-memory, niet uit vaste side-hustle-routines.
- **Drie kernroutines** — dagelijkse prioriteiten, wekelijkse samenvatting (markdown, geen HTML), risico-log check. Plus Athena-audit en workflow-audit.
- **Token-efficiënt** — compacte logs, batching, geen HTML-slurpers, rotatie na 50 entries.
- **Repo-trigger** — "check de repo en doe de update".
- **VM-persistent geheugen** — één wet: `VM-GEHEUGEN.md`.
- **Athena** — aparte auditor-bot + heartbeat, plus een externe zondagscheck door jou, want een stilgevallen bot meldt zijn eigen stilte niet.

## Wat erin zit

- `echo-profile.md` — wie Echo is (rol). Niet het runbook.
- `echo-routines.md` — rooster: trigger, input, output, done, fail.
- `athena-profile.md` — auditor. Eigen bot; Echo speelt de rol alleen als noodoplossing.
- `argus-profile.md` — researcher. Taken uit session-memory.
- `taakbrief-template.md` — verplicht bij elke delegatie.
- `decisions-log-template.md` — logformaat + voorbeeld goed/slecht.
- `VM-GEHEUGEN.md` — enige bron van waarheid voor pull/werk/kaart/push en rotatie.
- `onboarding-interview.md` — twee sporen, terugkoppeling, opzet-check, eerste run.
- `state/` — persistent geheugen.

## Licentie

MIT — gratis te gebruiken en aan te passen.
