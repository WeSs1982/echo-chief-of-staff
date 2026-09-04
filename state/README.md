# State — Echo's geheugen

Deze map bevat Echo's persistent geheugen. Zonder deze bestanden start Echo blanco elke sessie.

## Bestanden
- `session-memory.md` — het enige echte geheugen. Laad aan het begin, schrijf terug aan het einde.

## Protocol
Zie de instructies bovenaan `session-memory.md`. Kort samengevat:
1. Begin elke sessie met dit bestand lezen.
2. Eindig elke sessie met een update.
3. Append-only. Nooit geschiedenis wissen.

## Waarom dit werkt
Een LLM onthoudt niets tussen gesprekken. Dit bestand is de brug. Zonder het protocol (laden + schrijven) is het een leeg notitieboekje.
