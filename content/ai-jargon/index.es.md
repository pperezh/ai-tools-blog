---
title: "Jerga de IA: no te pierdas, ¡hazlo bien!"
date: 2026-06-04
description: "Por qué cambiar de modelo no es suficiente: cómo separar el modelo, el agente y la habilidad para construir un flujo de trabajo de IA coherente y multiherramienta."
tags: ["IA", "productividad", "flujos de trabajo", "jerga"]
---

El espacio de la IA avanza rápido y es bastante difícil mantenerse al día con todo este nuevo vocabulario. Hace unos meses empecé a usar múltiples herramientas de IA de forma simultánea: Claude Code para programación, OpenCode en la terminal, Cowork para tareas de archivos y Antigravity para páginas web. Lo que noté rápidamente es que los mismos conceptos reciben nombres diferentes según quién haya creado la herramienta, y la gente utiliza "modelo", "agente" e "IA" de manera intercambiable, lo que genera una confusión real cuando intentas configurar un flujo de trabajo coherente.

Vale la pena separar claramente tres conceptos: el **modelo**, el **agente** y la **habilidad** (*skill*). Para mí es más fácil entender esto mediante una analogía con la cocina. El modelo es el cerebro del chef: sabe cocinar, pero no puede producir nada por sí mismo. En ese contexto, el "agente" es la cocina: el espacio de trabajo donde el modelo realmente opera, con acceso a tus archivos, tu terminal y tu navegador. OpenCode, Hermes, Claude Code y Cowork no son modelos; son cocinas que ejecutan modelos en su interior. El mismo chef (por ejemplo, Claude Sonnet) puede trabajar en diferentes cocinas y producir resultados muy distintos según las herramientas que esa cocina tenga disponibles. Continuando con la analogía, una "habilidad" (o *skill*) es la receta: un conjunto de instrucciones paso a paso escritas una sola vez para una tarea específica —como cómo formatear tus reportes, cómo ejecutar tu análisis o qué bibliotecas usar. Piénsalo así: la misma cocina y el mismo chef, pero con una receta diferente, dan como resultado un plato final totalmente distinto. De igual manera, la misma receta y la misma cocina, pero con un chef diferente, también variarán el resultado.

La implicación práctica es que cambiar de modelo no mejora automáticamente tus resultados. Si tu cocina no está configurada y tus recetas no están escritas, incluso el mejor chef producirá comida mediocre. Mi opinión, que quizás sea un tanto controversial (*hot take*), es que configurar correctamente tu archivo `AGENTS.md` (o `claude.md`) produce resultados más consistentes que andar detrás del último lanzamiento de modelo. Piensa en ese archivo como el cuaderno personal que el chef lleva a cada cocina. Eso, sumado a la creación de una pequeña biblioteca de habilidades adaptadas a tus flujos de trabajo reales, es lo que marca la diferencia.

La tabla interactiva de abajo ilustra cómo se combinan estas tres piezas para las tareas que más realizo: escribir documentos, ejecutar análisis de datos y actualizar este blog. Cada tarea utiliza una cocina, un chef y una receta diferentes, adaptados a ese objetivo específico.

Actualmente estoy trabajando en una manera de mantener estos tres elementos organizados y listos para usar en diferentes conjuntos de herramientas, en una configuración que la gente llama "independiente del modelo" (*model-agnostic*). ¡Mantente atento a esa próxima publicación! Mientras tanto, me encantaría saber cómo es tu configuración. Puedes escribirme a [patricio@pperezh.com](mailto:patricio@pperezh.com).

<style>
.ai-kitchen { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif; margin: 2rem 0; }
.ai-kitchen table { width: 100%; border-collapse: collapse; font-size: 14px; }
.ai-kitchen thead tr { border-bottom: 2px solid #e2e2e2; }
.ai-kitchen th { font-size: 11px; font-weight: 600; letter-spacing: 0.07em; text-transform: uppercase; color: #999; padding: 0 10px 10px; text-align: left; }
.ai-kitchen th:first-child { padding-left: 0; }
.ai-kitchen td { padding: 11px 10px; vertical-align: middle; border-bottom: 1px solid #f0f0f0; }
.ai-kitchen td:first-child { padding-left: 0; }
.ai-kitchen tr:last-child td { border-bottom: none; }
.ai-kitchen .pill { display: inline-block; font-size: 12px; padding: 3px 9px; border-radius: 99px; white-space: nowrap; }
.ai-kitchen .p-purple { background: #EEEDFE; color: #3C3489; }
.ai-kitchen .p-teal   { background: #E1F5EE; color: #085041; }
.ai-kitchen .p-amber  { background: #FAEEDA; color: #633806; }
.ai-kitchen .new-badge { font-size: 10px; padding: 1px 5px; border-radius: 99px; background: #FAECE7; color: #712B13; vertical-align: middle; margin-left: 4px; }
.ai-kitchen .arrow { color: #ccc; font-size: 13px; padding: 0 2px; }
.ai-kitchen .output-label { font-size: 13px; font-weight: 500; color: #111; }
.ai-kitchen .goal-label { font-size: 13px; color: #555; }
.ai-kitchen .footnote { font-size: 11px; color: #aaa; margin-top: 1rem; line-height: 1.6; }
</style>

<div class="ai-kitchen">
  <table>
    <thead>
      <tr>
        <th>Meta / Objetivo</th>
        <th>🧠 Modelo</th>
        <th></th>
        <th>🍳 Agente / env</th>
        <th></th>
        <th>📋 Receta (Skill)</th>
        <th></th>
        <th>📄 Resultado (Output)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="goal-label">Escribir un reporte técnico</td>
        <td><span class="pill p-purple">Claude Opus 4.8</span><span class="new-badge">nuevo</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Cowork</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">document-style</span></td>
        <td class="arrow">→</td>
        <td class="output-label">report.docx</td>
      </tr>
      <tr>
        <td class="goal-label">Ejecutar análisis de datos</td>
        <td><span class="pill p-purple">Claude Sonnet 4.6</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">OpenCode</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">math-analysis</span></td>
        <td class="arrow">→</td>
        <td class="output-label">results.csv + plot</td>
      </tr>
      <tr>
        <td class="goal-label">Crear página web</td>
        <td><span class="pill p-purple">Gemini 3.5 Flash</span><span class="new-badge">nuevo</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Antigravity</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">web-pages</span></td>
        <td class="arrow">→</td>
        <td class="output-label">article.html</td>
      </tr>
      <tr>
        <td class="goal-label">Tarea de código agéntica</td>
        <td><span class="pill p-purple">GPT-5.5</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">code-review</span></td>
        <td class="arrow">→</td>
        <td class="output-label">pull request</td>
      </tr>
      <tr>
        <td class="goal-label">Tarea rutinaria de bajo costo</td>
        <td><span class="pill p-purple">GLM 5.1</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">OpenCode</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">—</span></td>
        <td class="arrow">→</td>
        <td class="output-label">varía</td>
      </tr>
    </tbody>
  </table>
  <p class="footnote">* Gemini 3.5 Flash lanzado el 19 de mayo de 2026 en Google I/O. Se espera Gemini 3.5 Pro en junio de 2026.<br>* Claude Opus 4.8 es el último modelo de frontera de Anthropic a la fecha de este escrito.</p>
</div>
