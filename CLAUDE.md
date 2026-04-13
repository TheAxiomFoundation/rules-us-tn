# rac-us-tn

Tennessee benefit-program source and encodings live here.

## Scope

- Tennessee-administered overlays, manuals, and guidance
- federal program cores remain in `rac-us`
- keep Tennessee source slices in this repo even when the underlying program is federal

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
- Do not leave promoted corpus files as `status: stub`.
- Do not hand-edit promoted policy outputs; improve the automatic system and rerun.
