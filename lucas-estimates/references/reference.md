# ArcTouch estimation — reference

Detailed alignment with ArcTouch standards (from PRD §5b and Estimation Tool).

## ArcTouch standard ↔ application

| ArcTouch standard | Application |
|-------------------|-------------|
| **Assumptions tab [Owner: PM]** | Project-level assumptions (platform, region/GEO, integrations, SEO, content, design, accessibility, GDPR) in PRD or equivalent. Populate the Estimation Tool Assumptions tab from the PRD and the proposal narrative. |
| **Product Backlog and Estimates** | Columns: **Epic**, **Feature/Task**, **Scope Assumptions**, **Risks**, **Who**. Matches Estimation Tool. Effort: Engineering Days, Design Days, Backend Eng Days — T-shirt sizes only. |
| **Engineering Days / Design Days** | Single-point (realistic) estimates per row. Estimation Tool (2025) may use Low/High; map single value to Low/High per ArcTouch guidance. Do not add buffer in raw rows; velocity is applied in the Team tab. |
| **Do not include testing or bug fixing in line estimates** | QA, UAT, and Launch are team staffing, not separate backlog rows. Raw estimates = dev + code review only. Testing and bug fixing are projected from historical data in the process. |
| **Do not adjust for velocity in the estimate rows** | Velocity (e.g. ~60% dev+review, 10% test, 20% bug fixing, 10% non-project) is applied in the **Team** tab and capacity planning, not in backlog rows. No buffer in the numbers. |
| **Backend Estimates** | **Backend Eng Days** column for API/integration (e.g. CRM, middleware). Same logic as the Estimation Tool Backend Estimates tab. |
| **Who** | Values: **eng**, **design**, **eng & design** — determines which of Engineering Days / Design Days apply per row. |
| **Accessibility** | Not a separate line item. WCAG 2.1 AA in scope via design system and implementation. Use Eng/Design % (A11y) in Estimation Tool if tracking separately. |
| **Sanity check** | After pasting into "2. Estimates" or the Estimation Tool, use the **Team** tab and **Sprint and Capacity Planner** (*Estimating a Project*) to validate duration and budget. |

## Template spreadsheet

- **Reference template (do not edit):** [ArcTouch Estimation Tool — template](https://docs.google.com/spreadsheets/d/1qPm7HX2VPH6k4JEuDwDkmIOOnXNXP9ePioYBIiFiDzo/edit?gid=1383075938#gid=1383075938) — duplicate and rename to client/project name before adding estimates.

## Notion references

- [Estimating a Project](https://www.notion.so/5c486ab577b94e3d9a3085bafd772ddc) — process overview; links to Estimation Tool and Sprint and Capacity Planner.
- [Estimation Tool (2025)](https://www.notion.so/2b5db8adf6118019b983cf7a895c4a51) — main spreadsheet/tool (Assumptions, Product Backlog and Estimates, Team tab, Backend Estimates).
- [Estimation Guide](https://www.notion.so/429b2e55b1f04065a29cbbbb1fb6bd81) — detailed guidance.
- *Estimation Template* — referenced in process; use the template spreadsheet above (duplicate first; never edit the original).

Deprecated / client-specific: "Estimation tool for Grey projects," "The Estimation Process for Grey NY projects" — use the standard Estimation Tool (2025) and Estimating a Project process.
