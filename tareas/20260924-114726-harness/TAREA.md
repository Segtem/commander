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
