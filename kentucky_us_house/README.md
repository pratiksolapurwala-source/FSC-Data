# Kentucky U.S. House of Representatives — General Election Results (2020, 2022)

Columns: `county, precinct, office, district, party, candidate, votes`

## Files

- `kentucky_2022_ushouse_general.csv` — **precinct-level** results, 9,240 rows.
  Source: MIT Election Data and Science Lab (MEDSL), `2022-elections-official`
  repository, Kentucky precinct file (`individual_states/2022-ky-local-precinct-general.zip`),
  filtered to `office == "US HOUSE"`.
  https://github.com/MEDSL/2022-elections-official

- `kentucky_2020_ushouse_general.csv` — **district-level** results only, 16 rows
  (6 districts). `county` and `precinct` are blank: MEDSL's precinct-level 2020
  returns were removed from GitHub (the `2020-elections-official` repo's
  README now says "We are no longer maintaining 2020 precinct data in this
  repository" and points to Harvard Dataverse instead), and Harvard Dataverse
  could not be reached from this environment. OpenElections' Kentucky repo
  has no 2020 folder at all (its year list jumps from 2019 to 2023). Source:
  MEDSL "U.S. House 1976–2022" dataset, redistributed via the R4DS
  TidyTuesday project:
  https://github.com/rfordatascience/tidytuesday/blob/main/data/2023/2023-11-07/readme.md
  (original: https://doi.org/10.7910/DVN/IG0UN2)

## Notes

- `party` values are as reported by each source (not normalized between the
  two files — 2022 uses MEDSL's `party_detailed`; 2020 uses MEDSL's `party`).
- Kentucky was never assigned Census-defined Voting Tabulation Districts
  (VTDs), which is part of why precinct-level 2020 sourcing for this state is
  thin outside of Dataverse-hosted, non-GitHub datasets.
- If true precinct-level 2020 figures are needed, MEDSL's Harvard Dataverse
  page ("Precinct-Level Returns 2020") is the authoritative source but could
  not be fetched from this environment — same limitation encountered with
  the Mississippi Secretary of State site in this session.
