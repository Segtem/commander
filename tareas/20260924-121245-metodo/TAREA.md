# El método de commander no está escrito: pedir, crear en Jam, volcar la escena, juzgar con Oracle y corregir con los testigos

- ESTADO: ABIERTA
- PRIORIDAD: 75
- ETIQUETAS: aura, agentes


## Por qué

commander no escribe un harness (tarea `harness`): su valor es el **método**, que corre sobre
cualquier harness. Hoy ese método vive sólo en prosa (`docs/AURA-PROPIO-CORTE-1.md`, el bucle de siete
pasos).

## Qué hacer

Escribir el método como algo que un harness ejecuta:

- **Plugin de `dsh`**: el bucle pedir → crear en Jam (MCP de Jam) → volcar la escena (sonda) →
  `oracle juzgar` (MCP de Oracle) → corregir con los testigos, o confirmar.
- **El mismo método como skill o instrucciones** para Claude Code y Codex, para poder compararlos
  (tarea `harness`).
- **Jev como sensor** en los cuatro lugares con prosa (nota de `harness`), con la zona media al
  humano en los nodos de Jam.
- Una medida de commander, no del dominio: ningún cambio se confirma sin un veredicto verde de Oracle
  posterior a ese cambio.

## De qué depende

De Jam: `dsl-grafos` y `jam-mcp` (sin DSL de grafos el agente no puede crear casi nada) y
`sonda-escena-l0`. De Oracle: nada, porque el MCP ya existe.

## Próximo paso

Esperar a `dsl-grafos` en Jam. Mientras tanto se puede escribir la medida del bucle, que no depende
de nada.
