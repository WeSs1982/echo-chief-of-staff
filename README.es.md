# Echo + Argus — Chief of Staff con investigador y bucle de retroalimentación

[English](README.md) · [Nederlands](README.nl.md) · [Deutsch](README.de.md) · [Polski](README.pl.md) · [Español](README.es.md)

No es una plantilla vacía — es un cuaderno de bitácora que recuerda por qué decidiste algo, para que no tengas que explicarlo dos veces.

Echo registra cada decisión junto con el motivo y, más tarde, el resultado. Se detiene solo en cuanto algo se rompe, en lugar de seguir adelante sobre un error o sobre una copia vieja. Y ajusta su comportamiento a lo que tú rechazas, siempre que digas por qué.

## Pega esto en un nuevo Grok Bot

    Eres Echo, mi chief of staff. Clona este repo en /workspace/<nombre-repo> si esa carpeta aún no existe, y haz un pull. Lee echo-profile.md, echo-routines.md, VM-GEHEUGEN.md y onboarding-interview.md. Ejecuta la entrevista de onboarding — una pregunta a la vez. Espera mis respuestas. Comprueba mi remoto de git y el conector. Nada de push ni de rutinas antes de terminar el onboarding y de que la comprobación de configuración esté limpia.

Solo hace falta git — pero haz primero un fork de este repo y usa la URL de tu propio fork, porque tu cuaderno de bitácora vive en `state/`, dentro del repo.

Arranca sin acceso a tu correo ni a tu agenda. Solo lo pide cuando una tarea realmente lo necesita.

Echo no puede crear los demás bots. Cuando proponga el equipo y tú digas que sí, creas tú dos Grok Bots más y pegas `argus-profile.md` y `athena-profile.md` como su system prompt.

## Lo que obtienes

Lo que obtienes es una base, no un sistema terminado. Echo todavía no te conoce. Cuenta con un mes de rodaje: dale tareas reales, rechaza con un motivo y mira si la próxima vez lo hace de otra manera. Para eso está el cuaderno de bitácora. Si inviertes ese mes, acabarás con un chief of staff ajustado a ti. Si no lo haces, seguirá siendo una plantilla.

## Glosario

- **Ficha** — session card: una nota por ejecución con PASS/FAIL y qué cambiará la próxima vez. Sin ficha, la ejecución no cuenta.
- **Lock** — una regla fijada porque algo salió mal dos veces, o porque tú dijiste "lock".
- **Encargo** — el formulario con el que Echo delega: objetivo, no-objetivo, input, done, plazo, escalado.
- **Heartbeat** — la prueba de que un bot sigue vivo: una entrada el día esperado. El silencio no es prueba.
- **Rojo** — fallo de protocolo. Se avisa y se para, no se sigue trabajando en silencio.
- **Caja fuerte / escritorio** — la caja fuerte es tu remoto de git, el escritorio es la carpeta de trabajo en la VM.
- **Rotación** — las líneas viejas del registro se resumen en cuanto el registro se alarga demasiado.
- **Compaction** — lo mismo para la memoria: resumir en vez de arrastrarlo todo.

## Inicio rápido

1. **Haz primero un fork de este repo.** Tu cuaderno de bitácora vive en `state/`, dentro del repo — así que pertenece a tu propia caja fuerte, no a la de otra persona. Usa la URL de tu fork en todo lo que sigue.
2. **Obligatorio:** un remoto de git a tu elección más el conector de git en Grok Bot. Nada más.
3. Nuevo Grok Bot: pega el prompt de arriba como primer mensaje, con la URL de clonado de tu fork.
4. Responde a las preguntas del onboarding. Al final Echo propone a Argus (investigador) y Athena (auditor) — él no puede crearlos, así que creas tú dos Grok Bots más, con `argus-profile.md` y `athena-profile.md` como system prompt. Athena debe ser un bot aparte: uno que se audita a sí mismo tiene un punto ciego.
5. Athena hace la comprobación de configuración. Nada de rutinas mientras esa lista no esté limpia. Después una primera ejecución pequeña juntos, y a partir de ahí el heartbeat del domingo. Sin auditoría en 8 días = rojo.

## Añadir más adelante

- **Firecrawl o Exa** para Argus — comparación de fuentes más afilada. También funciona sin ello; Argus usa entonces lo que Grok Bot puede hacer por su cuenta.
- **Acceso a correo o agenda** — solo si una tarea se topa realmente con su ausencia. Echo lo pide una vez, con motivo.

## La caja fuerte es un remoto de git a tu elección

- **GitHub o GitLab** — gratis, repo privado, suficiente para la mayoría.
- **Codeberg** — europeo, sin big tech.
- **Gitea o Forgejo en tu propio homelab** — todo en casa.

¿Aún no tienes cuenta? [github.com/signup](https://github.com/signup) es la opción más rápida.

## Por qué esto es distinto

- **Registro de decisiones con motivo y resultado** — por qué, qué se descartó y si fue acertado.
- **Bucle de retroalimentación** — cada rechazo lleva un motivo breve. Argus ajusta a eso su elección de fuentes.
- **Kill switch** — disparador, parada, aviso, unlock. Ver `echo-routines.md`.
- **Bot silencioso** — sin salida durante 7 días habiendo trabajo esperado = rojo, nada de "si calla es que funciona".
- **Pull fallido = parada** — si el pull falla, Echo no sigue trabajando sobre una copia vieja.
- **Bot investigador** — Argus con puntuación de calidad de fuentes. Tras el onboarding las tareas salen de la session memory, no de rutinas fijas de side hustle.
- **Tres rutinas base** — prioridades diarias, resumen semanal (markdown, sin HTML), revisión del registro de riesgos. Más la auditoría de Athena y la de workflow.
- **Eficiente en tokens** — registros compactos, batching, nada de HTML devorador, rotación tras 50 entradas.
- **Disparador de repo** — "revisa el repo y haz la actualización".
- **Memoria persistente en la VM** — una sola ley: `VM-GEHEUGEN.md`.
- **Athena** — bot auditor aparte + heartbeat, más una comprobación externa tuya cada domingo, porque un bot que se ha quedado callado no avisa de su propio silencio.

## Qué contiene

- `echo-profile.md` — quién es Echo (rol). No es el runbook.
- `echo-routines.md` — calendario: trigger, input, output, done, fail.
- `athena-profile.md` — auditor. Bot propio; Echo asume el papel solo como recurso de emergencia.
- `argus-profile.md` — investigador. Tareas desde la session memory.
- `taakbrief-template.md` — obligatorio en cada delegación.
- `decisions-log-template.md` — formato de registro + ejemplo bueno/malo.
- `VM-GEHEUGEN.md` — única fuente de verdad para pull/trabajo/ficha/push y rotación.
- `onboarding-interview.md` — dos vías, devolución, comprobación de configuración, primera ejecución.
- `state/` — memoria persistente.

Nota: los archivos de perfil y de state están escritos en neerlandés, que es el idioma en el que operan Echo y su equipo.

## Licencia

MIT — libre para usar y adaptar.
