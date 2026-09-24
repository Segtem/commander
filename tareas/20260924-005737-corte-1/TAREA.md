# El corte 1 no existe: un agente coloca en Unreal a través de Jam y Oracle juzga cada cambio

- ESTADO: ABIERTA
- PRIORIDAD: 80
- ETIQUETAS: aura, unreal, corte-1


## Por qué

Aura (tryaura.dev) pone un agente adentro del editor. Lo que le falta es alguien externo que diga si
el cambio está bien: el agente que coloca no puede ser el que juzga. Este proyecto es un Aura propio
donde ese juez es Oracle, consumido desde PyPI (`requirements.txt`, fijado con `==`). El plan del
bucle de siete pasos está en [docs/AURA-PROPIO-CORTE-1.md](../../docs/AURA-PROPIO-CORTE-1.md) y el
estudio que lo motiva en [docs/AURA-Y-ORACLE.md](../../docs/AURA-Y-ORACLE.md).

## De qué depende

Las piezas del motor viven en Jam (`~/Dev/jam`), no acá, y se siguen en su tracker:

- `sonda-escena-l0` — la sonda headless que vuelca la escena como hechos L0.
- `colocar-cli` — colocar sin Slate, para que un agente pueda hacerlo.
- `colocacion-tanda` — la medida que juzga una tanda de piezas entre sí.
- `escenario-corte-1` — el arnés que ejerce el escenario de punta a punta.

`relaciones-colocacion` ya está cerrada (pieza, vecina, asentamiento).

## Qué es de este proyecto

El agente y el bucle: pedir, colocar con `jam:preview`, sondear, `oracle juzgar`, corregir con los
testigos o confirmar. Las medidas del dominio de colocación son de Jam; acá van sólo las del bucle
(por ejemplo, que ningún cambio se confirme sin un veredicto verde posterior a él).

## Próximo paso

Esperar las cuatro piezas de Jam; mientras tanto, decidir qué agente corre el bucle y cómo habla con
el editor (sondas headless por `-ExecCmds`, como hoy Jam).
