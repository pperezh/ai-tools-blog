---
title: "Beyond the Default AI Model"
date: 2026-05-27
description: "An interactive field guide to the modern AI landscape, outlining why relying on a single model is a workflow limitation and mapping out key labs, models, and interfaces."
tags: ["AI", "models", "workflow"]
---

AI models are evolving at a pace that is genuinely hard to keep up with. Every few weeks, a new model tops a benchmark, a new interface ships, and the previous "best option" quietly steps aside. More importantly, different models are now excelling at very different tasks, writing, coding, math, image generation, cost efficiency, which means that relying on a single model is increasingly a limitation, not a workflow.

To navigate this effectively, there are three things worth keeping distinct: the parent company, the model itself, and the interface you use to interact with it. These are three separate things that receive different names and are often conflated, which creates unnecessary confusion. A company like Anthropic builds models like Sonnet and Opus, which you can access through [claude.ai](https://claude.ai), the desktop app, or Claude Code in the terminal. Same logic applies across the board. Getting this picture clear is the first step toward using AI deliberately rather than by habit.

One trend worth paying attention to: over the last few months, engineers and entrepreneurs in the US have been quietly shifting toward leaner, more cost-efficient models (many of them Chinese) rather than defaulting to the flagship US options. This is recent, it is accelerating, and it changes the calculus of what you should have access to.

If you want a first approach to non-traditional models, I would suggest starting with OpenCode (I'm not sponsored by them or anything) an agent that runs in the terminal with a clean TUI, but also has desktop and web versions available. It connects to a wide range of models from a single interface, which I think is currently the most practical way to consolidate your access and start experimenting.

The table below is my attempt to give you a clear snapshot of the current AI landscape: who builds what, what each model is best known for, and where you can actually use it.

I am genuinely curious what combinations have worked for you. [patricio@pperezh.com](mailto:patricio@pperezh.com).

---

<!-- Outer wrapper representing the dark-themed block widget -->
<div class="ai-models-wrapper">
<!-- The inner page contents which gets cloned and exported on Download -->
<div id="ai-models-page" class="ai-models-page">
<header>
<div class="eyebrow">AI Landscape</div>
<h1 class="table-title">The Models Worth Knowing<br><em>May 2026</em></h1>
<p class="subtitle">A field guide to who's building what — and where each lab truly shines.</p>
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
<th>Company</th>
<th>Models</th>
<th>Best Name</th>
<th>Interface</th>
<th>Excels At</th>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">Claude Desktop</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Claude Code</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Writing, coding<br><span style="color: rgb(122, 130, 153); font-family: 'DM Mono', monospace; font-size: 11px;">⭐ The one I use for writing tasks</span></span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">Codex IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">OpenAI CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Math, physics, images</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">Antigravity 2.0</span></div>
<div class="iface-row"><span class="iface-badge badge-ide">IDE</span><span class="iface-detail">Antigravity IDE</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Antigravity CLI</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Images, multimodal, science</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">X Desktop App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">xAI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Real-time news, long context</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">DeepSeek App</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">DeepSeek API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Cost-efficient</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Z.AI API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Cost-efficient</span>
<span class="note">⭐ The one I use for cheap tasks</span>
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
<div class="iface-row"><span class="iface-badge badge-desk">Desktop</span><span class="iface-detail">—</span></div>
<div class="iface-row"><span class="iface-badge badge-cli">CLI</span><span class="iface-detail">Baidu Qianfan API</span></div>
</div>
</div></td>
<td><div class="cell">
<span class="excels-text">Cost-efficient</span>
</div></td>
</tr>
</tbody>
</table>
</div>

<p class="asterisk-note"><span>*</span> Recent release — already the best Chinese model on global leaderboards.</p>
</div>
</div>
