# Conference Draft

## Purpose

Define the deliverables for the DIC4 IEEE draft and its GitHub specification.

## Requirements

### Requirement: Importable IEEE manuscript
The repository SHALL supply modular IEEEtran conference sources, a BibTeX bibliography, and an Overleaf source archive.

#### Scenario: Open the archive
- **WHEN** the reviewer imports the archive as an Overleaf project
- **THEN** `main.tex` is at the project root with its section files and bibliography available.

### Requirement: Explicit MCP tool contract
The manuscript SHALL define the read-only MCP tools, the snapshot version check, and the allocation trace fields.

#### Scenario: Request a plan from a stale snapshot
- **WHEN** the proposed planning tool receives a stale snapshot version
- **THEN** it returns a stale-snapshot error so the client can retrieve the current version.

### Requirement: Planned evaluation
The manuscript SHALL identify the replay baselines and metrics and explicitly identify the evaluation as prospective.

#### Scenario: Inspect empirical claims
- **WHEN** the reviewer reads the evaluation and conclusion
- **THEN** no study outcomes are described as observed.

### Requirement: Automated OpenSpec validation
The repository SHALL configure GitHub Actions to run strict OpenSpec validation on pushes and pull requests.

#### Scenario: Submit a branch update
- **WHEN** a push or pull request triggers the workflow
- **THEN** the workflow runs strict validation and reports the command exit status.
