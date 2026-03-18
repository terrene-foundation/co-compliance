# CO for Regulatory Compliance (COComp)

Structured human-AI collaboration for regulatory compliance analysis. Built on the [Cognitive Orchestration](https://terrene.foundation/standards/co/) (CO) methodology.

**CO Specification**: v1.1 (CC BY 4.0, [Terrene Foundation](https://terrene.foundation))

## What This Is

A CO domain application for compliance officers who need to analyze regulations, map requirements to controls, identify gaps, produce compliance reports, and prepare for audits.

COComp does not replace the compliance officer's judgment. It structures the analysis process, ensures completeness, and produces traceable documentation. The compliance officer makes every applicability determination, risk acceptance decision, and compliance status judgment.

**What COComp produces:**
- Requirements registers extracted from regulatory texts with exact citations
- Control mappings connecting requirements to organizational controls
- Gap analyses with severity ratings and remediation recommendations
- Compliance reports for management, board, and regulatory audiences
- Audit documentation packages with organized evidence and control narratives

**What COComp does not do:**
- Provide legal advice (it identifies requirements; legal counsel interprets obligations)
- Make compliance determinations autonomously (the human decides)
- Guarantee regulatory coverage (regulations change; verify currency against official sources)

## Quick Start

### Option A: Claude Code (CLI)

```bash
git clone https://github.com/terrene-foundation/co-compliance.git
cd co-compliance
claude
```

Then type `/start`.

The AI will introduce itself, explain the five-phase workflow, and ask about your compliance project. Describe what you need in plain language: "I need to assess our GDPR readiness" or "We have a SOC 2 audit in three months and need to prepare."

### Option B: Claude Desktop Cowork (Plugin)

**What you need:**
- Claude Desktop with Cowork support
- A Claude Pro, Max, or Team subscription

**Step 1: Download the repository**

Go to [github.com/terrene-foundation/co-compliance](https://github.com/terrene-foundation/co-compliance). Click the green **"Code"** button, then click **"Download ZIP"**. Unzip it and move the folder to your Documents.

**Step 2: Install the plugin**

1. Open Claude Desktop
2. Switch to the **"Cowork"** tab
3. Click **"Customize"** in the left sidebar
4. Click **"Browse plugins"**
5. Click **"Load from folder"** and navigate to the `plugin` folder inside your downloaded folder

**Step 3: Open and start**

1. In Cowork, click **"Open folder"** and select the root `co-compliance` folder (the one containing `CLAUDE.md`)
2. Type `/co-compliance:start` in the chat

### What happens after `/start`

The AI will:
- Greet you and explain the five-phase compliance workflow
- Ask what regulations or frameworks are in scope
- Ask about your timeline (audit date, regulatory deadline)
- Ask what output you need (report, gap analysis, audit package)
- Check for any existing workspace and offer to create one if needed

Answer in plain language. You do not need to use technical terms or special commands.

### What a successful start looks like

You will see:
- The AI introducing itself as a compliance analysis assistant
- A summary of the five workflow phases and the domain-specific skills
- Questions about your compliance project
- A workspace check with an offer to create one

If you see all of this, you are set up correctly. If the AI does not seem to know about compliance analysis or the CO workflow, see [Troubleshooting](#troubleshooting) below.

## Workflow

### Core Phases

| Phase | What Happens | CLI Command | Cowork Skill |
|-------|-------------|-------------|--------------|
| **01 Research** | Identify applicable regulations, research requirements | `/analyze` | `/co-compliance:analyze` |
| **02 Plan** | Create assessment plan; stops for your approval | `/plan` | `/co-compliance:plan` |
| **03 Execute** | Work through assessment tasks one at a time | `/execute` | `/co-compliance:execute` |
| **04 Review** | Quality check and adversarial critique | `/review` | `/co-compliance:review` |
| **05 Finalize** | Polish reports, validate evidence, prepare deliverables | `/finalize` | `/co-compliance:finalize` |

### Domain-Specific Skills

These can be used at any phase, whenever you need them:

| CLI Command | Cowork Skill | What It Does |
|-------------|-------------|--------------|
| `/analyze-regulation` | `/co-compliance:analyze-regulation` | Analyze a regulation and extract a structured requirements register |
| `/map-controls` | `/co-compliance:map-controls` | Map requirements to your organization's controls |
| `/assess-gaps` | `/co-compliance:assess-gaps` | Identify and prioritize compliance gaps |
| `/draft-report` | `/co-compliance:draft-report` | Draft a compliance report for any audience |
| `/prep-audit` | `/co-compliance:prep-audit` | Prepare audit documentation packages |

### Utility Skills

| CLI Command | Cowork Skill | What It Does |
|-------------|-------------|--------------|
| `/ws` | `/co-compliance:ws` | Show workspace status |
| `/wrapup` | `/co-compliance:wrapup` | Save session notes before closing |
| `/checkpoint` | `/co-compliance:checkpoint` | Review progress and learning |

## Agents

### Domain Specialists

| Agent | What It Does |
|-------|-------------|
| **regulation-analyst** | Reads regulatory texts with precision. Extracts every obligation as a testable requirement with exact citations, applicability criteria, and cross-references. |
| **control-mapper** | Connects requirements to your organization's controls. Assesses coverage (full, partial, none, compensating) with documented rationale for each mapping. |
| **gap-assessor** | Identifies where your controls fall short. Classifies gaps by severity, assesses regulatory exposure and business impact, recommends specific remediation. |
| **report-drafter** | Produces compliance reports structured for the target audience (board, management, regulators, auditors) with evidence references throughout. |
| **audit-preparer** | Organizes evidence into audit-ready packages. Drafts control narratives, responds to auditor requests, and flags evidence gaps before auditors find them. |

### Management

| Agent | What It Does |
|-------|-------------|
| **todo-manager** | Tracks compliance tasks in the workspace |
| **gh-manager** | Manages GitHub issues for compliance milestones |

## Hard Refusals

COComp will refuse certain requests outright. These are safety constraints, not limitations to work around.

| Request | Response | Reason |
|---------|----------|--------|
| Misrepresent compliance status | **REFUSE** | Creates legal exposure and endangers the organization |
| Omit a known regulatory requirement | **REFUSE** | Produces incomplete analysis that causes audit failures |
| Fabricate audit evidence | **REFUSE** | Fabricating evidence is fraud |
| Provide legal advice | **DECLINE** | Compliance analysis identifies requirements; legal counsel interprets obligations |
| Skip validation phases | **REFUSE** | Each phase catches different classes of errors |
| Work without human direction | **REFUSE** | The compliance officer makes all judgment calls |

## Limitations

| Concern | What To Know |
|---------|-------------|
| **Regulatory currency** | The AI's knowledge has a training cutoff. Regulations enacted or amended after that date may not be reflected. Always verify against official sources (EUR-Lex, Federal Register, official gazettes) before relying on any citation. |
| **Jurisdiction specificity** | COComp covers major regulatory frameworks (GDPR, CCPA, HIPAA, SOX, PCI DSS, DORA, NIS2, AI Act) with general knowledge. Jurisdiction-specific interpretations, enforcement guidance, and local transpositions may require additional research. |
| **Organizational context** | COComp does not know your organization's specific controls, processes, or risk appetite. You must provide this context. The AI will ask for it when needed. |
| **Legal advice boundary** | COComp identifies what regulations require. It does not interpret legal obligations, assess liability, or recommend legal strategy. For those questions, consult legal counsel. |
| **Evidence verification** | COComp can reference evidence you describe but cannot independently verify that evidence exists, is authentic, or covers the audit period. Evidence verification remains a human responsibility. |
| **Completeness guarantee** | No compliance analysis tool can guarantee 100% coverage. Use COComp as a structured aid, not as the sole basis for compliance determinations. |

## File Structure

<details>
<summary>Click to expand the full file tree</summary>

```
co-compliance/
  CLAUDE.md                    # Master directive with compliance rules
  LICENSE                      # Apache 2.0
  .claude/
    agents/
      domain/                  # 5 compliance specialists
        regulation-analyst.md
        control-mapper.md
        gap-assessor.md
        report-drafter.md
        audit-preparer.md
      management/              # Task tracking
        todo-manager.md
        gh-manager.md
    commands/                  # 14 CLI commands
      start.md
      analyze.md
      plan.md
      execute.md
      review.md
      finalize.md
      analyze-regulation.md
      map-controls.md
      assess-gaps.md
      draft-report.md
      prep-audit.md
      ws.md
      wrapup.md
      checkpoint.md
    rules/                     # Guardrail rules
      domain-integrity.md
      communication.md
  plugin/                      # Cowork plugin
    .claude-plugin/plugin.json
    CLAUDE.md
    skills/                    # 14 skills
      start/
      analyze/
      plan/
      execute/
      review/
      finalize/
      analyze-regulation/
      map-controls/
      assess-gaps/
      draft-report/
      prep-audit/
      ws/
      wrapup/
      checkpoint/
    agents/                    # Same agents, packaged for plugin
      domain/
      management/
  workspaces/
    _template/                 # Workspace template
      01-research/
      02-planning/
      03-work/
      04-review/
      05-output/
      journal/
      todos/
```

</details>

## The Five CO Layers

| Layer | What It Does | In COComp |
|---|---|---|
| **L1 Intent** | Specialized agents with domain knowledge | 5 compliance specialists + 2 management agents |
| **L2 Context** | Institutional knowledge hierarchy | `CLAUDE.md` with regulatory frameworks, terminology, compliance standards |
| **L3 Guardrails** | Hard and soft enforcement | Hard refusals for misrepresentation, omission, fabrication; rules in `rules/` |
| **L4 Instructions** | Structured workflow with gates | 5 phases + 5 domain skills + approval gates |
| **L5 Learning** | Knowledge that compounds | `journal/`, `/checkpoint`, `/wrapup` |

## Troubleshooting

**The AI does not seem to know about compliance analysis or the CO workflow.**
You may have opened the wrong folder. In Cowork, click "Open folder" and make sure you select the root folder (the one containing `CLAUDE.md`), not the `plugin` subfolder.

**Skills like `/co-compliance:start` do not work.**
The plugin may not be loaded. Go to the Cowork tab, click "Customize", and check that `co-compliance` appears in the plugin list. If not, click "Browse plugins" > "Load from folder" and select the `plugin` folder.

**The AI says it cannot find files or workspaces.**
Make sure you unzipped the download fully. On Mac, double-clicking the ZIP should unzip it. On Windows, right-click and choose "Extract All." If the folder structure looks like `co-compliance/co-compliance/CLAUDE.md` (nested), move the inner folder out and use that.

**The AI lost context between sessions.**
Before closing a session, type `/wrapup` (CLI) or `/co-compliance:wrapup` (Cowork). This saves progress including which regulations were analyzed, what gaps were found, and what decisions the compliance officer made. When you start a new session, type `/start` (or `/co-compliance:start`) to reload context.

**The AI is citing an outdated version of a regulation.**
COComp's regulatory knowledge has a training cutoff. If a regulation has been amended recently, tell the AI: "This regulation was amended on [date]. The current version is [version]." The AI will flag its uncertainty when it detects potential currency issues, but it cannot independently check for amendments published after its training data.

## License

- **Template code**: Apache 2.0
- **CO Methodology**: CC BY 4.0, Terrene Foundation

## Links

- [Terrene Foundation](https://terrene.foundation)
- [CO Specification](https://terrene.foundation/standards/co/) (CC BY 4.0)
- [CO Template](https://github.com/terrene-foundation/co-template) -- build your own CO application
- [COR (Research)](https://github.com/terrene-foundation/co-research) -- CO for academic research
- [COF (Finance)](https://github.com/terrene-foundation/co-finance) -- CO for finance education
