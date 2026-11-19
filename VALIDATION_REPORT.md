# Submission acceptance report

Checked on 2026-11-19. Numerical acceptance passed against the v4 manuscript and supplement identified in `manuscript.json`. The five scientific core source files are unchanged from the uploaded archive.

## Input and repairs

Uploaded archive: `active-information-engine.zip`, 3,881,064 bytes, SHA-256 `2e1e4f7465884d2a432b4f52b3216ae09bd4031b35d300c9e0569a305f82a6e6`.

The received archive omitted `CITATION.bib` and `docs/manuscript.json` despite listing them in `SHA256SUMS`. Both files were recovered from the local reference copy with exact matches to the original manifest hashes. The missing manuscript identifier otherwise caused every reproduction script to fail. The restored original tree passed all 134 original checksums before repairs.

Archive inspection found no absolute paths, parent traversal, duplicate entries, encrypted files, symlinks, or excessive expansion. Finder metadata and AppleDouble records were removed. The code review found no external network calls, dynamic code execution, credential access, or destructive file operations. Subprocess execution is limited to the named local reproduction scripts. Runtime paths are derived from the repository directory.

The saved-data audit was strengthened: it now verifies schedule counts and metadata, all plotted CSV fields against audited JSON, passive reference values, relative gain, slice, activation boundary, ridge, and zero-gain tables. Negative controls confirmed rejection of changed net/mechanical work that preserves the energy identity, a missing CSV row, and a NaN.

## Clean environments and dependencies

Two new CPython 3.11 virtual environments were created with system packages disabled and no user site packages. Official PyPI wheels were downloaded using system HTTPS, verified against PyPI SHA-256 values, and installed offline with hash checking. Direct pip HTTPS installation failed because of the available Python connection; secure downloads were used without disabling certificate checks.

The original NumPy 1.24.3, SciPy 1.11.1 and Matplotlib 3.7.2 versions were retained. PyPI release metadata reported advisory entries for Pillow 10.0.0 and fonttools 4.42.0. They were replaced by Pillow 13.0.0 and fonttools 4.68.0; the final twelve locked runtime packages returned no advisory entries in that check. Sources and before/after records are in `reports/dependency_advisories.json`. This check covers PyPI's known runtime-package advisories, not every possible vulnerability or the host operating system.

All twelve runtime and transitive versions are pinned in `requirements-lock.txt`. `requirements-macos-arm64.lock` adds hashes for the CPython 3.11 macOS arm64 wheels used here; other platforms should use the portable version lock. Environment and wheel records are in `reports/acceptance.json` and `reports/dependency_wheels.json`.

## SM IX B-D

All 11 comparisons passed at the supplement's reported precision:

| Quantity | Manuscript | Recomputed | Absolute difference |
|---|---:|---:|---:|
| IX B active J_net | 2.229314 | 2.229314356 | 3.56e-07 |
| IX B active J_mech | 2.971665 | 2.9716646464 | 3.54e-07 |
| IX B active C_sens | 0.74235 | 0.742350290406 | 2.9e-07 |
| IX B passive J_net | 0.528038 | 0.528038046012 | 4.6e-08 |
| IX B rho_N | 0 | 0 | 0 |
| IX B M_N_cross | 0.0874645 | 0.0874644670175 | 3.3e-08 |
| IX C c_cross | 0.00108146 | 0.00108145659425 | 3.41e-09 |
| IX C peak tau | 1.1283 | 1.12827718173 | 2.28e-05 |
| IX C peak net work | 2.48568 | 2.48568238547 | 2.39e-06 |
| IX C peak rho_N | 0 | 0 | 0 |
| IX D rho_N | 0.0405 | 0.0405023737832 | 2.37e-06 |

The ten scientific tests passed in both clean environments. The repaired dependency environment also passed the complete quick entry point: tests, benchmarks, 80 Fig. 2 cells, 119 Fig. 3 cells, plotting, and saved-data audit. Independent finite-persistence trend checks passed in the original clean numerical environment.

## Full Fig. 2 and Fig. 3 reproduction

The complete full entry point was run from scratch, including joint reoptimization at every cell and separately optimized passive references.

| Check | Fig. 2 | Fig. 3 |
|---|---:|---:|
| Grid cells | 1800 | 3321 |
| Maximum KKT residual | 1.03e-09 | 6.33e-08 |
| Maximum bidirectional net-work difference | 2.49e-14 | 1.07e-13 |
| Optimization elapsed seconds | 84.2 | 395.4 |

Fig. 2 has zero activation mismatches. Fig. 3's maximum independent mechanical-work discrepancy is 4.96e-13. Its maximizing persistence ranges from 0.897535347 to 1.36867932 across the 41 durations, consistent with the manuscript's approximately 0.90–1.37.

All 5,121 saved precision schedules were reevaluated; maximum saved-objective discrepancy was 0. The 120 independent Fig. 2 work checks had maximum error 4.62e-14. The conservative concavity-based objective-gap bound was at most 1.88e-05; it is an upper bound rather than an observed error. All seven full plotting CSVs match the input archive numerically with maximum difference zero.

Full figures were redrawn with the repaired dependencies and the full saved-data audit was rerun in that environment. Final quick and full PNGs were visually inspected for labels, clipping, legends and colorbars. The supplied PDF/SVG/PNG figures show physical and numerical reproduction, not pixel-identical manuscript artwork.

## Publication scope and limits

The user's later instruction authorizes a PUBLIC repository under `wwj666-oss/active-information-engine`, superseding the earlier private-only request. The account and absence of an existing same-name repository were checked before creation. The intended version tag is `v1.0.0-submission`.

Only reproduction code, generated numerical data, generated figures and documentation are included. Manuscript PDFs, historical drafts, local environment directories, caches, contact addresses and original working paths are excluded. No Zenodo deposit or integration was used. The original all-rights-reserved licensing decision is retained.

The implementation is a disclosed manuscript-based numerical reconstruction, not a claim to be the original author code. The two reference PDFs were verified locally against their recorded SHA-256 identifiers and are not redistributed. KKT-based global precision optimality uses the manuscript's concavity premise. Finite scans do not establish uniqueness of the persistence optimum outside the tested domain; the passive-limit check is finite-parameter convergence evidence. Linux CI is configured, but a local macOS run alone does not establish a successful GitHub Actions run.

Remote visibility, tag SHA and exact remote file checks are recorded separately after upload, so this source report does not claim an upload outcome before it occurs.
