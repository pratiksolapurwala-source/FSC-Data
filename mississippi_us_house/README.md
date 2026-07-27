# Mississippi U.S. House of Representatives — General Election Results (1992–2010)

Columns: `county, precinct, office, district, party, candidate, votes`

Granularity varies by year depending on what was available:

| Year | Granularity | Rows | Source |
|------|-------------|------|--------|
| 1992 | district only | 13 | MEDSL "U.S. House 1976–2022" |
| 1994 | district only | 11 | MEDSL "U.S. House 1976–2022" |
| 1996 | district only | 22 | MEDSL "U.S. House 1976–2022" |
| 1998 | district only | 17 | MEDSL "U.S. House 1976–2022" |
| 2000 | district only | 18 | MEDSL "U.S. House 1976–2022" |
| 2002 | district only | 17 | MEDSL "U.S. House 1976–2022" |
| 2004 | **county-level** | 246 | Mississippi Secretary of State official certification |
| 2006 | **county-level** | 217 | OpenElections (`openelections-data-ms`) |
| 2010 | **precinct-level** | 9,268 | OpenElections (`openelections-data-ms`) |

`county` and `precinct` are left blank where that granularity wasn't available.

## Sources

- MEDSL "U.S. House 1976–2022" (district-level, all years 1992–2004), redistributed
  via R4DS TidyTuesday:
  https://github.com/rfordatascience/tidytuesday/blob/main/data/2023/2023-11-07/readme.md
  (original: https://doi.org/10.7910/DVN/IG0UN2)
- OpenElections Mississippi data repo (county-level for 2006, precinct-level for 2010):
  https://github.com/openelections/openelections-data-ms
- Mississippi Secretary of State's official 2004 general election certification
  PDFs (county-level, one per congressional district: `CertCD1.pdf`–`CertCD4.pdf`,
  https://sos.ms.gov/elections/electionresults/2004General/Certication%20Results/),
  supplied by the user and transcribed here since this environment could not
  reach sos.ms.gov directly. Each district's county-level vote counts were
  cross-checked against that district's own certified state totals (candidate
  votes must sum exactly to the certified statewide total); CD1 and CD4
  reconcile exactly, CD2 and CD3 reconcile to within 1 vote (likely a rounding
  artifact in the original document). Party affiliations for the 2004
  candidates (not printed on the certification PDFs) were taken from the MEDSL
  1976–2022 dataset, cross-validated against the same certified state totals.

## Notes

- OpenElections does not have a Mississippi *general* election data folder for
  1992–2002, and its 2004 folder only contains primary election files — so
  those years fall back to MEDSL's district-level totals. 2004 was later
  upgraded to county-level using the official SOS certification PDFs (see
  Sources above).
- `party` values are as reported by each source and are not normalized across
  years (MEDSL uses full names like `DEMOCRAT`/`REPUBLICAN`; the 2006 file
  uses abbreviations like `DEM`/`REP`/`LBT`; the 2010 file uses full names
  like `Democrat`/`Republican`/`Reform`).
- The 2010 precinct file's raw county count (109) is higher than Mississippi's
  82 actual counties, likely reflecting minor naming/formatting inconsistencies
  in the underlying county-converted source data — left as-is rather than
  guessing at corrections.
- A separate `..._tallahatchie__precinct.csv` file in the OpenElections repo
  for 2010 duplicates rows already present in the main precinct file and was
  not merged in.
