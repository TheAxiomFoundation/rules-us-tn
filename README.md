# rac-us-tn

Tennessee jurisdiction-specific RAC source and encoding corpus.

This repo is for Tennessee-administered policy layers. Federal program cores stay
in `rac-us`; Tennessee overlays, manuals, guidance, and state-specific encodings
live here.

## Current scope

- TennCare ABD Manual source slices for Tennessee SNAP utility allowances
- Tennessee SNAP Policy Manual source slices for delegated SNAP state options
- Tennessee SNAP Income Policy source slices for self-employment expense treatment
- jurisdiction-local source corpus for Tennessee SNAP overlays

## Layout

```text
rac-us-tn/
├── sources/
│   └── slices/
│       ├── tdhs/
│       │   └── snap/
│       │       └── current-effective/
│       └── tenncare/
│           └── post-eligibility/
│               └── current-effective/
├── scripts/
│   ├── check_no_promoted_stubs.py
│   └── validate_repo.py
└── CLAUDE.md
```

## Local commands

```bash
cd /Users/maxghenis/TheAxiomFoundation/rac
uv run python -m rac.validate all /Users/maxghenis/TheAxiomFoundation/rac-us-tn
uv run python -m rac.test_runner /Users/maxghenis/TheAxiomFoundation/rac-us-tn -v

cd /Users/maxghenis/TheAxiomFoundation/rac-us-tn
python3 scripts/validate_repo.py
```

## Encoding policy

- Repo boundaries follow jurisdictions.
- Keep Tennessee-administered overlays in `rac-us-tn`, even when they sit on top of
  a federal program like SNAP.
- Keep exact local excerpts in `sources/slices/`.
- When a Tennessee source sets a value inside a federally delegated slot, add a
  `*.meta.yaml` sidecar next to the source slice with `relation: sets` pointing
  to the canonical upstream CFR or USC target.
- Do not hand-edit promoted policy outputs; use AutoRAC plus benchmarked repair
  loops.
