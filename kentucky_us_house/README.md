# Kentucky U.S. House of Representatives — General Election Results (1992–2022)

Columns: `county, precinct, office, district, party, candidate, votes`

## Files

| Year | Granularity | Rows | Source |
|------|-------------|------|--------|
| 1992 | county-level | 301 | Kentucky State Board of Elections official report (user-supplied text export) |
| 1994 | county-level | 252 | Kentucky State Board of Elections official report (user-supplied text export) |
| 1996 | county-level | 266 | Kentucky State Board of Elections official report (user-supplied text export) |
| 1998 | county-level | 286 | Kentucky State Board of Elections official report (user-supplied text export) |
| 2000 | county-level | 349 | Kentucky State Board of Elections official report (user-supplied text export) |
| 2020 | county-level | 315 | Kentucky Secretary of State official results report (user-supplied PDF) |
| 2022 | **precinct-level** | 9,240 | MEDSL `2022-elections-official` (GitHub) |

## Sources

- 1992–2000: plain-text exports of the Kentucky State Board of Elections'
  "OFFICIAL"/canvass election night tally reports, supplied by the user
  (`92usrep.txt`, `94gen_USRep.txt`, `96Gen_usrep1.txt`, `98Gen_usrep.txt`,
  `00Gen_Statewidebycounty.txt`), since this environment can't reach
  elect.ky.gov/sos.ky.gov directly. Every district's county-level vote counts
  were cross-checked against that district's own printed state total (all
  reconciled exactly), and further cross-validated against the MEDSL
  "U.S. House 1976–2022" dataset (which independently confirmed every
  candidate's statewide total for all five years).
- 2020: Kentucky Secretary of State's official 2020 general election results
  report (user-supplied PDF); all 6 districts reconciled exactly against
  certified state totals.
- 2022: MEDSL `2022-elections-official` GitHub repository, Kentucky precinct
  file, filtered to `office == "US HOUSE"`.
  https://github.com/MEDSL/2022-elections-official

## Notes

- The 2000 source file did not print party labels directly (unlike 1992–1998,
  which had explicit `DEM`/`REP`/`REF`/etc. header rows) — party affiliations
  for 2000 candidates were taken from the MEDSL 1976–2022 dataset, the same
  source used to independently confirm every year's statewide totals.
- 1994's official source file contained two slightly different vote counts
  for CD3 (Jefferson County) — an initial tally and a second, marginally
  different one appearing later in the same file. The first tally was used,
  since it matches MEDSL's confirmed final official totals exactly; the
  second entry does not and is presumed to be a preliminary or superseded
  count that was left in the source export.
- `party` values are not normalized across years/files (e.g. `WRITE-IN` vs
  `WRI` abbreviations in the raw sources were expanded to full labels
  consistently here, but naming otherwise follows what each source used).
- Kentucky's congressional district boundaries shifted between decennial
  redistricting cycles (e.g. Lawrence County appears in CD4 in 1992/1994 but
  in CD5 from 1996 onward) — this is reflected faithfully in the per-year
  district assignments, not an error.
