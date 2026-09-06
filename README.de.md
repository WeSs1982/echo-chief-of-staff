# Echo + Argus — Chief of Staff mit Researcher und Feedbackschleife

[English](README.md) · [Nederlands](README.nl.md) · [Deutsch](README.de.md) · [Polski](README.pl.md) · [Español](README.es.md)

Keine leere Vorlage — ein Logbuch, das sich merkt, warum du etwas entschieden hast, damit du es nicht zweimal erklären musst.

Echo protokolliert jede Entscheidung samt Begründung und später dem Ergebnis. Es stoppt sich selbst, sobald etwas kaputtgeht, statt auf einem Fehler oder einer veralteten Kopie weiterzulaufen. Und es passt sein Verhalten an das an, was du ablehnst — vorausgesetzt, du schreibst dazu, warum.

## Das hier in einen neuen Grok Bot einfügen

    Du bist Echo, mein Chief of Staff. Klone dieses Repo nach /workspace/<repo-name>, falls das Verzeichnis noch nicht existiert, und mach einen Pull. Lies VM-GEHEUGEN.md und onboarding-interview.md. Führe das Onboarding-Interview durch — eine Frage nach der anderen. Warte auf meine Antworten. Prüfe mein Git-Remote und den Connector. Kein Push und keine Routinen, bevor das Onboarding abgeschlossen ist.

Nötig ist nur Git: ein Git-Remote deiner Wahl plus der Git-Connector in Grok Bot.

Startet ohne Zugriff auf deine Mail oder deinen Kalender. Fragt erst danach, wenn eine Aufgabe es wirklich braucht.

## Was du bekommst

Was du bekommst, ist eine Grundlage, kein fertiges System. Echo kennt dich noch nicht. Rechne mit einem Monat Einarbeitung: gib ihm echte Aufgaben, lehne mit einer Begründung ab, und schau, ob er es beim nächsten Mal anders macht. Genau dafür ist das Logbuch da. Wenn du diesen Monat investierst, hast du danach einen Chief of Staff, der auf dich abgestimmt ist. Wenn nicht, bleibt es eine Vorlage.

## Glossar

- **Karte** — Session-Card: ein Zettel pro Lauf mit PASS/FAIL und dem, was beim nächsten Mal anders läuft. Keine Karte = der Lauf zählt nicht.
- **Lock** — eine Regel, die feststeht, weil etwas zweimal schiefging oder weil du "Lock" gesagt hast.
- **Auftragsbrief** — das Formular, mit dem Echo delegiert: Ziel, Nicht-Ziel, Input, Done, Deadline, Eskalation.
- **Heartbeat** — der Beweis, dass ein Bot noch lebt: ein Eintrag am erwarteten Tag. Stille ist kein Beweis.
- **Rot** — Protokollversagen. Es wird gemeldet und gestoppt, nicht stillschweigend weitergearbeitet.
- **Tresor / Schreibtisch** — der Tresor ist dein Git-Remote, der Schreibtisch das Arbeitsverzeichnis auf der VM.
- **Rotation** — alte Logzeilen werden zusammengefasst, sobald das Log zu lang wird.
- **Compaction** — dasselbe für das Gedächtnis: zusammenfassen statt alles mitzuschleppen.

## Schnellstart

1. Neuer Grok Bot: `echo-profile.md` als System-Prompt einfügen.
2. Zwei weitere Bots: `argus-profile.md` als Researcher, `athena-profile.md` als Auditor. Athena sollte ein eigener Bot sein — ein Bot, der sich selbst auditiert, hat einen blinden Fleck.
3. `echo-routines.md` als Routinen-Datei verwenden.
4. Optional: Firecrawl oder Exa an Argus anbinden. Es geht auch ohne — Argus nutzt dann das, was Grok Bot selbst kann.
5. **Erforderlich:** ein Git-Remote deiner Wahl und der Git-Connector in Grok Bot.
6. Den Prompt oben einfügen (Clone-URL anpassen, falls du einen Fork nutzt).
7. Athena macht zuerst den Setup-Check, danach den Heartbeat am Sonntag. Kein Audit in 8 Tagen = rot.

## Der Tresor ist ein Git-Remote deiner Wahl

- **GitHub oder GitLab** — kostenlos, privates Repo, für die meisten genug.
- **Codeberg** — europäisch, kein Big Tech.
- **Gitea oder Forgejo im eigenen Homelab** — alles im eigenen Haus.

Noch kein Konto? [github.com/signup](https://github.com/signup) ist der schnellste Weg.

## Warum das anders ist

- **Decisions-Log mit Begründung + Ergebnis** — warum, was abgelehnt wurde, und ob das richtig war.
- **Feedbackschleife** — jede Ablehnung bekommt eine kurze Begründung. Argus passt seine Quellenwahl daran an.
- **Kill Switch** — Trigger, Stopp, Meldung, Unlock. Siehe `echo-routines.md`.
- **Stiller Bot** — kein Output über 7 Tage, obwohl Arbeit erwartet wurde = rot, kein "Stille heißt, es läuft".
- **Fehlgeschlagener Pull = Stopp** — schlägt der Pull fehl, arbeitet Echo nicht auf einer veralteten Kopie weiter.
- **Research-Bot** — Argus mit Quellen-Qualitätsscore. Aufgaben kommen nach dem Onboarding aus dem Session-Memory, nicht aus festen Side-Hustle-Routinen.
- **Drei Kernroutinen** — Tagesprioritäten, Wochenzusammenfassung (Markdown, kein HTML), Risiko-Log-Check. Dazu das Athena-Audit und das Workflow-Audit.
- **Token-effizient** — kompakte Logs, Batching, keine HTML-Fresser, Rotation nach 50 Einträgen.
- **Repo-Trigger** — "prüf das Repo und mach das Update".
- **VM-persistentes Gedächtnis** — ein Gesetz: `VM-GEHEUGEN.md`.
- **Athena** — eigener Auditor-Bot + Heartbeat, dazu ein externer Sonntagscheck durch dich, denn ein verstummter Bot meldet sein eigenes Schweigen nicht.

## Was drin ist

- `echo-profile.md` — wer Echo ist (Rolle). Nicht das Runbook.
- `echo-routines.md` — Plan: Trigger, Input, Output, Done, Fail.
- `athena-profile.md` — Auditor. Eigener Bot; Echo übernimmt die Rolle nur als Notlösung.
- `argus-profile.md` — Researcher. Aufgaben aus dem Session-Memory.
- `taakbrief-template.md` — Pflicht bei jeder Delegation.
- `decisions-log-template.md` — Logformat + Beispiel gut/schlecht.
- `VM-GEHEUGEN.md` — einzige Quelle der Wahrheit für Pull/Arbeit/Karte/Push und Rotation.
- `onboarding-interview.md` — zwei Spuren, Rückkopplung, Setup-Check, erster Lauf.
- `state/` — persistentes Gedächtnis.

Hinweis: Die Profil- und State-Dateien sind auf Niederländisch geschrieben, weil Echo und sein Team in dieser Sprache arbeiten.

## Lizenz

MIT — frei nutzbar und anpassbar.
