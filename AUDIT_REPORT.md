# Repository Audit Report

_Date:_ 2026-04-08

## Scope
This audit reviewed **all tracked files** in the repository:

- `README.md`
- `requirements.txt`
- `notebooks/DDM.ipynb`
- `notebooks/PV_Coupon_Calculator.ipynb`
- `notebooks/PV_FV_Calculator.ipynb`
- `notebooks/portfolio_returns_engine_MVP.ipynb`

## Plan
1. Inventory repository files and notebook metadata.
2. Review each file for correctness, completeness, and dependency coverage.
3. Identify gaps that block reproducible local execution.
4. Apply targeted fixes to documentation and dependency declarations.
5. Run a validation check to confirm notebooks parse successfully and dependencies align.

## Findings

### 1) `README.md`
- Project overview was clear but missing reproducible setup steps and notebook-specific guidance.
- No dependency installation instructions were included.

### 2) `requirements.txt`
- Existing dependency list omitted packages used in notebooks:
  - `matplotlib` (used in `portfolio_returns_engine_MVP.ipynb`)
  - `yfinance` (used in `DDM.ipynb`)
  - `jupyter` (required for local notebook execution)

### 3) Notebooks
- All notebooks are structurally valid and parseable as notebook JSON.
- Several notebooks rely on interactive `input()` prompts by design.
- `portfolio_returns_engine_MVP.ipynb` includes inline tests/assertions and plotting logic.
- DDM notebook depends on live market data (`yfinance`) and therefore requires network access for full runtime behavior.

## Execution Completed

### Changes made
- Expanded `README.md` with explicit setup and usage instructions.
- Updated `requirements.txt` to include missing runtime dependencies used by notebooks.

### Validation steps run
- Confirmed repository file inventory with `rg --files`.
- Parsed notebook metadata and code-cell inventory with a Python audit command.

## Residual Risks / Notes
- Notebook outputs are retained in repository and may become stale over time.
- Interactive prompt-based notebooks are less suitable for CI automation without refactoring to function-based APIs.
