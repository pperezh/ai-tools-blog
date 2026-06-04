---
title: "Más allá del modelo de IA por defecto"
date: 2026-05-27
description: "Una guía de campo interactiva sobre el panorama moderno de la IA, que explica por qué depender de un solo modelo es una limitación de flujo de trabajo y mapea laboratorios clave, modelos e interfaces."
tags: ["IA", "modelos", "flujo-de-trabajo"]
---

Los modelos de IA están evolucionando a un ritmo que es genuinamente difícil de seguir. Cada pocas semanas, un nuevo modelo lidera un benchmark, se lanza una nueva interfaz y la opción que antes era la "mejor" se hace a un lado silenciosamente. Más importante aún, diferentes modelos ahora sobresalen en tareas muy distintas (escritura, programación, matemáticas, generación de imágenes, eficiencia de costos), lo que significa que depender de un solo modelo es cada vez más una limitación y no un flujo de trabajo.

Para navegar esto de manera efectiva, vale la pena mantener claras tres distinciones: la empresa matriz, el modelo en sí y la interfaz que usas para interactuar con él. Son tres cosas separadas que reciben nombres diferentes y que a menudo se confunden, lo que crea una confusión innecesaria. Una empresa como Anthropic construye modelos como Sonnet y Opus, a los que puedes acceder a través de [claude.ai](https://claude.ai), la aplicación de escritorio o Claude Code en la terminal. La misma lógica se aplica en todos los ámbitos. Tener este panorama claro es el primer paso para usar la IA de manera deliberada en lugar de por costumbre.

Una tendencia a la que vale la pena prestar atención: en los últimos meses, los ingenieros y emprendedores en los EE. UU. se han estado inclinando silenciosamente hacia modelos más ligeros y eficientes en costos —muchos de ellos chinos— en lugar de usar por defecto las opciones insignia estadounidenses. Esto es reciente, se está acelerando y cambia el cálculo de a qué deberías tener acceso.

Si quieres un primer acercamiento a los modelos no tradicionales, sugeriría comenzar con OpenCode (no estoy patrocinado por ellos ni nada por el estilo) que es un agente que se ejecuta en la terminal con una TUI (interfaz de usuario de texto) limpia, pero que también tiene versiones web y de escritorio disponibles. Se conecta a una amplia gama de modelos desde una sola interfaz, lo que creo que es actualmente la forma más práctica de consolidar tu acceso y comenzar a experimentar.

La tabla a continuación es mi intento de darte una instantánea clara del panorama actual de la IA: quién construye qué, por qué es más conocido cada modelo y dónde puedes usarlo realmente.

Me causa una curiosidad genuina saber qué combinaciones te han funcionado. [patricio@pperezh.com](mailto:patricio@pperezh.com).

---

<!-- Estilos específicos para la página web en vivo dentro del tema Blowfish de Hugo -->


<!-- Contenedor exterior del widget con temática oscura -->
<div class="ai-models-wrapper">
<!-- Contenido de la página que se clona y exporta al hacer clic en Descargar -->
<div id="ai-models-page" class="ai-models-page">
<header>
<div class="eyebrow">Panorama de la IA</div>
<h1 class="table-title">Los modelos que vale la pena conocer<br><em>Mayo 2026</em></h1>
<p class="subtitle">Una guía de campo sobre quién construye qué y dónde brilla realmente cada laboratorio.</p>
</header>

<div class="table-wrap">
<table>
<colgroup>
<col class="col-company">
<col class="col-models">
<col class="col-best">
<col class="col-iface">
<col class="col-excels">
</colgroup>
<thead>
<tr>
<th>Empresa</th>
<th>Modelos</th>
<th>Mejor versión</th>
<th>Interfaz</th>
<th>Sobresale en</th>
</tr>
</thead>
<tbody>
<!-- ANTHROPIC -->
<tr data-company="anthropic">
<td><div class="cell company-cell">
<div class="company-dot dot-anthropic"></div>
<span class="company-name">Anthropic</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">Haiku 4.5</span>
<span class="model-tag">Sonnet 4.6</span>
<span class="model-tag">Opus 4.7</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">Claude Opus 4.7</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">claude.ai</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">Claude Desktop</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Claude Code</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Escritura, programación<br><span style="color: rgb(122, 130, 153); font-family: 'DM Mono', monospace; font-size: 11px;">⭐ El que uso para tareas de escritura</span></span>
</div></td>
</tr>

<!-- OPENAI -->
<tr data-company="openai">
<td><div class="cell company-cell">
<div class="company-dot dot-openai"></div>
<span class="company-name">OpenAI</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">GPT-4o</span>
<span class="model-tag">GPT-5</span>
<span class="model-tag">GPT-5.5</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">GPT-5.5</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">ChatGPT.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">Codex IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">OpenAI CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Matemáticas, física, imágenes</span>
</div></td>
</tr>

<!-- GOOGLE -->
<tr data-company="google">
<td><div class="cell company-cell">
<div class="company-dot dot-google"></div>
<span class="company-name">Google</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">Gemini Flash</span>
<span class="model-tag">Gemini Pro</span>
<span class="model-tag">Gemini 3.1 Pro</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">Gemini 3.1 Pro</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">gemini.google.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">Antigravity 2.0</span></div>
<div class="iface-row"><span class="iface-badge badge-ide">IDE</span><span class="iface-detail">Antigravity IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Antigravity CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Imágenes, multimodal, ciencia</span>
</div></td>
</tr>

<!-- XAI -->
<tr data-company="xai">
<td><div class="cell company-cell">
<div class="company-dot dot-xai"></div>
<span class="company-name">xAI</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">Grok 4</span>
<span class="model-tag">Grok 4 Fast</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">Grok 4</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">x.ai/grok</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">X Desktop App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">xAI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Noticias en tiempo real, contexto largo</span>
</div></td>
</tr>

<!-- DEEPSEEK -->
<tr data-company="deepseek">
<td><div class="cell company-cell">
<div class="company-dot dot-deepseek"></div>
<span class="company-name">DeepSeek</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">V4 Flash</span>
<span class="model-tag">V4 Pro</span>
<span class="model-tag">R1</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">DeepSeek V4 Pro</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">chat.deepseek.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">DeepSeek App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">DeepSeek API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Eficiente en costos</span>
</div></td>
</tr>

<!-- ZHIPU -->
<tr data-company="zai">
<td><div class="cell company-cell">
<div class="company-dot dot-zai"></div>
<span class="company-name">z.AI</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">GLM-4.6</span>
<span class="model-tag">GLM-5</span>
<span class="model-tag">GLM-5.1</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">GLM-5.1</span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">chatglm.cn</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Z.AI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Eficiente en costos</span>
<span class="note">⭐ El que uso para tareas baratas</span>
</div></td>
</tr>

<!-- BAIDU -->
<tr data-company="baidu">
<td><div class="cell company-cell">
<div class="company-dot dot-baidu"></div>
<span class="company-name">Baidu</span>
</div></td>
<td><div class="cell">
<div class="models-list">
<span class="model-tag">ERNIE 5.0</span>
<span class="model-tag">ERNIE 5.1</span>
</div>
</div></td>
<td><div class="cell">
<span class="best-name">ERNIE 5.1<span class="asterisk">*</span></span>
</div></td>
<td><div class="cell">
<div class="iface-list">
<div class="iface-row"><span class="iface-badge badge-web">Web</span><span class="iface-detail">ernie.baidu.com</span></div>
<div class="iface-row"><span class="iface-badge badge-desk">Escritorio</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">Terminal</span><span class="iface-detail">Baidu Qianfan API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Eficiente en costos</span>
</div></td>
</tr>
</tbody>
</table>
</div>

<p class="asterisk-note"><span>*</span> Lanzamiento reciente — ya es el mejor modelo chino en las tablas de clasificación globales.</p>
</div>
</div>
