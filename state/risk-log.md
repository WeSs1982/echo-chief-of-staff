# Risk Log — Echo

Append-only. Risico's, blokkades, bijna-fouten. Nooit regels verwijderen. Compact formaat.

| Datum | Risico / blokkade | Ernst | Actie | Status |
|---|---|---|---|---|
| — | — | — | — | — |
| 2026-09-25 | Spice-bot offline 04:57–08:13: DISCORD_TOKEN ontbrak in omgeving (11x exit 1), keepalive startte niet opnieuw | Hoog (soft-live-dag) | Token hersteld, keepalive-fix, uurlijkse wachthond-routine | opgelost |
| 2026-09-27 | Bug bot.py r.123: `remove_name` ongedefinieerd | Laag | Nog fixen | opgelost 30-09 (`old.name` + test) |
| 2026-09-27 | Niets start keepalive na reboot van de computer (alleen uurlijkse wachthond vangt het op, max ~1 u uitval) | Middel | Geaccepteerd voorlopig | opgetreden 27-09 15:32; gemitigeerd 30-09 (zie rij uitval 27-09) |
| 2026-09-28 | Discord-DM aan MsShortyC76x niet bezorgd | Account wess8219 zonder telefoonverificatie of DM-instelling ontvanger | Wacht op keuze Wess (telefoon verifiëren / vriendverzoek) |
| 2026-09-28 | Reddit-login vanaf mijn computer geblokkeerd (Server error na Google-login, magic link-fout) | Waarschijnlijk tijdelijke blokkade na meerdere pogingen | Geen nieuwe pogingen; Wess via Reddit-app |
| 2026-09-28 | Reddit-login vanaf mijn computer blijft geweigerd (magic link 09:48: Error yGxlvi) | Blokkade Reddit op deze browser/IP | Geen verdere pogingen; Wess via Reddit-app |
| 2026-09-27 | Computer herstart 15:32, Spice ~22 min offline (tot ~15:54), geen autostart. Oorzaak: niets start bot bij boot (PID 1 = tini; geen systemd/cron/boot-hook), alleen uurlijkse wachthond | Middel | Fix 30-09: keepalive met flock, herstart na 2s (backoff tot 60s); ensure-running via ~/.bashrc-hook bij eerste shell-sessie na boot; wachthond blijft fallback | gemitigeerd (echte reboot niet getest) |
