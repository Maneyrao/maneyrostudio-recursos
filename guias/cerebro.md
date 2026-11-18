# Tu segundo cerebro con IA: plantilla de 6 carpetas

Un lugar donde está todo lo que sabés de tu trabajo o tu negocio, ordenado para que una IA (Claude Code o Codex) lo lea, lo complete y te responda con eso. Se arma con **Obsidian** (gratis), la **plantilla de 6 carpetas** y las **skills oficiales de Obsidian** para agentes.

Herramientas (todas gratis y de código abierto):
- Obsidian: https://obsidian.md
- Skills oficiales de Obsidian para agentes: https://github.com/obsidianmd/obsidian-skills (MIT)
- Graphify, para ver tu cerebro como mapa: https://github.com/Graphify-Labs/graphify (Apache-2.0)

---

## Paso 1 · Bajá la plantilla
Bajá [segundo-cerebro.zip](../segundo-cerebro.zip) (o mirá la carpeta [segundo-cerebro](../segundo-cerebro)) y descomprimilo. Son 6 carpetas, cada una con un archivo de ejemplo:

| Carpeta | Qué va |
|---|---|
| `00-entrada` | Todo lo nuevo, sin ordenar: ideas, audios transcriptos, notas rápidas. La IA lo reparte después. |
| `01-negocio` | Qué vendés, precios, cómo hablás, preguntas frecuentes. |
| `02-clientes` | Un archivo por cliente: qué compró, qué le importa, en qué quedaron. |
| `03-proyectos` | Lo que está en curso, con próximo paso y fecha. |
| `04-procesos` | Cómo se hace cada cosa, paso por paso (para que la IA o un empleado lo repita). |
| `05-archivo` | Lo terminado. No se borra: se archiva. |

Más un archivo `CLAUDE.md` en la raíz con las reglas para la IA.

## Paso 2 · Abrila en Obsidian
Instalá Obsidian → «Abrir carpeta como bóveda» → elegí la carpeta descomprimida.

## Paso 3 · Llenala (15 minutos)
Reemplazá los ejemplos de `01-negocio` con lo tuyo. Con eso solo la IA ya te conoce. Lo demás se va llenando con el uso.

## Paso 4 · Dale las skills de Obsidian a tu IA
En la terminal:
```bash
claude plugin marketplace add obsidianmd/obsidian-skills
claude plugin install obsidian@obsidian-skills
```
(Para Codex: `codex plugin marketplace add obsidianmd/obsidian-skills`.)
Después abrí Claude Code **dentro de la carpeta de la bóveda**.

## Paso 5 · Mirá tu cerebro como mapa (opcional, el del video)
Necesitás Python 3.11+ y `uv`:
```bash
uv tool install graphifyy
graphify install
```
En Claude Code, dentro de la bóveda: `/graphify .` → abrí `graphify-out/graph.html` en el navegador.

## Paso 6 · Los 5 prompts de todos los días
1. **Vaciar la entrada:** «Leé `00-entrada`, mové cada nota a la carpeta que corresponde y enlazala con lo relacionado. Mostrame qué moviste.»
2. **Antes de una reunión:** «Resumime todo lo que sé de [cliente] y en qué quedamos la última vez.»
3. **Responder igual que yo:** «Con mi tono de `01-negocio/tono.md`, respondé esta consulta: [pegá el mensaje].»
4. **Qué hago hoy:** «Revisá `03-proyectos` y decime los 3 próximos pasos más urgentes.»
5. **Que no se pierda nada:** «Pasá esta conversación/audio a nota y guardala donde corresponda.»

## Cuidados
- No guardes contraseñas ni datos de tarjetas en la bóveda.
- Si la compartís con un agente que puede escribir, hacé una copia de seguridad fuera de su alcance (por ejemplo, sincronización con historial).

## ¿Lo querés para tu negocio, ya armado?
Lo armamos con un agente que mete solo los documentos, mensajes y archivos, los conecta y les responde a vos y a tu equipo. Escribí **NEGOCIO** por privado o reservá una llamada corta: https://calendly.com/maneyro-achievements/30min?utm_source=instagram&utm_medium=dm&utm_campaign=recursos
