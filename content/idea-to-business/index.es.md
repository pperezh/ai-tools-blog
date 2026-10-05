---
title: "Una 'skill' para bosquejar tu nueva idea de negocio"
date: 2026-08-13
description: "simplemente usa esta 'skill' y podras tener una primera aproximación para cualquier idea de negocio en aspectos como: segmentación de mercado, estrategia GTM, identidad de marca, pitch deck y sitio web en Next.js."
tags: ["IA", "Agentes", "Workflows", "Startups", "Negocios"]
sidebarGroup: "concepts"
---

Transformar una idea bruta en un negocio listo para lanzar requiere semanas de trabajo fragmentado. Es necesario identificar segmentos de clientes objetivos, analizar competidores, diseñar una estrategia Go-To-Market (GTM), definir una identidad de marca visual, construir un pitch deck convincente y desarrollar una presencia web moderna.

Si tienes una idea, quieres empezar ya mismo, ver de inmediato cómo se ve y testearla en la práctica: para eso creé este skill.

**`idea-to-business` (I2B)** es un workflow agéntico ('skill') open-source diseñado para ejecutar sistemáticamente todo el pipeline de creación de empresas dentro de tu entorno de trabajo de IA.

---

## 🗺️ ¿Qué es `idea-to-business`?

`idea-to-business` es un skill de prompt de sistema estructurado que convierte cualquier entorno de IA en un arquitecto de negocios autónomo. En lugar de generar un solo bloque masivo de texto, I2B ejecuta una **máquina de estados determinista de 6 fases** con **4 puntos de control con intervención humana (🛑)**. El agente se detiene en hitos estratégicos clave—como la evaluación de segmentos, el nombrado de la empresa, la elección de estilo de marca y el diseño del logo—para garantizar que la visión humana guíe cada decisión antes de generar los activos finales.

### El Pipeline de un Vistazo

<div class="ai-kitchen">
  <table>
    <thead>
      <tr>
        <th>Meta</th>
        <th>🧠 Modelo</th>
        <th></th>
        <th>🍳 Agente / Env</th>
        <th></th>
        <th>📋 Skill</th>
        <th></th>
        <th>📄 Resultado</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="goal-label">1. Segmentación de Mercado</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">3 segmentos evaluados 🛑</td>
      </tr>
      <tr>
        <td class="goal-label">2. GTM y Posicionamiento</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">gtm_strategy.md</td>
      </tr>
      <tr>
        <td class="goal-label">3. Marca y Logo SVG</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">logo.svg y tokens de estilo 🛑</td>
      </tr>
      <tr>
        <td class="goal-label">4. Pitch Deck y Web</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">Next.js y diapositivas Reveal.js</td>
      </tr>
    </tbody>
  </table>
  <p class="footnote">* 🛑 indica un punto de control obligatorio de revisión humana antes de continuar.</p>
</div>

---

## ⚡ La Máquina de Estados de 6 Fases

El workflow opera bajo un estricto modelo de **Aislamiento Dinámico del Workspace**, creando un directorio raíz exclusivo para la empresa (ej. `[nombre-empresa]/`) para mantener todos los documentos estratégicos, presentaciones y código web perfectamente organizados.

1. **Ingestión y Análisis Inicial**: Lee tu idea conceptual, hipótesis de público objetivo y notas del dominio.
2. **Segmentación de Mercado (Punto de control 🛑)**: Evalúa 3 segmentos de clientes según la severidad del problema, tamaño de mercado, disposición a pagar y velocidad de llegada al mercado.
3. **Nombrado de Empresa (Punto de control 🛑)**: Genera opciones de nombre con estrategia de dominio y crea el workspace aislado tras la confirmación del usuario.
4. **Análisis GTM y de Mercado**: Produce `market_analysis.md` (posicionamiento de competidores, brechas de valor) y `gtm_strategy.md` (canales de adquisición, tácticas de BD y CTAs).
5. **Identidad de Marca y Logo Emblemático (Puntos de control 🛑)**: Establece paletas de color HSL, tipografías (`brand_styles.md`) y renderiza un logo SVG vectorial personalizado.
6. **Pitch Deck Ejecutivo y Sitio Web en Next.js**: Construye una presentación de 9 diapositivas en Reveal.js (vía Quarto) con estilos SCSS, junto a una landing page en Next.js lista para producción sin texto de relleno.

---

## 🛠️ Aspectos Clave de Ingeniería de IA

* **Control Humano en el Bucle**: Evita generaciones descontroladas bloqueando las decisiones arquitectónicas e identitarias tras la aprobación del usuario.
* **Garantía Cero Textos de Relleno**: Toda la redacción, propuestas de valor y contenido web se basan directamente en el análisis estratégico del mercado.
* **Tokens de Diseño Dinámicos**: Las paletas de colores y tipografías definidas en la Fase 4 se vinculan dinámicamente a las hojas de estilo SCSS del deck y a las variables CSS de Next.js.
* **Skill Portátil**: Estandarizado en un archivo `SKILL.md`, compatible con Claude Code, Cursor, Windsurf, ChatGPT y cualquier entorno LLM con instrucciones de sistema.

---

## 🚀 Cómo Empezar y Lo Que Viene

El workflow completo es open source y está disponible desde hoy. Puedes copiar las instrucciones del skill en tu herramienta de IA favorita y transformar tu próxima idea en un negocio validado en minutos.

* Explora el repositorio en GitHub: [pperezh/idea-to-business](https://github.com/pperezh/idea-to-business)

### 🔮 ¿Qué viene a continuación?

Si te parece potente validar ideas de negocio de forma agéntica, mantente atento: **¡pronto vendrá `idea-to-paper`!**

`idea-to-paper` aplicará este mismo enfoque agéntico basado en máquinas de estado al ámbito de la investigación académica, ayudando a científicos y desarrolladores a transformar hipótesis iniciales y datos experimentales en manuscritos listos para publicación.

¡Me encantaría conocer tus opiniones y comentarios sobre este workflow! Escríbeme a [patricio@pperezh.com](mailto:patricio@pperezh.com).
