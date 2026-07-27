# Ohio U.S. House of Representatives — General Election Results (2004, 2022)

Columns: `county, precinct, office, district, party, candidate, votes`

## Files

- `ohio_2022_ushouse_general.csv` — **precinct-level** results, 17,938 rows.
  Source: MIT Election Data and Science Lab (MEDSL), `2022-elections-official`
  repository, Ohio precinct file (`individual_states/2022-oh-local-precinct-general.zip`),
  filtered to `office == "US HOUSE"`.
  https://github.com/MEDSL/2022-elections-official

- `ohio_2004_ushouse_general.csv` — **district-level** results only, 39 rows
  (18 districts). `county` and `precinct` columns are left blank because no
  county- or precinct-level breakdown for the 2004 Ohio U.S. House race was
  available from an accessible source (Ohio SOS's historical results page and
  Harvard Dataverse were unreachable from this environment; OpenElections'
  Ohio repo only has a 2004 primary file, not general). Source: MEDSL "U.S.
  House 1976–2022" dataset, redistributed via the R4DS TidyTuesday project.
  https://github.com/rfordatascience/tidytuesday/blob/main/data/2023/2023-11-07/readme.md
  (original: https://doi.org/10.7910/DVN/IG0UN2)

## Notes

- `party` values are as reported by each source (not normalized between the
  two files — 2022 uses MEDSL's `party_detailed`, 2004 uses MEDSL's `party`).
- 2022 write-in votes for Ohio are only reported at the county level by the
  state (not per precinct); MEDSL records these with precinct name
  `COUNTY FLOATING`.
- If true county-level 2004 figures are needed, the Ohio Secretary of State's
  archived canvass (https://www.ohiosos.gov/elections/election-results-and-data/2004-elections-results/)
  is the authoritative source but could not be fetched from this environment.
