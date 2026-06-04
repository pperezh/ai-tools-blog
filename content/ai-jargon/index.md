---
title: "AI jargon: don't get lost, get it right!"
date: 2026-06-04
description: "Why switching models isn't enough: separating the model, the agent, and the skill to build a coherent multi-tool AI workflow."
tags: ["AI", "productivity", "workflows", "jargon"]
---
The AI space is moving fast, and it's quite hard to keep up with all the new vocabulary. A few months ago I started using multiple AI tools simultaneously — Claude Code for coding work, OpenCode in the terminal, Cowork for file tasks, Antigravity for web pages. What I noticed quickly is that the same concepts get different names depending on who built the tool, and people use "model", "agent", and "AI" interchangeably in ways that create real confusion when you try to set up a coherent workflow.

Three concepts are worth separating clearly: the **model**, the **agent**, and the **skill**. I find it easiest to understand this using an analogy to cooking. The model is the chef's brain, it knows how to cook, but it cannot produce anything on its own. In that context, the "agent" is the kitchen: the workspace where the model actually operates, with access to your files, your terminal, and your browser. OpenCode, Hermes, Claude Code, and Cowork are not models, they are kitchens that run models inside them. The same chef (e.g., Claude Sonnet) can work in different kitchens and produce very different results depending on what tools are available. Continuing the analogy, a "skill" is the recipe: a set of step-by-step instructions written once for a specific task, like how to format your reports, how to run your analysis, or what libraries to use. Think about it: the same kitchen and the same chef, but a different recipe, yields a completely different final dish. Similarly, the same recipe and kitchen with a different chef will also yield a different result.

The practical implication is that switching models does not automatically improve your results. If your kitchen is not configured and your recipes are not written, even the best chef will produce mediocre food. My thinking, which might be a bit of a hot take, is that getting your `AGENTS.md` (or `claude.md`) file right produces more consistent results than chasing the latest model release. Think of that file as the personal notebook the chef carries into every kitchen. That, in addition to building a small library of skills tailored to your actual workflows, is what makes the difference.

The interactive table below illustrates how these three pieces combine for the tasks I do most: writing documents, running data analysis, and updating this blog. Each task uses a different kitchen, chef, and recipe tailored to that specific goal.

I am currently working on a way to keep these three elements organized and ready to be used across different toolkits in a setup that people are calling model-agnostic. Stay tuned for that upcoming post, and in the meantime, I'd love to hear what your setup is! You can reach me at [patricio@pperezh.com](mailto:patricio@pperezh.com).



<div class="ai-kitchen">
  <table>
    <thead>
      <tr>
        <th>Goal</th>
        <th>🧠 Model</th>
        <th></th>
        <th>🍳 Agent / env</th>
        <th></th>
        <th>📋 Skill</th>
        <th></th>
        <th>📄 Output</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="goal-label">Write a technical report</td>
        <td><span class="pill p-purple">Claude Opus 4.8</span><span class="new-badge">new</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Cowork</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">document-style</span></td>
        <td class="arrow">→</td>
        <td class="output-label">report.docx</td>
      </tr>
      <tr>
        <td class="goal-label">Run a data analysis</td>
        <td><span class="pill p-purple">Claude Sonnet 4.6</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">OpenCode</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">math-analysis</span></td>
        <td class="arrow">→</td>
        <td class="output-label">results.csv + plot</td>
      </tr>
      <tr>
        <td class="goal-label">Build a web page</td>
        <td><span class="pill p-purple">Gemini 3.5 Flash</span><span class="new-badge">new</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Antigravity</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">web-pages</span></td>
        <td class="arrow">→</td>
        <td class="output-label">article.html</td>
      </tr>
      <tr>
        <td class="goal-label">Agentic coding task</td>
        <td><span class="pill p-purple">GPT-5.5</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">code-review</span></td>
        <td class="arrow">→</td>
        <td class="output-label">pull request</td>
      </tr>
      <tr>
        <td class="goal-label">Cheap routine task</td>
        <td><span class="pill p-purple">GLM 5.1</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">OpenCode</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">—</span></td>
        <td class="arrow">→</td>
        <td class="output-label">varies</td>
      </tr>
    </tbody>
  </table>
  <p class="footnote">* Gemini 3.5 Flash launched May 19, 2026 at Google I/O. Gemini 3.5 Pro expected June 2026.<br>* Claude Opus 4.8 is Anthropic's latest frontier model as of this writing.</p>
</div>
