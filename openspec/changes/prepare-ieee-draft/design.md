## Context

Overleaf imports an archive rooted at the main TeX file. Github stores that same manuscript as modular source so edits can be reviewed.

## Goals / Non-Goals

**Goals:** IEEE conference structure, an upload-ready source archive, and traceable research claims.

**Non-Goals:** Running a household trial or implementing the proposed household MCP server.

## Decisions

- Use IEEEtran conference mode and BibTeX. Keep body sections separate from the entry point.
- Use the same input files in GitHub and the Overleaf ZIP.
- Describe versioned snapshots and read-only allocation in the manuscript. Keep evaluation outcomes pending until the replay study is run.

## Risks / Trade-offs

- [ZIP drift] Rebuild the ZIP from the paper directory whenever submission sources change.
- [Unverified empirical claims] Explicitly label experiments as planned and document the baseline comparisons.
