---
tags:
  - processed
  - aum-model
date: 2026-07-12
acted-on: true
compiled: 2026-08-05
backlog: false
---

# Quick Run Through of Model

> Jay's honest reaction to [[aum-bomt-intelligence-compounding-vehicle]] after Exo added the §21 "Current State" subsection. Captured 2026-07-12.

---

## What's Accurate

- The `departments/` folder structure (especially the ExoCare workflow with its numbered task folders, `skill.md`/`task.md`, `scripts/`, and `references/`) is literally the file-tree abstraction we discussed. Workflow = folder, task = subfolder, instructions + tools + data inside. That pattern is correct and aligns with the durable abstraction layer.
- The AI Assets folder follows the same logic at the brand/content level. Good pattern reuse.
- The gap table is fair. You have the structure (125 markdown files, consistent folders), but almost none of the execution layer is real yet (`emit_diff()` doesn't exist, no agent traverses the tree, scripts are pseudocode, no dogfooding has happened).

## Where I'd Push Back Slightly

The agent calls the current state a "null plan" without operationalization. That's directionally correct for long-term scaling, but it's a bit harsh for where you actually are.

You're in prototype / pattern-validation stage, not "null." Building the folder structure manually first was the right move — it let you think through the right abstraction (instructions + tools + data per task) without getting lost in code. Many founders skip this and jump straight to brittle frameworks.

The real risk isn't that the structure is wrong. The risk is:

- It stays manual forever (human consultant has to build/maintain every workflow by hand).
- It never gets wired to an executor, so it never becomes a running system that produces real diffs and compounds AUM.

## Key Thoughts on Automation & Throughput

Yes — this must be automated if you want any real throughput or scaling. Relying on a human consultant to manually capture, write, and maintain every `skill.md`, script, and reference across 20+ workflows is unsustainable. That path leads to exactly what you said: it takes forever and has no throughput.

The file-tree model becomes powerful only when an agent can read and execute it. The departments folder should eventually be the thing the Reflex Arc / coding agent traverses, not something a human reads and follows step-by-step.

## What Needs to Exist (in rough priority order)

1. `emit_diff()` as the single logging chokepoint — This is still the #1 missing piece. Every task completion (especially step 09 in ExoCare) should call a real `emit_diff()` function instead of writing to Airtable or a proxy.
2. An executor loop — A coding agent (Hermes or Claude Code) that can be pointed at a workflow folder, read the README + numbered task folders in sequence, treat `scripts/` as tools, `references/` as context, and actually run the workflow while logging via `emit_diff()`.
3. Dogfooding on real work — Run at least one full workflow (ExoCare is the obvious first candidate) against your own delivery/ops processes. This is non-negotiable before you sell it to clients.
4. Build & maintenance mechanisms — Later, use agents to help scaffold new workflows from process descriptions and review diffs to propose tree updates ("tree gardener" agent).

Until steps 1–3 exist, the beautiful folder structure remains a well-designed manual. Once they exist, the tree becomes a living, executable, compounding asset — exactly what makes the AUM model defensible.

## Bottom Line

Your agent's diagnostic is correct on the current state and the gaps. The folder pattern you built is the right one. The vision of file trees as the durable abstraction layer is solid. But the system is not real yet — it's a strong prototype that needs an execution engine and real usage (dogfooding) to become the operational intelligence asset described in the AUM model.

The good news: you don't have to throw anything away. The departments folder is already the physical manifestation of the right architecture. You just need to connect it to the Reflex Arc + `emit_diff()` and start running it.

---

*Processed 2026-07-13: Priority items promoted to §22 "Path to Operationalization" in [[aum-bomt-intelligence-compounding-vehicle]]. Departments README updated with Known Gaps section.*
