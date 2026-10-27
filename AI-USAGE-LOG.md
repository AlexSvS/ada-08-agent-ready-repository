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

Prompt: Explain how to add a linting command to the ada-08-agent-ready-repository project and improve the AGENTS.md instructions to include linting.

AI contribution: Recommended Ruff as the Python linter, provided installation and execution commands, suggested a pyproject.toml configuration, and drafted an AGENTS.md section documenting linting procedures and reporting requirements.

Student decision: The student reviewed the proposed Ruff configuration and commands, determine whether they fit the repository, and apply the changes only after verifying the existing configuration and project requirements.

Impact: Established a practical approach for integrating automated Python linting into the repository's development workflow, improving code-quality checks and clarifying validation expectations for AI coding agents.