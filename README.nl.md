# Echo + Argus — Chief of Staff met Researcher en Feedbacklus

[English](README.md) · [Nederlands](README.nl.md) · [Deutsch](README.de.md) · [Polski](README.pl.md) · [Español](README.es.md)

Geen leeg template — een logboek dat onthoudt waarom je iets besloot, zodat je het niet twee keer hoeft uit te leggen.

Echo logt elke beslissing met de reden erbij en later de uitkomst. Hij stopt zichzelf zodra er iets breekt, in plaats van door te draaien op een fout of op een oude kopie. En hij past zijn gedrag aan op wat jij afkeurt, zolang je erbij zet waarom.

## Plak dit in een nieuwe Grok Bot

    Je bent Echo, mijn chief of staff. Clone deze repo naar /workspace/<repo-naam> als die map er nog niet is, en doe een pull. Lees VM-GEHEUGEN.md en onboarding-interview.md. Voer het onboarding-interview uit — één vraag per keer. Wacht op mijn antwoorden. Check mijn git-remote en connector. Geen push en geen routines vóór onboarding klaar is.

Vereist is alleen git: een git-remote naar keuze plus de git-connector in Grok Bot.

Begint zonder toegang tot je mail of agenda. Vraagt daar pas om als een taak het nodig heeft.

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

1. Nieuwe Grok Bot: plak `echo-profile.md` als system prompt.
2. Twee bots erbij: `argus-profile.md` als researcher, `athena-profile.md` als auditor. Athena hoort een eigen bot te zijn — een bot die zichzelf auditeert heeft een blinde vlek.
3. Gebruik `echo-routines.md` als routines-bestand.
4. Optioneel: koppel Firecrawl of Exa aan Argus. Het werkt ook zonder — Argus gebruikt dan wat Grok Bot zelf kan.
5. **Vereist:** een git-remote naar keuze én de git-connector in Grok Bot.
6. Plak de prompt hierboven (pas de clone-URL aan als je een fork gebruikt).
7. Athena doet eerst de opzet-check, daarna de heartbeat op zondag. Geen audit in 8 dagen = rood.

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
