---
tags:
  - vault-guide
notes: 3/6/26 - AI Agents can update for better productive use; note and date changes/updates
---
(https://www.youtube.com/watch?v=Dq3R3uS0sQ4&t=321s)
# Vault Directions: How This Vault Works

This vault is based on the (Steph Ango) bottom-up note-taking philosophy, + Karpathy 2nd Brain model; with customizations for your specific needs. This guide explains the system architecture and how to use it effectively.

---
### Using Templates on Mobile with Templater Plugin

1. **Create a blank note** → Tap the "+" button to create a new empty note
2. **Name it first** → Tap the title at the top and give it a descriptive name (include date if time-sensitive, e.g., `Dump - Exo Strategy - 2026-01-22`)
3. **Open the note** → Make sure you're inside the note with an active editor (cursor visible)
4. **Tap the Templater icon** → Run the Templater command (or use command palette if set up)
5. **Select your template** → Choose from Dump, Content, Admin, Solomon Talk, etc. → Template inserts with full YAML properties
6. **Fill in the template** → Edit properties and add your content → Auto-saves

**Key:** Templater needs an active editor to work, so create the blank note and open it first.

---

## The CEO's Original Philosophy

**Core Principle:** Embrace chaos and laziness to create emergent structure.

Instead of forcing rigid organization upfront, the CEO's system:
- Captures thoughts quickly without deciding where they go
- Organizes retroactively using **properties** (metadata) and **categories**
- Uses **internal links** profusely to create a web of connections
- Leverages periodic reviews (daily → weekly → monthly → yearly) for reflection
- Allows multiple organizational views through **Bases** (queryable databases)

**Key belief:** Files you control, in standard formats, last forever. Obsidian is just the interface.

---

## How Our Customized Structure Works

### 1. **Note Types & Templates**

Every note starts from a template. This enforces consistency without thinking.

**Reference notes** (things outside your world):
- Books, People, Companies, etc.
- Live in `References/` folder
- Use templates: Book, People, Contact, etc.
- Properties allow cross-category search (e.g., "All Sci-fi media rated 7/7")

**Capture notes** (your own thoughts):
- Journal entries, evergreen notes, quick ideas
- Live in root folder
- Tags like `#brain-dump`, `#0🌲` (evergreen) help identify type
- Properties like `categories`, `created`, `status` make them queryable

**Specialized capture systems:**
- **Dumps** - Raw business/personal brain dumps organized by project/topic
- **Content** - Ideas evolving across formats (tweet → short-form → long-form)
- **Admin** - Actual work tasks and system maintenance
- **Ideas** - Standalone concepts with ratings and status
- **Meetings** - Work conversations with people, organizations, topics
- **Projects** - Ongoing work initiatives with status and timeline
- **Events** - Things you attend (personal or business)

---

### 2. **Categories & Auto-Organization**

Instead of forcing folders, notes self-organize through the `categories` property.

**How it works:**
```yaml
categories:
  - "[[Books]]"
  - "[[Sci-fi]]"
```

Every note with `categories: [[Books]]` automatically appears in the Books category's database view (called a "Base").

**Available Categories:**
- Books, Podcasts, People, Companies, Events
- Projects, Meetings
- Admin, Ideas, Dumps, Content
- Evergreen (for evergreen notes with tag `#0🌲`)

**Advantage:** One note can belong to multiple categories. No forced choosing of single locations.

---

### 3. **Bases = Queryable Organization**

A Base is a database view that queries your notes by properties and displays them in tables.

**Examples:**
- **Books.base** → Shows all notes with `categories: [[Books]]`, organized by Author, Genre, Rating, Created date
- **Content.base** → Shows all content ideas, filterable by Stage (raw-thought → tweet → long-form), Status (draft/ready), and Platform
- **Dumps.base** → Shows all brain dumps organized By Project (Exo, Steel) or By Topic
- **Projects.base** → Shows all projects with Status, Type, Year, URL

**On your phone:** You navigate to `Categories/Books.md`, which embeds `![[Books.base]]`, displaying your organized book list automatically.

---

### 4. **Tags vs Categories**

- **Categories** = What bucket this note belongs to (organizational)
- **Tags** = How you describe it (descriptive, searchable)

Example:
```yaml
categories:
  - "[[Content]]"
tags:
  - mindset
  - growth
  - content-creation
```

**Special tags in use:**
- `#0🌲` = Evergreen notes (ideas refined over time)
- `#brain-dump` = Raw capture (tangential thoughts)
- `#reference` = Archive/reference material you browse occasionally

---

### 5. **Properties Drive Everything**

Properties (top YAML metadata) are how the system auto-organizes.

**Reusable across categories:**
- `categories` - Which bucket(s)
- `created` - When created
- `status` - Current state (pending, in-progress, completed, draft, ready)
- `rating` - 1-7 | **(1-10)** scale (universal across all note types) -- *1-10 is fine.. 7 is weird stop point*
- `topics` - Thematic groupings
- `project` - Which project (for Dumps, Tasks, etc.)

**Type-specific:**
- Books: `author`, `genre`, `pages`, `isbn`
- Content: `content_stage`, `platform`
- People: `phone`, `email`, `org`
- Meetings: `date`, `people`, `topics`, `org`
- Projects: `start`, `year`, `status`, `url`

**Benefit:** Short property names (`start` not `start_date`) speed up entry on mobile. Reusable properties allow cross-category queries ("Show me all Sci-fi content I've rated 7").

---

## Our Key Customizations

### 1. **Dumps Category (Business Brain Dump Evolution)**

**Why:** The CEO didn't have a structured brain-dump system. We created one.

- Each thought gets its own note (not one massive file)
- Properties: `project` (Exo, Steel), `topic`, `type: dump`, `review_date`
- Tag: `#brain-dump` identifies them as capture zones
- Weekly review: Extract insights into Projects, Ideas, or Admin tasks
- Dumps.base shows all dumps organized by Project or Topic

**Workflow:** Capture → Review → Extract → Archive

---

### 2. **Content Category (Repurposing Ideas)**

**Why:** The CEO didn't have a system for evolving one idea across formats.

- Single note is your hub for idea evolution
- `content_stage` property tracks progression: raw-thought → tweet → short-form → long-form → caption
- `status` marks it draft/ready/published
- `platform` tags which social networks it fits
- Content.base has filtered views: By Stage, Ready to Post, By Platform

**Workflow:** Capture raw thought → Polish into tweet → Expand to short-form → Develop long-form → Pull captions

---

### 3. **Admin Category (Real Work Tracking)**

**Why:** The CEO's system was idea-focused. You also track actual tasks.

- Notes for real work: vault maintenance, business tasks, communications, billing
- Properties: `status`, `priority`, `created`
- Admin.base shows what's pending, in-progress, or overdue

---

### 4. **Root Folder Organization (Your Personal Space)**

**What lives here:**
- Evergreen notes (tagged `#0🌲`)
- Brain dumps (tagged `#brain-dump`)
- One-off personal writings
- Examples and reference guides
- This Vault-Directions file

**Rule:** If it's in root, it's something you wrote or something central to your thinking.

---

### 5. **Folders Are Fine (Updated 2026-07-07)**

The old rule was "no folders for organization — use properties instead." That rule is **relaxed**. Folders are fine where they serve a clear structural purpose:

- **`WIKI/`** — the compiled knowledge layer (AI-maintained, based on Karpathy's LLM Wiki pattern). Contains `SCHEMA.md`, `index.md`, `log.md`, `raw/`, `references/`, and future entity/concept pages. See `WIKI/SCHEMA.md` for full conventions.
- **`Categories/`, `Templates/`, `References/`, `Daily/`, `Attachments/`** — existing structural folders that hold what properties can't.

Personal notes still live in root and self-organize through properties. Folders don't replace properties — they hold compiled knowledge, immutable sources, and app config. The principle "capture first, organize retroactively" still applies to personal notes. But when a system needs its own home (like the wiki), a folder is the right tool.

**What we didn't keep from the original CEO template:**
- Clippings folder (merged into References)
- Overly specific categories (Movies, Shows, Recipes, etc.)

---

## How to Use This Vault (Workflow)

### Daily
1. **Capture:** Quick notes in root (tagged `#brain-dump` or `#0🌲`)
2. **Create:** Use templates for new ideas (Content, Dumps, Admin, etc.)
3. **Link:** Reference other notes with `[[Note Name]]`

### Weekly
1. **Review Dumps:** Extract key insights into Projects, Ideas, or Admin
2. **Review Content:** Polish raw thoughts into tweet/short-form versions
3. **Review Admin:** Update task statuses, check what's pending

### Monthly
1. **Review collections:** Scan your Categories/Bases to see patterns
2. **Create connections:** Use random note button to resurface old ideas and link them
3. **Maintenance:** Fix formatting, update properties, archive completed items

---

## How to Create New Notes

### On Desktop

1. **Click "Create new note"** (+ icon or Cmd+N)
2. **Name it:** Use a descriptive name, include date if it's time-sensitive (e.g., `Solomon Talk - 2026-01-21` or `Dump - Exo Onboarding Strategy`)
3. **Choose a template:** When you create the note, Obsidian will prompt you to select a template. Choose the appropriate one:
   - `Solomon Talk Template` → For weekly conversations with Solomon
   - `Content Template` → For ideas you'll repurpose across formats
   - `Dump Template` → For brain dumps with project/topic
   - `Admin Template` → For tasks and work items
   - `Project Template` → For ongoing initiatives
   - `Evergreen Template` → For refined ideas (tag `#0🌲`)
4. **Fill it in:** The template loads with pre-filled properties and structure
5. **Save:** Cmd+S or auto-saves

### On Phone

1. **Tap the "+" button** (new note)
2. **Quick switcher opens** - Type the template name you want (e.g., `Solomon`)
3. **Tap the template** → New note loads with template structure
4. **Rename it** → Tap the title at top, add date if needed
5. **Fill in your content** → Type your response
6. **Fill properties** (optional) → Tap the properties bar at top to add/edit metadata
7. **Done** → Auto-saves

---

## Templates vs Evergreen: When to Use Each

**Templates** - Use when you want consistency and structure:
- Solomon Talk Template (weekly conversations)
- Content Template (ideas for repurposing)
- Dump Template (brain dumps with structure)
- Admin Template (tasks and work)
- Project Template (ongoing initiatives)
- Book/People/Podcast Templates (reference material)

**Evergreen Notes** - Use when you're refining a personal insight:
- Tag with `#0🌲`
- Usually one-time capture that gets polished
- Examples: "Life is poker, not chess", "You're only as big as your beliefs"
- These are your wisdom notes; treat them like evolving pieces

**Quick Rule:** If it has a repeated structure → Use a template. If it's a one-time insight you're refining → Use Evergreen template or just write in root with `#0🌲` tag.

---

## Your Weekly Rituals

### Sunday Morning: Solomon Talk (15 minutes)

1. **Create note:** `Solomon Talk - [today's date]`
2. **Have 3-5 exchanges** with Solomon about what's on your mind
3. **Save and done**

**View all your Solomon Talks:**
- Go to `Categories/Conversations.md`
- Scroll to Conversations.base
- Filter by "Solomon Talks" view
- See all talks dated over time

### Weekly Review (30 minutes)

- **Review Dumps:** Go to `Categories/Dumps.md` - extract insights into Projects/Ideas/Admin
- **Review Content:** Check `Categories/Content.md` - polish what's ready to post
- **Review Admin:** Check `Categories/Admin.md` - update task statuses

### Monthly Review (1 hour)

- **Scan Categories:** Go through each Category (Books, People, Projects) - look for patterns
- **Create connections:** Use random note button to find old ideas, link them together
- **Maintenance:** Fix formatting, archive completed items, update ratings

### Yearly Review (2-3 hours)

- **Read all Solomon Talks:** All 52 conversations - see your arc of growth
- **Review all Content:** What did you publish? What resonated?
- **Look for themes:** What kept coming up? Where did you grow most?
- **Celebrate:** How far have you come?

---

## How to View Your Organized Collections

**Every category has a Base view:**

1. **Go to root folder** (main vault)
2. **Click `Categories/` folder**
3. **Pick a category** (e.g., `Books.md`, `Conversations.md`, `Content.md`)
4. **Scroll down to see the Base** (shows as a table)
5. **Explore the different views** (each Base has multiple table views)

**Examples:**
- `Categories/Books.md` → Shows all books organized by Author, Genre, Rating
- `Categories/Content.md` → Shows all content organized by Stage (raw-thought → ready), Platform, Status
- `Categories/Conversations.md` → Shows all conversations, filtered by type (Solomon Talks)
- `Categories/Projects.md` → Shows all projects organized by Status, Year, URL

---

## Phone Workflow

On Obsidian Mobile, the system works the same way:

1. **Create new note** → Choose template from quick switcher
2. **Name it** → Include date if time-sensitive
3. **Fill content** → Type your response/idea
4. **Fill properties** (optional) → Tap properties bar at top to add metadata
5. **View collections** → Go to `Categories/[Name].md` to see organized views
6. **Search** → Use quick switcher to find notes by name

Templates and Bases sync automatically between desktop and phone via Obsidian Sync.

---

## Decision Tree: What Type of Note Should I Create?

**Am I capturing something that will evolve across formats (tweet → short-form → long-form)?**
- Yes → Use `Content Template` (categories: [[Content]])
- No → Continue

**Am I having my weekly conversation with Solomon?**
- Yes → Use `Solomon Talk Template` (categories: [[Conversations]])
- No → Continue

**Am I capturing a raw business brain dump?**
- Yes → Use `Dump Template` (categories: [[Dumps]], add project/topic)
- No → Continue

**Am I tracking a work task or system maintenance?**
- Yes → Use `Admin Template` (categories: [[Admin]])
- No → Continue

**Am I starting a new project or initiative?**
- Yes → Use `Project Template` (categories: [[Projects]])
- No → Continue

**Am I storing information about an external thing (book, person, company)?**
- Yes → Use appropriate Reference template (Book, People, Company, etc.)
- No → Continue

**Am I refining a personal insight or wisdom?**
- Yes → Use `Evergreen Template` or just write in root with `#0🌲` tag
- No → Continue

**Am I just capturing a quick thought?**
- Yes → Write in root, tag with `#brain-dump` (no template needed)

---

## The Solomon Talk System [Personal]

**What it is:** A weekly conversation with Solomon, your 85-year-old wiser self. He has your best interests in mind and decades of wisdom. You speak line-by-line, back-and-forth.

**Why it matters:** Over time, you'll have 52 conversations per year. In 5 years, that's 260 wisdom exchanges. You can review them to see:
- What you were worried about (and how it resolved)
- Patterns in Solomon's advice
- Your growth arc over months and years
- Themes that keep emerging

**How to start:** Every week (same day/time), create a new Solomon Talk using the template. Have 3-5 exchanges. That's it.

**How to review:** Go to `Categories/Conversations.md` and view the "Solomon Talks" filtered view to see all talks chronologically.

---

## Key Principles to Remember

1. **Capture first, organize later** - Don't overthink where something goes
2. **Use tags to describe, categories to bucket** - Tags are flexible, categories are organizational
3. **Properties are queryable** - Every property you add makes notes more findable
4. **Links are breadcrumbs** - Especially unresolved links (notes not created yet)
5. **Review regularly** - Weekly reviews prevent vault from becoming a graveyard; Solomon Talks are your anchor ritual
6. **Reusable > custom** - Use properties across categories (genre, rating, author, etc.)
7. **Templates make consistency easy** - Use them; they're designed for each note type
8. **Date your captures** - When notes are time-sensitive (Dumps, Solomon Talks, Content), include the date in the name

---

## Quick Reference: If You Forget How to...

**...create a new note on mobile?**
- Tap the + button, search for template name in quick switcher, select template, rename with date

**...create a Solomon Talk?**
- New note → Search "Solomon" → Select "Solomon Talk Template" → Name it `Solomon Talk - [date]` → Have your conversation → Save

**...view all your Solomon Talks?**
- Go to `Categories/Conversations.md` → Scroll to Conversations.base → Filter by "Solomon Talks" view

**...see all my Content?**
- Go to `Categories/Content.md` → Scroll to Content.base → Use filters "By Stage", "Ready to Post", or "By Platform"

**...find a specific note?**
- Use quick switcher (Cmd+K on desktop, search icon on mobile) → Type note name or keyword

**...understand what type of note to create?**
- See the "Decision Tree: What Type of Note Should I Create?" section in this file

**...link to another note?**
- Type `[[Note Name]]` in your text - links work instantly, even if the note doesn't exist yet

**...add properties to a note?**
- Tap or click the properties bar at the top of the note (usually shows "created", "categories", "tags", etc.)

**...understand how the system works?**
- Read the "How the System Works" and "Your Weekly Rituals" sections in this file, or read CLAUDE.md for technical details

---

## Your Vault is Yours

This structure is flexible. Add properties when needed. Create new categories if a pattern emerges. Delete what doesn't serve you. The CEO's philosophy was bottom-up and emergent—if you discover a better way to organize, adjust the system.

The key is: **files you control, in formats you understand, organized in ways that make sense to you.**

---

## Remember

Your vault is a tool for thought, capture, and growth. The Solomon Talks are your anchor ritual—the weekly moment you step outside time and talk to your wiser self. Over years, these conversations become a map of your journey.

Start small. Create one note. See how it feels. Build the habit. The system is here to serve you, not the other way around.
