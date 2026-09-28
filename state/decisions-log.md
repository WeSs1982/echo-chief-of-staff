# Decisions Log — Echo

Append-only. Elke beslissing met reden en uitkomst. Nooit regels verwijderen. Compact formaat — vaste velden, geen lange zinnen.

| Datum | Beslissing | Reden | Uitkomst | Status |
|---|---|---|---|---|
| — | — | — | — | — |
| 2026-09-27 | Athena: wekelijkse coach-audit (week 1) geschreven in coach-audit.md; rode vlag aan WeSs | Zondag-heartbeat; logs leeg = protocol niet gevolgd | Voorstel: logs bijwerken + één rij per wijziging; wacht op ja Wess via WeSs | open |
| 2026-09-25 | Keepalive-fix: echte exitcode loggen (`code=$?`) | Keepalive logde altijd 0, oorzaak uitval onzichtbaar | Log toont nu echte codes (1, 143) | done |
| 2026-09-25 | Routine "Spice-bot wachthond" elk uur :48 (ensure-running + logcheck, stil bij OK) | Na uitval 25-09: niets startte bot/keepalive opnieuw | Draait sinds 25-09, alle runs OK | done |
| 2026-09-26 | persona.txt + knowledge.md aangepast (25+, Hagga Basin-tips alleen op vraag, Fremen-gids-toon); backups *.pre-hagga.bak | Wess-akkoord op tips + leeftijd 25+ | Bot herstart 13:44, login OK | done |
| 2026-09-26 | #server-info (Members, read-only, wachtwoord gepind) + #guides (read-only) + 3 guide-posts + schone kaart | Wess-akkoord per stap | Live, GET-check OK | done |
| 2026-09-27 | Auto-rol Member bewezen (3x Granted: 25-09 11:45, 26-09 01:20, 26-09 11:14) | Athena-audit | knowledge.md-claim nu geverifieerd | done |
| 2026-09-27 | #show-your-pets + #boom-room onder COMMUNITY (gesynct, Members view/send) | Verzoek Wess | Live, geen posts | done |
| 2026-09-27 | Argus site-review spiceuphub.com | Verzoek Wess | Goed genoeg; 5 verbeterpunten; Wess gevraagd of opdracht naar Opus mag | open |
| 2026-09-27 | Logboek-regel: één rij per Spice Up-wijziging (datum, beslissing, reden, uitkomst) | Athena rode vlag; ja van Wess 09:06 | Ingevoerd | done |
| 2026-09-27 | Athena: profiel-review geschreven in coach-audit.md; voorstel aan WeSs | Tweewekelijkse review | 2 voorstellen (WeSs-logregel in profiel, Spice Werving #server-info); wacht op ja Wess | open |
| 2026-09-27 | Athena profiel-review: voorstel 1 vastgelegd in WeSs-geheugen (profiel); voorstel 2: Spice Werving ge\u00efnformeerd dat #server-info live is | Regel mag niet wegvallen bij samenvatting; verouderde info | Beide verwerkt | done |
| 2026-09-27 | Discord-serverwidget uitgezet (Betrokkenheid > Widget server) | Widget toonde online namen publiek; Wess vroeg om uitzetten | widget.json geeft "Widget Disabled" (50004) | done |
| 2026-09-27 | Member-rol-ID 1552748130846646283 aan Wess gegeven voor ledengedeelte site (Opus, .env) | Toegang ledengedeelte op guildlid + rol Member | ID via Discord API geverifieerd | done |
| 2026-09-27 | #screenshots (1552745160968765440) uit ARCHIVE terug naar COMMUNITY, rechten gesynct | Galerij-kanaal voor /leden op de site (keuze Wess) | Onder COMMUNITY, gesynct; bot-leestoegang via API gecontroleerd | done |
| 2026-09-27 | Site stap 2 (rol-toegang /leden, wachtkamer, niet-lid-melding) live door Opus | Ledengedeelte achter Discord-login + rol Member | Uitgelogde pagina bereikbaar (curl); test ingelogd door Wess nog open | open |
| 2026-09-27 | Vercel spiceup: DISCORD_BOT_TOKEN (bestaand Spice-token, geen reset), DISCORD_GALLERY_CHANNEL_ID, LLM_API_KEY (sleutel Spice, zelfde Google-project) toegevoegd, Production, Sensitive | Chat (stap 4) en galerij (stap 6) live krijgen; Reset Token zou Spice-bot breken | Alle drie opgeslagen; redeploy Ready 11:31 | done |
| 2026-09-27 | Leonidas (leonidas85, 398867366236389397) rol Admin gegeven op Discord, via browser als eigenaar | Verzoek Wess 12:05; Spice-bot mist rechten om rollen te geven (403) | Rollen nu Admin, Member, Dune Player, PS5; via API gecontroleerd | done |
| 2026-09-28 | Werving: Discord-DM aan MsShortyC76x (Brooke) vanaf wess8219 met goedgekeurde tekst | Wess akkoord op outreach | Niet bezorgd (Discord-melding 09:13); waarschijnlijk telefoonverificatie ontbreekt | open |
| 2026-09-28 | Werving: Reddit-DMs aan Bubahmon, thebadgameruk, PollutionFull6359 via herkansing (magic link + Google) | Wess akkoord op outreach | Niet verstuurd: magic link fout N6aOOi, na Google-bevestiging opnieuw 'Server error'; Wess stuurt zelf via app | gestopt |
| 2026-09-28 | Werving: Discord-DM aan MsShortyC76x opnieuw verstuurd na koppelen telefoonnummer wess8219 (door Wess in app) | Eerste poging 09:13 niet bezorgd | Bezorgd 09:43, geen foutmelding; wacht op reactie | klaar |
