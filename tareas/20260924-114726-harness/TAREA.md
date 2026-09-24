# No se sabe qué harness conviene para el agente: DeepSeek Harness, Claude Code o Codex sobre el corte 1

- ESTADO: ABIERTA
- PRIORIDAD: 55
- ETIQUETAS: aura, agentes


## Por qué

DeepSeek Harness (`dsh`, deepseek-ai/deepseek-harness, MIT, TypeScript/Node, preview desde el
2026-08-13) es un harness donde todo es un plugin: el adaptador de modelo, las herramientas y el bucle.
Encaja con el bucle de commander, pero no se mete adentro de los motores: el motor se expone por MCP y
el harness se conecta desde afuera, igual que Claude Code o Codex. Así el agente, que es el que actúa,
queda separado de Oracle, que es el que juzga.

## Qué hacer

Cuando exista el corte 1 (Jam por DSL + sonda + Oracle), correr el mismo pedido con `dsh`, Claude
Code y Codex, y comparar con Oracle como juez: cuántas vueltas, cuántos rojos corregidos con los
testigos, costo. `dsh` está en preview y avisa cambios incompatibles: fijar la versión.

## Próximo paso

Esperar al corte 1.

### Nota (2026-09-24 11:54:28 UTC)

2026-09-24, Brian y Claude: commander necesita un harness, pero no se escribe uno. El bucle (modelo, herramientas, sesión) es del harness (dsh, Claude Code, Codex); Jam y Oracle se exponen como servidores MCP (el de Oracle ya existe, el de Jam falta y sale de dsl-llm); el método de commander (pedir → crear en Jam → volcar la escena → oracle juzgar → corregir con testigos) se empaqueta como plugin de dsh y como skill/instrucciones para los otros. Así el método no queda atado a un harness en preview y la comparación no reescribe nada.
