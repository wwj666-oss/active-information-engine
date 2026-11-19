# Active Information Engine — submission v1.0.0

Numerical code and data for *Optimal Net Work in an Active Information Engine with Costly Sensing*.

## DOI and citation

This submission version is archived in Zenodo: [10.5281/zenodo.24361271](https://doi.org/10.5281/zenodo.24361271).

Wan, W., Ren, H., Dong, A., & Fu, R. (2026). *Code and Data for Optimal Net Work in an Active Information Engine with Costly Sensing* (v1.0.0-submission) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.24361271

The deposited ZIP is identical to the verified submission archive below. The submission tag and archive are preserved unchanged. Earlier statements in the bundled validation documents about no Zenodo deposit describe the initial GitHub delivery stage before this DOI record was created.

## Reproduce

The complete structured source distribution is stored in [active-information-engine-v1.0.0-submission.zip](active-information-engine-v1.0.0-submission.zip). It contains 143 files: scientific source code, scripts, tests, full numerical data and precision schedules, PDF/SVG/PNG figures, pinned dependencies, manuscript identifiers and validation records. The archive delivery preserves the validated directory structure; it is not a binary program.

Download or clone this repository, verify the archive, and extract it:

```sh
shasum -a 256 -c ARCHIVE_SHA256SUMS
unzip active-information-engine-v1.0.0-submission.zip
cd active-information-engine
python scripts/verify_integrity.py
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python run_all.py --workers 4
```

On Windows, extract the ZIP normally and activate the environment with `.venv\Scripts\activate`. For all 5,121 main-figure grid cells, run `python run_all.py --full --workers 4` inside the extracted directory. To redraw the supplied full data, run `python scripts/plot_figures.py --mode full`.

## Validation

See [the acceptance report](VALIDATION_REPORT.md). Ten scientific tests and all eleven SM IX B–D comparisons passed in clean Python 3.11 environments. Both full figure grids were recomputed, and all seven full plotting CSVs match the input package numerically with maximum difference zero. All 5,121 saved precision schedules passed reevaluation. Packaging omissions, dependency security advisories and a CSV-audit gap were repaired; scientific core source files were preserved.

The intended version tag is `v1.0.0-submission`. The validated archive SHA-256 is:

```
daa95881a72a65baca90f892af39ceb23994ade1cd7f16bdb7b9898e8c621b7c
```

## Scope

This is a disclosed manuscript-based numerical reconstruction, not a claim to archive the original author code. The reference manuscript PDFs and historical drafts are excluded. Code, generated data and documentation are public at the user's instruction. The exact submission archive has subsequently been deposited manually in Zenodo; no automatic GitHub integration is enabled. No reuse license has been assigned; see [LICENSE](LICENSE).

The file layout and detailed methods are documented inside the archive. Runtime packages are pinned; platform-specific wheel hashes were verified for CPython 3.11 on macOS arm64. GitHub Actions checks the extracted bundle separately on Linux when available.
