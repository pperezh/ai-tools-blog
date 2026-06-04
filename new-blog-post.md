# Workflow: New Blog Post (`/new-blog-post`)

This workflow guides the AI coding assistant through the step-by-step process of initiating, drafting, refining, and designing a featured thumbnail for a new bilingual blog post in the AI Tools blog.

---

## Step 1: Initiate Post & Select Topic
1. Prompt the user for:
   * The **topic** or title of the new blog post.
   * A clean URL **slug** (e.g., `my-new-post`).
2. Create the bilingual page bundle directory at `content/<slug>/`.
3. Initialize the template files inside that folder:
   * `content/<slug>/index.md` (for the English version)
   * `content/<slug>/index.es.md` (for the Spanish version)
4. Add the standard Blowfish frontmatter:
   ```yaml
   ---
   title: "Your Title"
   date: YYYY-MM-DD
   description: "Brief summary of the article."
   tags: ["Tag1", "Tag2"]
   ---
   ```

---

## Step 2: Generate Drafts & CSS Style Reference
1. Draft the article in English, then translate it accurately and naturally into Spanish.
2. **CRITICAL styling instruction**: Ensure there are **no inline `<style>` blocks** inside the markdown files. All blog post visual components must reference the centralized stylesheet at `assets/css/custom.css`.
3. Supported reusable table layouts in [custom.css](file:///Users/pperezh/agy-ai-tools-blog/assets/css/custom.css):
   * **Workflow Tables (`.ai-kitchen`)**:
     * Grid columns: Goal, Model (purple pill), Agent/env (teal pill), Skill (amber pill), Output (bold text label).
     * Automatically supports dark mode variables (`--table-border`, `--table-text-primary`, etc.) with perfect contrast.
     * Example structure:
       ```html
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
               <td class="goal-label">Goal Title</td>
               <td><span class="pill p-purple">Model Name</span><span class="new-badge">new</span></td>
               <td class="arrow">→</td>
               <td><span class="pill p-teal">Agent Name</span></td>
               <td class="arrow">→</td>
               <td><span class="pill p-amber">Skill Name</span></td>
               <td class="arrow">→</td>
               <td class="output-label">output.ext</td>
             </tr>
           </tbody>
         </table>
         <p class="footnote">* Footnote explanation here.</p>
       </div>
       ```
   * **Landscape Grids (`.ai-models-wrapper`)**: Used for company, models list, interface badge lists, and excels-at ratings.
   * **Ranked Resource Tables (`.tt`)**: Used for ranked lists of resources (like MCP servers) with custom score bars.

---

## Step 3: Review & Edit Drafts
1. Show the generated English and Spanish drafts to the user for review.
2. Edit grammar, syntax, and phrasing according to user feedback.
3. Test a local Hugo build to ensure there are no parsing errors.

---

## Step 4: Design the Featured Graphic (Thumbnail)
1. Once the user confirms the drafts are ready, prompt them for the graphic design direction of the featured image.
2. Use the `generate_image` tool to create a custom graphic representing the "soul" of the post.
   * **Design Direction**: Aim for premium, high-contrast dark-mode graphics with vibrant neon highlights (purple, teal, and amber) on dark glassmorphic backgrounds. Avoid generic table layouts.
3. Save the generated image as `content/<slug>/featured.png`.
4. Run a local `hugo` command to verify that the image is picked up and compiles correctly.
