---
title: "Escribe la configuración de tus agentes una vez, enlázala en todas partes"
date: 2026-06-10
description: "Cómo centralizar tus archivos de instrucciones globales, habilidades personalizadas y agentes usando una estructura de carpetas agnóstica a la herramienta y enlaces simbólicos."
tags: ["AI", "productivity", "workflows", "setup"]
---
La eficiencia de las herramientas de IA depende del contexto que les proporcionamos. En particular, el modelo debería poder leer al menos: **1) instrucciones globales (`AGENTS.md`), 2) instrucciones/habilidades personalizadas (carpeta `skills/`), y 3) personalidades/agentes (carpeta `agents/`)**. Algunos repositorios de habilidades y agentes disponibles públicamente son excelentes; sin embargo, en el mundo de la IA, parece haber un consenso entre los usuarios de que los mejores resultados provienen de **crear estos archivos manualmente con cuidado**. Por lo tanto, la gestión de estos archivos a través de diferentes modelos se ha convertido en un aspecto clave para mantener un flujo de trabajo verdaderamente independiente del modelo (model-agnostic).

A pesar de la importancia de estos archivos, aún no existe un estándar unificado sobre cómo gestionarlos en las diferentes herramientas de IA. Cada herramienta (Claude Code, OpenCode, Antigravity CLI, Codex CLI, etc.) utiliza una estructura de carpetas diferente para almacenarlos. Por lo tanto, hacer un seguimiento del archivo más actualizado en cada directorio puede convertirse en una pesadilla administrativa.

La solución que he encontrado es mantener **una sola copia real** en una carpeta recién creada llamada `~/.agents/`. Luego, estos archivos se replican en todas las herramientas de IA mediante **enlaces simbólicos (symlinks)**. Un enlace simbólico no es una copia; es una dirección de reenvío.

- `~/.agents/AGENTS.md` para mis instrucciones globales
- `~/.agents/skills/` para mis habilidades
- `~/.agents/agents/` para las definiciones de agentes

Todo lo que está bajo `~/.claude`, `~/.gemini`, `~/.codex` y `~/.config/opencode` es solo una señal que apunta de vuelta a ellos. Cuando una herramienta abre `~/.claude/CLAUDE.md`, está leyendo exactamente los mismos bytes que `~/.agents/AGENTS.md`.

Edita el original, y todos se actualizarán a la vez porque solo existe una única fuente de verdad.

Todo el proceso es una configuración que se hace una sola vez. Crea los directorios centrales, escribe tu `AGENTS.md` a mano y luego enlázalos usando comandos `ln -s`. Aquí tienes un ejemplo:

```bash
# Crea la carpeta unificadora/central
mkdir -p ~/.agents
# Diseña tus instrucciones globales a mano
nano ~/.agents/AGENTS.md
# Vincula el archivo de configuración que usa la herramienta a tu archivo central
ln -s ~/.agents/AGENTS.md ~/.claude/CLAUDE.md
```

Aplica esta lógica a tus directorios `skills/` y `agents/`. Ese es todo el sistema. Cada herramienta lee lo mismo. Cuando agregues una nueva herramienta, busca las rutas que lee, enlázalas con `ln -s` a su origen, y listo.

A continuación se muestra una tabla de las rutas de configuración nativas para mis herramientas más utilizadas y cómo este sistema las vincula con la carpeta central.

<div class="ai-kitchen">
  <table>
    <thead>
      <tr>
        <th>Herramienta</th>
        <th>🧠 Ruta de Configuración Nativa</th>
        <th></th>
        <th>🍳 Origen Central</th>
        <th></th>
        <th>📋 Ruta de Habilidades</th>
        <th></th>
        <th>📄 Tipo de Enlace</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="goal-label">Claude Code</td>
        <td><span class="pill p-purple">~/.claude/CLAUDE.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">~/.claude/skills/</span></td>
        <td class="arrow">→</td>
        <td class="output-label">enlace simbólico</td>
      </tr>
      <tr>
        <td class="goal-label">Codex CLI</td>
        <td><span class="pill p-purple">~/.codex/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">—</span></td>
        <td class="arrow">→</td>
        <td class="output-label">enlace simbólico</td>
      </tr>
      <tr>
        <td class="goal-label">Antigravity CLI</td>
        <td><span class="pill p-purple">~/.gemini/GEMINI.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">~/.gemini/antigravity-cli/skills/</span></td>
        <td class="arrow">→</td>
        <td class="output-label">enlace simbólico</td>
      </tr>
      <tr>
        <td class="goal-label">OpenCode</td>
        <td><span class="pill p-purple">~/.config/opencode/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">~/.agents/skills/</span></td>
        <td class="arrow">→</td>
        <td class="output-label">nativo</td>
      </tr>
    </tbody>
  </table>
  <p class="footnote">* OpenCode lee ~/.agents/skills/ de forma nativa — no crees un enlace simbólico para su carpeta de habilidades o se leerá doble.<br>* Gemini CLI fue descontinuado el 18 de junio de 2026; su reemplazo es Antigravity CLI, que conservó la carpeta de configuración ~/.gemini/.</p>
</div>

Si conectas alguna herramienta que no haya cubierto — o encuentras un truco más limpio — escríbeme a [patricio@pperezh.com](mailto:patricio@pperezh.com).
