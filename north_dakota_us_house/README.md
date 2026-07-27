# North Dakota U.S. House of Representatives — General Election Results (2022, 2024)

Columns: `county, precinct, office, district, party, candidate, votes`

North Dakota has a single, at-large congressional district, so `district` is
`AT-LARGE` for every row in both files.

## Files

- `north_dakota_2022_ushouse_general.csv` — **precinct-level**, 987 rows, all
  53 counties. Kelly Armstrong (R) vs. Cara Mund (Independent). Verified
  exactly against MEDSL's official dataset: Armstrong 148,399 / Mund 89,644 /
  Write-in 543 (total 238,586).

- `north_dakota_2024_ushouse_general.csv` — **precinct-level**, 1,048 rows,
  all 53 counties. Julie Fedorchak (R) vs. Trygve Hammer (D). Statewide sums:
  Fedorchak 249,101 / Hammer 109,231 / Write-in 1,455 (total 359,787), which
  is consistent with public reporting of the race (~69%/~30% split). This
  file predates MEDSL's public dataset coverage (which stops at 2022) and
  North Dakota's official results portal could not be reached from this
  environment, so this total could not be cross-checked digit-for-digit
  against an independent official source the way the 2022 file was.

Source: user-supplied CSVs, originally titled `north_dakota_2022_us_house_results.csv`
and `north_dakota_house_results.csv` (the latter renamed here to reflect that
it is 2024 data, based on the candidates listed).

## Notes

- Both files were checked for duplicate (county, precinct, party, candidate)
  rows — none found — and for full county coverage (53/53 in each).
- The 2022 source used `OTHER` as Cara Mund's party; normalized here to
  `INDEPENDENT` to match how MEDSL and other sources classify her candidacy.
- The 2024 source used `STATEWIDE` in the `district` column; normalized here
  to `AT-LARGE` for consistency with the 2022 file and with standard usage
  for North Dakota's single congressional district.
- Precinct counts differ slightly between the two years (398 distinct
  precincts in 2022 vs. 385 in 2024), reflecting normal precinct
  consolidation/renumbering between election cycles, not a data error.
