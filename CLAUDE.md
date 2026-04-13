# rac-us-tn

Tennessee benefit-program source and encodings live here.

## Scope

- Tennessee-administered overlays, manuals, and guidance
- federal program cores remain in `rac-us`
- keep Tennessee source slices in this repo even when the underlying program is federal
- Tennessee SNAP state-option and self-employment-treatment slices belong here

## Layout

```text
rac-us-tn/
├── sources/
│   └── slices/        # exact Tennessee source excerpts
└── scripts/
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

- Repo boundaries follow jurisdictions, not program labels.
- Tennessee SNAP overlays belong here, not in `rac-us`.
- Preserve exact source slices under `sources/slices/`.
- For delegated state-set parameters, add a `*.meta.yaml` sidecar next to the
  source slice with `relation: sets` pointing at the canonical upstream CFR or
  USC slot.
- Do not leave promoted corpus files as `status: stub`.
- Do not hand-edit promoted policy outputs; improve the automatic system and rerun.
