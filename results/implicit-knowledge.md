# Implicit Knowledge Found
## IK-01
What: 
Pytest must be invoked through `python -m pytest -v` instead of `pytest -v` because the pytest executable is not available on the system PATH in PowerShell.

How was it discovered: When the agent ran `pytest -v` it failed with a command-not-found error.

Should this remain implicit?
NO

Where should it become explicit?
README.md / AGENTS.md / scripts / verify_repo.sh

## IK-02
What: 
A globally installed customer_search package from another project (ada-05-spec-driven-feature) can shadow the current project's source when running python -m customer_search. Additionally, PowerShell file-writing commands may introduce BOM or encoding artifacts that interfere with direct CLI verification.

How was it discovered: 
Direct CLI tests involving boolean IDs produced inconclusive results. Investigation identified a conflicting installed package and potential encoding artifacts from commands such as Set-Content and New-TemporaryFile. Pytest remained unaffected because the project's pyproject.toml configures the appropriate editable installation for test discovery.

Risk:
CLI verification may execute the wrong project's code or produce misleading results due to encoding differences. This can lead to false conclusions about the implementation's correctness and leave potential bugs undetected.

Remediation:
AGENTS.md + repository check.