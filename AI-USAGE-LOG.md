### Entry 01 — Initial Audit

Tool: ChatGPT (GPT-6)

Date: 2026-10-26

Stage: Initial Audit

Prompt: 
"Analyze the ada-08-agent-ready-repository repository without modifying any files. Evaluate its agent-readiness using the eight specified dimensions: Entry Point & Navigation, Agent Instructions, Build / Run / Test, Architecture Boundaries, Requirements & Traceability, Automation & Guardrails, Testability & Evidence, and Safety & Permissions. Assign scores from 0 to 5, calculate weighted scores, identify evidence and main gaps, and summarize the total score and top three friction points."

AI contribution: 
The agent inspected the repository documentation and available evidence, including README.md, AGENTS.md, REQUIREMENTS.md, SPEC.md, TASKS.md, and ARQUITECTURE.md. Produced a weighted audit scoring each of the eight dimensions, for a total of 73/100. Identified the incorrect repository clone URL in the README, limited evidence of automated enforcement, and the lack of consolidated requirement-linked verification evidence as the top three friction points.

Student decision: 
The student used the audit as an initial assessment of the repository's readiness for AI coding agents.

Impact: 
N/A

### Entry 02 — AGENTS.md design
Tool: ChatGPT
Date: 2026-10-26
Stage: Initial Audit

Prompt: 
Explain how to add a linting command to the ada-08-agent-ready-repository project and improve the AGENTS.md instructions to include linting.

AI contribution: 
Recommended Ruff as the Python linter, provided installation and execution commands, suggested a pyproject.toml configuration, and drafted an AGENTS.md section documenting linting procedures and reporting requirements.

Student decision: 
The student reviewed the proposed Ruff configuration and commands, determine whether they fit the repository, and apply the changes only after verifying the existing configuration and project requirements.

Impact: 
Established a practical approach for integrating automated Python linting into the repository's development workflow, improving code-quality checks and clarifying validation expectations for AI coding agents.

### Entry 03 — Guardrail
Tool: ChatGPT
Date: 2026-10-26
Stage: Guardrail

Prompt:
"Review (do not modify) the repository https://github.com/AlexSvS/ada-08-agent-ready-repository.git. Once analyzed, select at least one critical rule and turn it into an automated gate. The mechanism can be a hook from the coding agent, pre-commit, script, CI, or verification wrapper.

Here are the rules, you can choose one:
- Do not leave broken tests
- Don't add secrets"

AI contribution: 
Proposed the scripts/check_repo_contract.py script to verify that required repository files exist, report missing files, and return an appropriate exit code. Adapted the required file list to match the repository's actual structure and naming conventions. Also provided a GitHub Actions workflow to execute the check automatically on pushes and pull requests.

Student decision: 
The student adopted the proposed guardrail and placed the validation script in scripts/check_repo_contract.py.

Impact: Modified scripts/check_repo_contract.py.

### Entry 04 — Implicit knowledge
Tool: ChatGPT
Date: 2026-10-26
Stage: Implicit knowledge

Prompt:
""Review (do not modify) the before-agent-run.md in repository https://github.com/AlexSvS/ada-08-agent-ready-repository.git. Once analyzed, check what knowledge was implied during the generation of the TASK_UNDER_TEST.md"

AI contribution: 
Discovered that "pytest" failed and the agent executed "python -m pytest" instead.

Student decision: 
The student modified the files README.md, AGENTS.md and subsecuent files to include "python -m pytest".

Impact: Modified README.md, AGENTS.md.

### Entry 05 — Readiness improvement report
Tool: ChatGPT (GPT-6)
Date: 2026-10-27
Stage: Readiness Improvement

Prompt:
Based on the revised repository readiness audit score, help create readiness-improvement-report.md for ada-08-agent-ready-repository.

AI contribution:
ChatGPT drafted a readiness improvement report using the revised score of 85/100. It documented the weighted scores for all eight audit dimensions, supporting evidence, main gaps, recognized improvements, and a prioritized improvement plan. The report also proposed acceptance criteria for repository validation, CI enforcement, requirements traceability, and agent safety boundaries.

Student decision:
The student reviewed the proposed report, verified that its evidence matches the current repository state, and incorporates the content into readiness-improvement-report.md.

Impact:
The report consolidates the readiness audit into an actionable improvement plan. It identifies automated enforcement, safety boundaries, and traceability as the main remaining friction points while documenting the repository improvements that support the revised 85/100 score.