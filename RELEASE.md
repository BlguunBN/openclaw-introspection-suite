# Release Instructions

Use this repo as the source of truth for the OpenClaw Introspection Suite.

## Before publishing

1. Verify the four skills still validate.
2. Confirm the trigger matrix still matches the current wording.
3. Review the suite index and workflow file for consistency.
4. Make sure the README stays short and does not duplicate the detailed docs.

## Packaging expectation

Each skill should remain a valid skill pack with:
- `SKILL.md`
- optional `references/`
- optional `examples/`

If you update a skill pack, validate it with the OpenClaw skill validator before shipping.

## Recommended publish checklist

- run validation on each skill
- update trigger matrix if wording changes
- update suite index if roles change
- update workflow if the sequence changes
- commit changes
- push to GitHub

## Keep the repo lean

Do not add extra docs unless they actually help someone publish or use the suite.
Avoid turning this into a general handbook.
