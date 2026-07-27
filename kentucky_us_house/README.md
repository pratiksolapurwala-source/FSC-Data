# Kentucky U.S. House of Representatives — General Election Results (2020, 2022)

Columns: `county, precinct, office, district, party, candidate, votes`

## Files

- `kentucky_2022_ushouse_general.csv` — **precinct-level** results, 9,240 rows.
  Source: MIT Election Data and Science Lab (MEDSL), `2022-elections-official`
  repository, Kentucky precinct file (`individual_states/2022-ky-local-precinct-general.zip`),
  filtered to `office == "US HOUSE"`.
  https://github.com/MEDSL/2022-elections-official

- `kentucky_2020_ushouse_general.csv` — **county-level** results, 315 rows across
  all 6 congressional districts. Source: Kentucky Secretary of State's official
  "2020 General Election Results" report (Michael G. Adams, Secretary of State),
  supplied by the user as a PDF since this environment could not reach
  elect.ky.gov / sos.ky.gov directly. Each district's county-level vote counts
  were cross-checked against that district's own certified state totals
  (candidate votes must sum exactly to the certified statewide total) — all
  6 districts reconciled exactly.

## Notes

- `party` values are as reported by each source (not normalized between the
  two files — 2022 uses MEDSL's `party_detailed`; 2020 uses the party labels
  printed in the official KY SOS report, e.g. `REPUBLICAN`/`DEMOCRATIC`/
  `LIBERTARIAN`/`POPULIST`/`WRITE-IN`).
- Kentucky was never assigned Census-defined Voting Tabulation Districts
  (VTDs), which is part of why precinct-level 2020 sourcing for this state is
  thin outside of Dataverse-hosted, non-GitHub datasets — MEDSL's precinct-level
  2020 file lives on Harvard Dataverse, unreachable from this environment, so
  county-level (from the official KY SOS report) is the finest granularity
  used here for 2020.
- CD3 (Jefferson County only) and the Jefferson County portion of CD4 both
  appear in the data — Jefferson County is split between congressional
  districts 3 and 4, so it has separate rows for each.
