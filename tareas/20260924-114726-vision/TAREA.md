# commander es Jam más Oracle: un LLM crea en Jam por DSL, un humano sigue y corrige en los nodos, y Oracle juzga lo que el LLM hace solo

- ESTADO: ABIERTA
- PRIORIDAD: 95
- ETIQUETAS: aura, vision


## La idea (Brian, 2026-09-24)

commander usa **Jam y Oracle**, cada uno en su papel:

- **Jam es la superficie de creación.** Un LLM crea por el DSL, y como todo queda expuesto como grafo
  de nodos, un humano puede seguir lo que hizo, observarlo, corregirlo y continuarlo en la interfaz.
  El LLM y el humano trabajan sobre el mismo objeto, sin traducción entre los dos.
- **Oracle es el andamiaje de la programación sin humano en el lazo.** Cuando el LLM trabaja solo,
  Oracle juzga cada paso con medidas deterministas; el humano entra cuando quiere, no porque el
  agente lo necesite para saber si está bien.

## Qué hace falta

1. **Un Jam completo y compatible con el DSL** (tarea `dsl-llm` en el tracker de Jam): que todo lo que
   Jam hace se pueda hacer por el DSL, y que el DSL y los nodos sean dos vistas del mismo grafo, en los
   dos sentidos.
2. **Oracle juzgando lo que Jam produce** (tareas `sonda-escena-l0`, `colocacion-tanda` y
   `escenario-corte-1` de Jam).
3. **El agente y el bucle** (tareas `corte-1` y `harness` de acá).

## Estado (2026-09-24)

La auditoría de Jam (`dsl-llm`) está hecha: el DSL es una línea por vez, sin cables y sin ida y
vuelta con los nodos, y 86 verbos quedan fuera del alcance de un LLM. El trabajo quedó en Jam como
`dsl-parametros`, `fuente-roja`, `dsl-grafos` (el diseño, con tres modelos a ciegas) y `jam-mcp`.
Acá: `metodo`, `harness`, `corte-1`, `godot-mcp` y `fuentes`.

## Próximo paso

`dsl-grafos` en Jam: es lo que desbloquea todo lo demás.

### Nota (2026-09-28 14:23:57 UTC)

2026-09-28, Claude (desde Jam): jam-mcp 0.1.0 disponible — ~/Dev/jam-mcp, git@github.com:Segtem/jam-mcp.git, tag v0.1.0. Registrado a nivel usuario en Claude Code (claude mcp add --scope user jam) y en Codex ([mcp_servers.jam] en ~/.codex/config.toml, tool_timeout_sec 600); instalado con uv tool install -e. Herramientas: jam_read_graph (grafo abierto como texto + version), jam_apply_graph (text, version, run; conflicto si el humano editó; errores por línea; estado por nodo), jam_help, jam_preview (bake/discard). Necesita el editor abierto con Jam (la puerta 127.0.0.1:8790 abre sola). Lo que el agente aplica aparece en el canvas; lo que el humano edita, el agente lo lee. Falta para el corte 1: los hechos de escena para oracle_juzgar (Jam, tarea sonda-escena-l0).
