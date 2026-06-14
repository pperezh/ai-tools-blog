---
title: "Write Your Agent Config Once, Symlink It Everywhere"
date: 2026-06-10
description: "How to centralize your global instruction files, custom skills, and agents using a tool-agnostic folder structure and symlinks."
tags: ["AI", "productivity", "workflows", "setup"]
---
The efficiency of AI tools depends on the context we provide them. In particular, the model should be able to read at least: **1) global instructions (`AGENTS.md`), 2) custom instructions/skills (`skills/` folder), and 3) personalities/agents (`agents/` folder)**. Some publicly available skill repositories and agents are amazing; however, in the AI world, there seems to be a consensus among users that the best results come from **carefully crafting these files manually**. Therefore, managing these files across different models has become a key aspect of maintaining a truly model-agnostic workflow.

Despite the importance of these files, there is no unified standard yet on how to manage them across different AI tools. Each tool (Claude Code, OpenCode, Antigravity CLI, Codex CLI, etc.) uses a different folder structure to store them. Therefore, keeping track of the most up-to-date file in each directory can become an administrative nightmare.

The solution I have found is to keep **one real copy** in a newly created folder called `~/.agents/`. Then, these files are mirrored across all AI tools using **symlinks**. A symlink isn't a copy; it's a forwarding address.

- `~/.agents/AGENTS.md` for my global instructions
- `~/.agents/skills/` for my skills
- `~/.agents/agents/` for agent definitions

Everything under `~/.claude`, `~/.gemini`, `~/.codex`, and `~/.config/opencode` is just a signpost back to those. When a tool opens `~/.claude/CLAUDE.md`, it's reading the exact same bytes as `~/.agents/AGENTS.md`.

Edit the original, and all of them update at once because there is only ever one source of truth.

The whole thing is a one-time setup. Create the central directories, write your `AGENTS.md` by hand, then symlink them using `ln -s` commands. Here's an example:

```bash
# Create the unifying/central folder
mkdir -p ~/.agents
# Handcraft your global instructions
nano ~/.agents/AGENTS.md
# Symlink the config file the tool uses to your central file
ln -s ~/.agents/AGENTS.md ~/.claude/CLAUDE.md
```

Apply this logic to your `skills/` and `agents/` directories. That's the whole system. Every tool reads the same thing. When you add a new tool, find the paths it reads, `ln -s` them home, and you're done.

Below is a table of the native configuration paths for my most used tools and how this system links them to the central folder.

<div class="ai-kitchen">
  <table>
    <thead>
      <tr>
        <th>Tool</th>
        <th>🧠 Native Config Path</th>
        <th></th>
        <th>🍳 Central Source</th>
        <th></th>
        <th>📋 Skills Path</th>
        <th></th>
        <th>📄 Link Type</th>
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
        <td class="output-label">symlink</td>
      </tr>
      <tr>
        <td class="goal-label">Codex CLI</td>
        <td><span class="pill p-purple">~/.codex/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">—</span></td>
        <td class="arrow">→</td>
        <td class="output-label">symlink</td>
      </tr>
      <tr>
        <td class="goal-label">Antigravity CLI</td>
        <td><span class="pill p-purple">~/.gemini/GEMINI.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">~/.gemini/antigravity-cli/skills/</span></td>
        <td class="arrow">→</td>
        <td class="output-label">symlink</td>
      </tr>
      <tr>
        <td class="goal-label">OpenCode</td>
        <td><span class="pill p-purple">~/.config/opencode/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-teal">~/.agents/AGENTS.md</span></td>
        <td class="arrow">→</td>
        <td><span class="pill p-amber">~/.agents/skills/</span></td>
        <td class="arrow">→</td>
        <td class="output-label">native</td>
      </tr>
    </tbody>
  </table>
  <p class="footnote">* OpenCode reads ~/.agents/skills/ natively — do not symlink its skills folder or it will double-read.<br>* Gemini CLI was deprecated on June 18, 2026; its replacement is Antigravity CLI, which kept the ~/.gemini/ config folder.</p>
</div>

If you wire up a tool I haven't covered — or find a cleaner trick — write me at [patricio@pperezh.com](mailto:patricio@pperezh.com).
