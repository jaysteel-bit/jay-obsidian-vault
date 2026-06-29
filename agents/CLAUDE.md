# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## What This Repository Is

This is an **Obsidian vault** — a personal knowledge management system using Markdown files organized with properties (YAML frontmatter), categories, and internal links. It is **not a software codebase** and does not have traditional build, test, or deployment commands.

**Repository purpose:** Personal note-taking, business planning, content ideation, and knowledge capture for a business owner managing multiple sub-brands/projects (Exo, Steel).

Claude may be called upon to assist in many ways. Sometimes directly using **“@claude”** — and sometimes indirectly with proactive wants/setups. 
- Claude can periodically ask the user if he wants to update the Claude file with important updates/new information that will be helpful in the future to achieve goals, if it believes it should. In the same way the user can ask Claude to make updates also.

---

## Key Structure

### Folder Organization
- **Root** - Personal evergreen notes, brain dumps, and core thinking
- **Templates/** - Markdown templates for creating consistent note types (Book, Content, Dump, Admin, Project, Meeting, etc.)
- **Templates/Bases/** - Obsidian Base files that create queryable database views of notes
- **Categories/** - Hub files that display organized views of notes by category
- **References/** - External content (people, books, articles you reference)
- **Daily/** - Timestamped daily notes (YYYY-MM-DD.md format)
- **Attachments/** - Images, PDFs, and media files
- **.obsidian/** - Obsidian app settings and configuration

### Note Property System

All notes use a consistent property/metadata system in YAML frontmatter:

**Universal properties:**
- `categories` - Which organizational bucket(s) (e.g., `[[Books]]`, `[[Content]]`, `[[Dumps]]`)
- `created` - Date created (`YYYY-MM-DD` format)
- `status` - Current state (pending, in-progress, completed, draft, ready, published)
- `tags` - Descriptive labels (e.g., `#brain-dump`, `#0🌲` for evergreen, `#reference`)
- `rating` - 1-7 scale (used across all media and ideas)

**Type-specific properties:** See individual templates for detailed property lists.

### Categories (Auto-Organized Collections)

The vault uses a **property-based organization system** (not folder-based). Notes self-organize through their `categories` property:

**Available categories:**
- **Books** - Books read/to-read with ratings and metadata
- **Podcasts** - Podcast and podcast episode notes
- **People** - Contacts, relationships, and people notes
- **Companies** - B2B partners, potential collaborators, competitors
- **Events** - Conferences, meetings, personal events
- **Projects** - Ongoing work initiatives (Exo, Steel, etc.)
- **Meetings** - Work conversations with people and topics
- **Admin** - System maintenance and real work tasks
- **Ideas** - Standalone concepts being developed
- **Dumps** - Raw brain dump capture zones organized by project/topic
- **Content** - Content ideas evolving across formats (tweet → long-form); can come from any part of vault with `categories: [[Content]]`
- **Conversations** - Ongoing dialogues and recurring talks (e.g., weekly Solomon Talks with your future self)
- **Evergreen** - Refined ideas (tagged `#0🌲`); primary source for content repurposing

Each category has a corresponding `.base` file that creates a queryable database view in Obsidian.

---

## Content System: Claude's Collaborative Partnership

This vault uses a **unique content philosophy**: Your original thoughts are the starting point. Claude then breaks them down into clear, understandable insights that make people feel *understood*.

### Content Philosophy

**Goal:** Create content that makes people feel understood through great copywriting at a 5th grade reading level.

**The Pattern:**
1. **Your Original Thought** (top of note) - Raw, unfiltered, authentic voice
2. **Divider (---)** - Separation between original and analysis
3. **Claude Analysis** - Structured breakdown that reveals the insight

### Claude's Analysis Structure

When Claude encounters a note meant for content repurposing, it should analyze using this pattern:

```markdown
### The Core Insight
[What's the fundamental idea here? What's the emotional or practical truth?]

### Why It Matters
[Why should someone care? What problem does this solve or feeling does it acknowledge?]

### The Lesson
[What's the takeaway? The actionable wisdom?]

[Include analogies and metaphors throughout to help the idea feel real and relatable]
```

**Examples:** See `Life is poker, not chess.md` and `You're only as big as your beliefs.md` for the full pattern.

**Mobile-First Formatting:** Wrap Claude Analysis in `<details>` tags to keep content collapsible on mobile (where the user spends 90% of time). This preserves full analysis while keeping notes clean and scannable.

### Content Repurposing Strategy

Almost any note in the vault can become content through the **Content category**:

- **Evergreen notes** (tagged `#0🌲`) → Most valuable for repurposing
- **Brain dumps** (tagged `#brain-dump`) → Extract the insight, analyze it
- **Project updates** → Become lessons or behind-the-scenes content
- **Meeting notes** → Turn into lessons about people, business, growth
- **Personal reflections** → Become relatable stories

**Add to content pipeline** by creating a note with:
```yaml
categories:
  - "[[Content]]"
content_stage: raw-thought
status: draft
topics: []
platform: []
```

Then evolve through stages: raw-thought → tweet → short-form → long-form → caption

### Copywriting Principles for This Vault

When Claude analyzes and rewrites content:

1. **5th Grade Reading Level** - Use short words, short sentences, active voice
2. **Analogies First** - Help people *feel* the truth, not just understand it
3. **Relatable Examples** - Draw from universal human experiences
4. **Emotional + Practical** - Make people feel understood AND give them something to do
5. **Conversational Tone** - Like talking to a friend, not a textbook
6. **Remove Jargon** - Every technical term needs a simple explanation

**Bad:** "Cognitive dissonance occurs when competing mental models create internal friction."
**Good:** "Your brain gets confused when reality doesn't match what you expected—like when someone breaks a pattern you've always seen."

---

## Common Operations When Maintaining This Vault

### Adding a New Note Type

1. Create a **Template** in `Templates/` with a descriptive name and YAML properties
2. Include a workflow description at the bottom explaining how to use it
3. Create a corresponding `.base` file in `Templates/Bases/` if it needs a queryable view
4. Create a category file in `Categories/` that references the `.base` file
5. Document the new type in `Vault-Directions.md`

### Updating Existing Templates

- Modify template YAML properties to add new fields
- Do not change property names (breaks existing notes) — instead add new properties
- Update the workflow description if the process changes

### Handling Brain Dumps and Capture Notes

- Brain dumps should be individual notes tagged `#brain-dump`, not one massive file
- Each dump should have `project` and `topic` properties
- Dumps.base shows all dumps organized by project/topic
- Weekly: Review dumps and extract insights into Projects, Ideas, or Admin tasks

### Content Evolution System

- The **Content** category is for ideas evolving across formats
- Single note is the hub; use `content_stage` property to track: raw-thought → tweet → short-form → long-form → caption
- Content.base has filtered views: "By Stage", "Ready to Post", "By Platform"
- Do not create separate files for each format; they stay together in one note

**Claude's role in content notes:**
- When you encounter a note with `categories: [[Content]]`, recognize it as content to be repurposed
- Follow the analysis pattern: Original thought → Divider → Claude Analysis (Core Insight → Why It Matters → Lesson)
- Use 5th grade reading level with analogies/metaphors that help people *feel* the insight
- Evolve the `content_stage` property as you develop different formats
- Update `status` to "ready" when a format is polished and ready to post

### Working with References

- External content (articles, books, people) lives in `References/`
- Use consistent templates (Book Template, People Template, etc.)
- Example notes exist for reference (prefixed with "Example -")
- Properties like `author`, `rating`, `genre` are reusable across types

### Daily Notes

- Auto-created in `Daily/` with YYYY-MM-DD format
- Used for quick capture and linking (not structured note-taking)
- Should reference other notes with `[[Note Name]]` links
- Do not add extensive properties to daily notes (they're capture, not reference)

### Understanding Bases (Database Queries)

- `.base` files are YAML configurations that query notes by properties
- Example: `Books.base` queries all notes where `categories.contains(link("Books"))`
- Bases can have multiple views (tables with different sort orders, filters)
- On phone: Navigate to `Categories/Books.md` to see the Books.base query rendered

---

## Key Principles

1. **Properties enable organization** - Don't use folder nesting; use properties instead
2. **Templates ensure consistency** - Every note should use a template
3. **Link frequently** - Use `[[Note Name]]` to create a web of connections
4. **Review periodically** - Weekly review prevents vault entropy
5. **Tags describe, categories organize** - Tags are flexible; categories are structural
6. **Reuse properties across types** - `rating`, `author`, `genre` should work across different note types
7. **Short property names** - Use `start` not `start_date` (faster on mobile)

---

## Vault-Specific Customizations

This vault deviates from the CEO's (Steph Ango) original template in these ways:

1. **Dumps category** - Structured brain dump system (individual notes, not one massive file)
2. **Content category** - Repurposing system for evolving ideas across formats
3. **Admin category** - Real task tracking (CEO's system was idea-focused)
4. **Removed categories** - No Movies, Shows, Recipes, Trips, Conferences, Clippings (too specific)
5. **Root folder focus** - Personal space for evergreen notes and core thinking

See `Vault-Directions.md` for full context on system philosophy and workflow.

---

## Common Questions

**Q: Should I add a property if it doesn't exist?**
A: Yes, if multiple notes of that type will have it. Add to the template, then existing notes will support the new property.

**Q: Can a note belong to multiple categories?**
A: Yes. Use array syntax: `categories: [["Books"]], [["Sci-fi"]]]`. It will appear in both Bases.

**Q: What if I want to see all notes with rating 7?**
A: Create a new `.base` file with a filter for `rating == 7`. Bases are YAML files, easily customizable.

**Q: How do I handle notes that don't fit a category?**
A: Tag them (`#brain-dump`, `#reference`) and leave them in root. Not everything needs to be categorized.

**Q: Can I rename a category?**
A: Yes, but you must update all notes that reference it (search and replace `[[OldCategory]]` with `[[NewCategory]]`).

---

## When to Consult This File

Future Claude sessions should reference this file when:
- Adding new note types or templates
- Modifying the vault structure
- Understanding why things are organized the way they are
- Implementing new categories or bases
- Troubleshooting how a specific note type should work

---

## The Operating Loop (the Karpathy layer — agent-owned)

> Added 2026-06-03. This vault has two complementary minds: **Steph Ango** governs *capture* (everything above — properties, categories, Bases, templates; Jay's job, mobile-first). **Karpathy's LLM-wiki pattern** governs *compilation* (this section — the agent reads raw notes and maintains a compiled, interlinked wiki; the agent's job). They are two halves of one system, not competing systems. Jay captures; the agent maintains; **Jay almost never edits the wiki layer by hand.**

**The three wiki-layer files (agent-maintained, do not hand-edit):**
- `index.md` — narrative catalog of the vault. Read this FIRST when answering any query, then drill into the pages it links.
- `log.md` — append-only timeline. Format: `## [YYYY-MM-DD] action | description`. Append an entry every time you ingest, query meaningfully, or lint. Never delete entries.
- `raw/` — immutable source documents (articles, transcripts, PDFs). Read from, never write to.

**The loop — four verbs:**
1. **Ingest** — a new note or source appears → read it, write/update its summary + any relevant entity/concept pages, update `index.md`, append to `log.md`. One source may touch 5–15 pages. You do the cross-referencing; Jay just reads the result.
2. **Query** — Jay asks a question → read `index.md` first, drill into relevant pages, answer with citations. **File good answers back into the vault as new pages** so exploration compounds.
3. **Lint** — periodically (monthly) → health-check: contradictions, stale claims, orphan pages, missing cross-links, concepts deserving their own page, gaps fillable by web search. Output a short punch list.
4. **Promote** — when a note stabilizes into a *decision/fact* (referenced 2+ times, or it's become a price/offer/commitment) → it graduates to its canonical home in the `agent-workspace` repo. Add `promoted-to: "agent-workspace/<path>"` to the note's frontmatter and a one-line forward link at the top. **Rule: thinking lives here (the Forge); decisions live in agent-workspace (the Reservoir).**

**Cadence:** run Ingest per session that touches the vault (or via a scheduled Hermes job once a GitHub remote exists). Lint monthly. Because Jay is on mobile ~90% of the time, *every* maintenance step is the agent's job — never design one that needs Jay at a desktop.

**Cross-repo authority:** this section governs the loop *inside* the vault. The full Forge↔Reservoir↔Product pipeline lives in `agent-workspace/KNOWLEDGE-SYSTEM.md` — consult it for promotion targets and the productization (exo-ai.co) connection.

---

[!NOTE] **This user usually uses this vault on mobile primarily. Only 5-10% of the time is he on a desktop with this vault. 