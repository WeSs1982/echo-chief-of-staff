# Beslissingen

Niet gedupliceerd. Het enige beslissingslog is `state/decisions-log.md` (append-only, één rij per beslissing: datum, beslissing, reden, uitkomst, status).

- Lezen: laatste 7 dagen + samenvatting onder `## Archief` in `state/session-memory.md`.
- Schrijven: Echo (en Athena voor audit-rijen). Andere bots zetten een beslissing die ze zien in `inbox.md`; Athena of Echo zet hem in het log.
- Format: `decisions-log-template.md`.
