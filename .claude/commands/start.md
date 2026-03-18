---
name: start
description: New user orientation. Explains the COComp workflow, checks workspace state, and asks about the compliance project.
---

# COComp Orientation

Welcome the user to this CO for Regulatory Compliance (COComp) workspace. This is a structured methodology for human-AI collaboration on compliance analysis.

## First, check the workspace

1. Look for a `workspaces/` directory in the current project folder
2. If it exists, list any active projects (non-template subdirectories)
3. If it does not exist, explain that the user needs to set up a workspace:
   ```
   cp -r workspaces/_template workspaces/my-project
   ```

## Then explain the workflow

This COComp workspace has five core phases and five domain-specific skills:

| Phase | What happens | Command |
|-------|-------------|---------|
| **01 Research** | Identify applicable regulations, research requirements | `/analyze` |
| **02 Plan** | Create a compliance assessment plan; stops for your approval | `/plan` |
| **03 Execute** | Work through the assessment one task at a time | `/execute` |
| **04 Review** | Quality check, adversarial critique of compliance work | `/review` |
| **05 Finalize** | Polish reports, validate evidence, prepare final deliverables | `/finalize` |

Domain-specific commands (usable at any phase):

| Command | Purpose |
|---------|---------|
| `/analyze-regulation` | Analyze a specific regulation and extract requirements |
| `/map-controls` | Map requirements to organizational controls |
| `/assess-gaps` | Identify gaps between requirements and controls |
| `/draft-report` | Draft a compliance report |
| `/prep-audit` | Prepare audit documentation package |

Utility commands: `/ws` (status), `/wrapup` (save progress), `/checkpoint` (review learning).

## Then ask

1. What is the compliance project? (e.g., GDPR readiness assessment, SOC 2 preparation, regulatory gap analysis)
2. Which regulations or frameworks are in scope?
3. Is this new or continuing existing work?
4. What is the target output? (compliance report, gap analysis, audit package, requirements register)
5. What is the timeline? (audit date, regulatory deadline, management reporting date)

Based on answers, recommend the next command to run.

## If continuing existing work

Read `.session-notes` if it exists. Summarize what was accomplished and what the next step is.
