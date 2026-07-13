---
tags:
  - needs-work
backlog: true
---
### AI: Here’s what you asked for.

1. Minimal First Executor Loop Spec

Purpose  
Create the smallest possible working executor that can be pointed at any workflow folder (e.g. departments/operations/workflows/exocare-delivery-case-management/) and actually run it end-to-end while logging structured diffs.

Target Agent  
Any capable coding agent (Claude Code, Hermes, Codex, or future Flow OS executor). The spec is deliberately simple so it can be implemented quickly for dogfooding.

Executor Loop Spec (v0.1)

Input

- Path to a workflow folder (must contain README.md + numbered task subfolders).

High-Level Flow

1. Load Workflow Context

- Read the workflow README.md.
- Extract: trigger, deliverable sequence table, handoff chain, stress test notes, and any global instructions.
- Load any workflow-level references/ or templates/.

3. Traverse Tasks in Order

- List all numbered subfolders (01-xxx/, 02-xxx/, …) sorted numerically.
- For each task folder in sequence:  
    a. Determine Executor Type

- If skill.md exists → AI-executable task.
- If task.md exists → Human or hybrid task (prompt human via UI or chat).
- Never both in the same folder (per README rules).

- b. Load Task Context

- Read the primary instruction file (skill.md or task.md).
- Load all files in references/ as context (markdown, matrices, templates, etc.).
- Load scripts/ as available tools (each script file describes one API call or action; auth comes from parent tools/ folder).

- c. Execute

- For AI tasks (skill.md):

- The agent follows the instructions in skill.md.
- It can call tools from scripts/ (the agent must be able to execute the script logic or translate it to real API calls via Composio/MCP later).
- It references data from references/.

- For human/hybrid tasks (task.md):

- Present the task clearly to the human (or pause and wait for input).
- Capture human output or confirmation.

- d. Log via emit_diff() (Critical)

- After task completion (success or failure), call:  
    emit_diff(  
-   namespace="operations",           # or department  
-   entity_id="exocare-ticket-123",   # ticket/case ID  
-   event="task-completed",           # or "ticket-closed", etc.  
-   state_before=...,  
-   state_after=...,  
-   actor="ai" | "human" | "system",  
-   metadata={task: "09-ticket-closed", workflow: "exocare-delivery-case-management"}  
- )  
-   
    
- This is the single source of truth for operational memory. No other logging.

5. Handle Handoffs & Branching

- Respect the handoff chain defined in the workflow README.
- If a task produces an output that triggers another workflow, the executor can hand off or spawn a new execution.

7. Error Handling & Human Escalation

- On failure or ambiguity, pause and surface to human with full context (current task, previous diffs, references).
- Support “retry”, “skip”, or “edit instructions” actions.

9. Completion

- After the final task, mark the workflow instance complete.
- Emit a final high-level diff for the entire workflow run.

Minimal Requirements for v0.1 (Dogfooding)

- The agent must be able to read markdown files from a local folder.
- Basic tool calling (at minimum, the ability to read and simulate the scripts in scripts/).
- A working emit_diff() function (even a simple version that writes to a local Postgres table or file for now).
- Human-in-the-loop support for task.md steps.
- No need for full Composio/MCP or pgpm packaging yet — those come in v0.2+.

This spec turns the existing folder structure from “documents a human reads” into “a tree an agent can execute.”

  

2. Draft: “Path to Operationalization” Section

Copy-paste ready — place this right after the new “Current State — What Actually Exists Today” subsection in the AUM doc.

  

19. Path to Operationalization (Next 4–8 Weeks)

The departments folder already contains the correct file-tree pattern. The immediate priority is turning that pattern into a running, logged system rather than continuing to build more manual folders.

Phase 1 – Make One Workflow Executable (Dogfooding)

1. Implement a minimal emit_diff() function as the single logging chokepoint (Postgres table + simple Python/TS wrapper for now).
2. Build or configure a basic executor loop (per the separate Executor Loop Spec) that can be pointed at one workflow folder (start with exocare-delivery-case-management).
3. Wire the executor to read skill.md / task.md, load references/, treat scripts/ as tools, and call emit_diff() after every task.
4. Run the full ExoCare workflow end-to-end on real internal delivery work (dogfooding). Capture real diffs and validate the structure works under live conditions.
5. Add basic human-in-the-loop support for task.md steps.

Phase 2 – Connect to Flow OS Core

6. Map the executor output directly into the Reflex Arc and diffs/rules tables so the tree becomes the source of operational memory.
7. Package the first workflow as a pgpm namespace (even if manually for v0.1) so it can be installed on a sovereign client stack later.
8. Create a simple scaffolding template or small agent that can generate new workflow folders from a process description (to reduce manual build cost).

Phase 3 – Self-Maintenance & Scaling

9. Add a lightweight “tree gardener” agent that reviews recent diffs and proposes updates to instructions, rules, or folder structure.
10. Define the promotion path from skill.md → global Skills library so common capabilities can be reused across workflows.

Success Criteria for This Phase

- At least one workflow has been executed end-to-end by an agent (not just read by a human).
- Real diffs are being written and are queryable.
- The executor can be pointed at any existing workflow folder and run it with minimal manual intervention.
- We have proven (via dogfooding) that the file-tree abstraction is executable and produces usable operational memory.

Until these steps are complete, the departments folder remains a high-quality prototype. Once complete, it becomes the foundation of the AUM compounding asset: a living, queryable, self-improving operational intelligence tree that gets more valuable with every execution.

  

This keeps the tone honest and grounded while giving clear, prioritized next steps. The Executor Loop Spec is intentionally minimal so you can start dogfooding quickly.

Would you like any adjustments to either piece before we move on?