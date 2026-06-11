---
name: arctouch-estimates
description: Structures project estimates and PRDs to align with ArcTouch estimation standards (Estimation Tool, Estimating a Project, Notion). Use when creating or updating estimate sheets, PRD effort tables, CSV for "2. Estimates" tab, or when the user asks about ArcTouch estimating, T-shirt sizes, backlog effort, or sprint planning. Always produce a SPRINT-PLAN.md that includes development order (Order), parallel tracks, predecessors, sprint allocation, and team size per sprint for full estimate packages.
metadata:
  tags: arctouch, estimates, prd, t-shirt sizes, backlog, estimation tool, notion, sprint plan, predecessors, parallel tracks, development order, team sizing
---

# ArcTouch Estimates
This is a new version!

Use this skill when drafting or updating **estimate sheets**, **PRD effort tables**, **CSV for the "2. Estimates" tab**, or **sprint plans** so they align with ArcTouch estimation standards (Notion: *Estimating a Project* → *Estimation Tool (2025)*; *Estimation Guide*). For any full estimate package, also produce **SPRINT-PLAN.md** with **development order** (Order column), **parallel tracks** (which tasks can run together), **predecessors** (blocking tasks per task), **sprint allocation**, and **team size per sprint** (see [SPRINT-PLAN.md — required structure](#sprint-planmd--required-structure) below).

## Template estimate sheet (required workflow)

**Reference template (read-only):** [ArcTouch Estimation Tool — template](https://docs.google.com/spreadsheets/d/1qPm7HX2VPH6k4JEuDwDkmIOOnXNXP9ePioYBIiFiDzo/edit?gid=1383075938#gid=1383075938)

Before editing or pasting estimates into a Google Sheet:

1. **Either** duplicate the template and rename the copy to the **client/project name** (e.g. "Estimate — Acme Corp"), **or** ask the user: "Do you already have a copy of the estimate sheet for this client? If not, duplicate the template and rename it to the client name."
2. **Never edit the template spreadsheet.** All edits and pastes go only into the client-specific copy.

## T-shirt sizes (effort in days)

Use **only** these values in Engineering Days, Design Days, and Backend Eng Days:

| Days | Size |
|------|------|
| 0 | None |
| 1 | Extra Small |
| 2 | Small |
| 5 | Medium |
| 10 | Large |
| 15 | Extra Large |
| 20 | Extra Extra Large |
| 40 | Huuuuge |

Do **not** use arbitrary numbers (e.g. 3, 7, 12). Round to the nearest size.

## Estimate sheet structure

**Columns** (matches ArcTouch Estimation Tool and typical "2. Estimates" tab):

| Column | Purpose |
|--------|--------|
| Epic | Phase or theme (e.g. Discovery & strategy, CMS & frontend, Core pages) |
| Feature/Task | Concrete deliverable or activity |
| Scope Assumptions | What is in/out; dependencies; client vs agency ownership |
| Risks | Scope not locked, content delayed, access delayed, etc. |
| Who | `eng only`, `design only`, or `eng & design` — determines which day columns apply |
| Engineering Days | T-shirt size (days) for frontend/engineering work |
| Design Days | T-shirt size (days) for design work |
| Backend Eng Days | T-shirt size (days) for API/integration (Salesforce, middleware, etc.) |

**Who** values: `eng only`, `design only`, `eng & design`. Use these consistently.

## ArcTouch alignment rules

1. **Single-point (realistic) estimates per row**  
   One number per cell. The Estimation Tool may use Low/High; map single value to Low/High per ArcTouch guidance when feeding the official spreadsheet. Do **not** add buffer in the backlog rows.

2. **Velocity in Team tab, not in rows**  
   QA, bug fixing, and non-project time are applied in the **Team** tab and capacity planning. Do **not** add a buffer or "testing" days in line items.

3. **No separate QA / UAT / Launch line items**  
   QA, UAT, and Launch are **team staffing**, not separate estimate rows. Raw estimates = dev + code review only.

4. **Assumptions tab [Owner: PM]**  
   Project-level assumptions (platform, region/GEO, integrations, SEO, content ownership, accessibility, GDPR) live in an Assumptions section and feed the Estimation Tool Assumptions tab.

5. **Backend Eng Days**  
   Use for API work, integration layer, CRM/middleware. Same logic as the Estimation Tool Backend Estimates.

6. **Accessibility**  
   Not a separate line item. Use Eng/Design % (A11y) at the end of the Estimation Tool to proper track those hours.

7. **Sanity check**  
   After pasting into "2. Estimates" or the Estimation Tool, use the **Team** tab and **Sprint and Capacity Planner** to validate duration and budget.

## Output formats

- **PRD:** Epics/features table with Scope assumptions, Risks, Who, and T-shirt sizes; totals by phase; copy-paste table for "2. Estimates" (no header or with header as in template).
- **CSV for "2. Estimates" tab:** Same columns; comma-separated; no extra buffer rows unless the template requires phase dividers or a reference row.
- **Totals:** By phase and overall. If the sheet is split by Engineering / Design / Backend Eng days, document the mapping to any blended or client-facing totals.
- **SPRINT-PLAN.md (required):** When creating or updating a full estimate package, **always** create (or update) a sprint plan file at **`estimates/<ClientOrProjectName>/SPRINT-PLAN.md`**. When making the sprint plan, **always** consider and include: **(1) development order** (task sequence), **(2) parallel tracks** (which tasks can run at the same time), **(3) predecessors** (which tasks block each task), **(4) sprint allocation** (tasks assigned to sprints respecting predecessors and timeline), **(5) team size per sprint** (FTE by discipline). See the required structure below.

### SPRINT-PLAN.md — required structure

Create **`estimates/<ClientOrProjectName>/SPRINT-PLAN.md`** (same folder as the estimate). **Always** derive and document the following in this order:

1. **Development order (Order)**  
   Number every task with a sequence **Order** (1, 2, 3, …) so that dependencies come first: e.g. backend/infra before app, design before build, integration after components. The estimate table (or CSV) must list tasks in this **development order** and include an **Order** column. This order is the build sequence used for predecessors and sprint allocation.

2. **Parallel tracks**  
   For each task, identify whether it can run **in parallel** with others (same discipline or no dependency between them). In the estimate table, add a **Parallel** column (e.g. same letter = same track: "A", "B", "—" for sequential). In SPRINT-PLAN.md, include a short **table or section** that lists parallel tracks (e.g. "Track A: tasks 1, 2; Track B: tasks 5, 6 — can run in parallel after task 4"). Use this to compress calendar time and size the team.

3. **Predecessors (blocking tasks)**  
   For **every** task, list **Predecessors**: the Order numbers that must complete before this task can start. Use "—" when there are none. Derive from logical dependencies (e.g. task 9 needs 5 and 6; task 16 needs 3, 5, 7). In SPRINT-PLAN.md, include a **Predecessors table**: **Order**, **Feature/Task**, **Predecessors**, and effort columns (Engineering Days, Design Days, Backend Eng Days). No task should start in a sprint before all its predecessors are done.

4. **Timeline and sprint length**  
   State where deadlines come from (e.g. deck, proposal, SOW). Define sprint length (e.g. 2 weeks = 10 working days) and how many sprints map to each phase or milestone (e.g. "Discovery = first 2 months", "First release = months 3–5" — use the project’s own phase names and dates).

5. **Sprint allocation**  
   A table: **Sprint** (number), **Calendar** (weeks/months from kickoff), **Phase or milestone**, **Tasks** (Order numbers), and **Eng D / Design D / Backend D** (and total) per sprint. Assign each task to the **earliest** sprint where **all its predecessors are done**; use parallel tracks to spread work. Ensure no sprint exceeds a feasible team size. Align sprint count and end dates with the stated timeline (e.g. "first milestone by month 4 → 8 two-week sprints").

6. **Team size per sprint**  
   A table: **Sprint**, **Eng D**, **Design D**, **Backend D**, **Eng FTE**, **Design FTE**, **Backend FTE**, **Team size (total FTE)**. FTE per discipline = (days in sprint ÷ working days per sprint), rounded up so the work fits. Add a **Suggested team** column or bullets per sprint (e.g. "2 Eng, 1 Design, 3 Backend") so the proposal can size the team to meet the deadlines.

7. **Optional: later phases**  
   If the estimate includes later phases or post–first-milestone work, add a compact sprint/team view for those phases.

8. **Summary**  
   One short paragraph: purpose of **order**, **parallel tracks**, and **predecessors**; number of sprints to the first (or key) milestone; team size range (min–max and peak); and that velocity/non-project time are applied in the Estimation Tool **Team** tab, not in the backlog.

The estimate table (or CSV) should include **Order** and **Parallel** columns and list tasks in **development order**; reference the sprint plan in the same folder (e.g. "Predecessors and sprint plan: see SPRINT-PLAN.md").

## Reference

For the full ArcTouch alignment table (Assumptions tab, velocity, backend, accessibility, deprecated references), see [reference.md](references/reference.md).
