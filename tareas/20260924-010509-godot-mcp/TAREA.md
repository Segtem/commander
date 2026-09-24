# No hay un proyecto Godot de prueba ni un plugin MCP elegido para que el agente trabaje en el editor

- ESTADO: ABIERTA
- PRIORIDAD: 60
- ETIQUETAS: aura, godot, mcp


## Por qué

Godot 4.7.2 ya está en `~/Dev/engines/Godot_4.7.2/`, pero Godot no trae MCP propio: el agente entra
al editor por un plugin en `addons/` del proyecto. Hay varios (septiembre de 2026); ninguno está
probado en casa:

- `yurineko73/godot-mcp-native`: el servidor corre dentro del editor por HTTP nativo de Godot, sin
  dependencias, con 154 herramientas.
- `AkiraZ1/godot-mcp`: probado en 4.7 con Claude Code y Codex.
- `Coding-Solo/godot-mcp`: es un proceso aparte (Node) que lanza el editor, corre el proyecto y captura
  la salida. Queda fuera del editor.
- `Fromlan/godot-mcp-connector`: GDScript puro para 4.7, con una política que frena lo destructivo;
  todavía es un esqueleto v0.1.0.

## Qué mirar al elegir

Varios exponen evaluación arbitraria de GDScript. Eso es escritura sin límite, y hay que leer el
código antes de instalarlo. La división de commander es: el agente escribe por el MCP del
motor, y Oracle juzga desde afuera, sólo lectura. Entonces el plugin tiene que poder volcar la
escena como hechos (el sensor), no sólo modificarla.

## Próximo paso

Crear un proyecto Godot mínimo (el equivalente de JamPlayground) dentro de commander. Leer el código
de dos candidatos y probar uno con Claude Code: que coloque un nodo y que la escena se pueda volcar
como JSON para `oracle juzgar`.
