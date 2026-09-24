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

## Próximo paso

La auditoría de `dsl-llm` en Jam: qué se puede hacer por el DSL y qué sólo desde la interfaz.
