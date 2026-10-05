---
title: "A 'Skill' to Sketch Out Your New Business Idea"
date: 2026-08-13
description: "Simply use this 'skill' and you'll get a first solid baseline for any business idea across market segmentation, GTM strategy, brand identity, pitch deck, and a Next.js website."
tags: ["AI", "Agents", "Workflows", "Startups", "Business"]
sidebarGroup: "concepts"
---

Turning a raw idea into a launch-ready business venture typically requires weeks of fragmented work. You need to identify target customer segments, analyze competitors, craft a Go-To-Market (GTM) strategy, establish a visual brand identity, design a compelling pitch deck, and build a modern web presence.

If you have an idea, want to get started right away, see immediately what it looks like, and test it in practice: that's why I created this skill.

**`idea-to-business` (I2B)** is an open-source agentic workflow ('skill') designed to systematically execute the entire venture creation pipeline inside your AI workspace.

---

## 🗺️ What is `idea-to-business`?

`idea-to-business` is a structured system-prompt skill that transforms any AI environment into an autonomous business architect. Rather than generating a single wall of text, I2B runs a **6-phase deterministic state machine** with **4 human feedback checkpoints (🛑)**. The agent pauses at key strategic milestones—such as segment scoring, naming, brand style selection, and logo emblem design—to ensure human intent guides every decision before asset generation begins.

### The Pipeline at a Glance

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
        <td class="goal-label">1. Market Segmentation</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">3 scored segments 🛑</td>
      </tr>
      <tr>
        <td class="goal-label">2. GTM & Positioning</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">gtm_strategy.md</td>
      </tr>
      <tr>
        <td class="goal-label">3. Brand & SVG Logo</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">logo.svg & style tokens 🛑</td>
      </tr>
      <tr>
        <td class="goal-label">4. Pitch Deck & Web</td>
        <td><span class="pill p-purple">Claude 3.7 Sonnet</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">Claude Code / Windsurf</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">idea-to-business</span></td>
        <td class="arrow">→</td>
        <td class="output-label">Next.js & Reveal.js slides</td>
      </tr>
    </tbody>
  </table>
  <p class="footnote">* 🛑 indicates a mandatory human-in-the-loop feedback checkpoint before advancing.</p>
</div>

---

## ⚡ The 6-Phase State Machine

The workflow operates under strict **Dynamic Workspace Isolation**, creating a dedicated parent directory for the business (e.g., `[company-name]/`) to keep all generated strategy files, pitch decks, and web code organized.

1. **Input Ingestion & Analysis**: Reads your initial concept, target audience assumptions, and domain notes.
2. **Market Segmentation (Checkpoint 🛑)**: Evaluates 3 distinct target customer segments based on pain severity, market size, willingness to pay, and speed-to-market.
3. **Company Naming (Checkpoint 🛑)**: Generates curated brand names with available domain strategies and initializes the workspace root upon user confirmation.
4. **GTM & Market Analysis**: Produces comprehensive `market_analysis.md` (competitor positioning, value gaps) and `gtm_strategy.md` (acquisition channels, BD blueprints, lead magnet CTAs).
5. **Brand Identity & Emblem Design (Checkpoints 🛑)**: Establishes locked HSL color palettes, typography specs (`brand_styles.md`), and renders a custom scalable SVG logo.
6. **Executive Pitch Deck & Next.js Website**: Builds a 9-slide Quarto Reveal.js presentation with SCSS styling, alongside a production-ready Next.js landing page with zero `lipsum` placeholders.

---

## 🛠️ Key AI Engineering Features

* **Human-in-the-Loop Safeguards**: Prevents runaway generation by locking key architectural and branding choices behind user approvals.
* **Zero-Placeholder Guarantee**: All generated copywriting, value propositions, and website content are fully grounded in the strategic market analysis.
* **Dynamic Design Tokens**: Color palettes and typography tokens defined in Phase 4 are dynamically bound to SCSS slide stylesheets and Next.js CSS variables.
* **Portable Skill Design**: Standardized as a `SKILL.md` file, making it compatible with Claude Code, Cursor, Windsurf, ChatGPT, and custom LLM environments.

---

## 🚀 Get Started & What's Coming Next

The entire workflow skill is open source and available today. You can copy the skill instructions into your favorite AI tool and turn your next idea into a validated business in minutes.

* Explore the GitHub repository: [pperezh/idea-to-business](https://github.com/pperezh/idea-to-business)

### 🔮 What's Next?

If you find validating business ideas with agents powerful, stay tuned: **`idea-to-paper` is coming soon!**

`idea-to-paper` will bring the same structured, multi-phase state machine approach to academic research—helping scientists and developers turn raw hypotheses and experimental data into publication-ready manuscripts.

I'd love to hear your thoughts and feedback on the workflow! Reach out at [patricio@pperezh.com](mailto:patricio@pperezh.com).
