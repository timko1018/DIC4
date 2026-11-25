## ADDED Requirements

### Requirement: Make allocation traces auditable
The manuscript SHALL specify the ordering and amount rule, and include a worked valid snapshot and a stale-snapshot outcome.

#### Scenario: Review method
- **WHEN** an earlier eligible batch has 200 g and a later eligible batch has 300 g for a 350 g request
- **THEN** the trace assigns 200 g and 150 g in that order and reports zero shortfall.
