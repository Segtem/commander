# commander

Un Aura propio: un agente que trabaja dentro del motor de juego (Unreal primero; Godot y Unity
después) y un juez externo que decide si cada cambio está bien. El juez es
[Oracle](https://github.com/Segtem/oracle), instalado desde PyPI:

```bash
python3 -m venv .venv && .venv/bin/pip install -r requirements.txt
.venv/bin/oracle test
```

`requirements.txt` fija la versión con `==`: se sube midiendo antes con la versión nueva.

Las piezas del motor (sondas, verbos de colocación, medidas del dominio) viven en
[Jam](https://github.com/Brianholl/jam). El trabajo se sigue en `tareas/`:
`.venv/bin/oracle tarea listar`.

- [docs/AURA-Y-ORACLE.md](docs/AURA-Y-ORACLE.md) — qué es Aura y dónde entra Oracle.
- [docs/AURA-PROPIO-CORTE-1.md](docs/AURA-PROPIO-CORTE-1.md) — el plan del primer corte.
