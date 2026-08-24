# Verify this Clink layouts repository

Read `README.md`, `PROMPT.md`, `Layouts/clink-flow.clinklayout`, and `.github/workflows/release.yml`. Audit only; do not edit, publish, or generate release artifacts.

For every `Layouts/*.clinklayout`, parse the JSON and check the schema against the included example. Confirm a unique stable `custom-`-prefixed id, a non-empty visible name, and exactly three rows of lowercase key labels. Check for accidental duplicated or missing keys, allowing only deviations that are explicit and intentional for that layout. Ensure filenames are clear kebab-case names and that files contain data only—no manifest assets, code, or unrelated settings.

Confirm `manifest.json` is not manually maintained (the release workflow generates it) and that no release-workflow changes weaken publishing or validation. Report each layout checked, its exact three-row arrangement, checks performed, and precise paths for failures or ambiguities. Recommend import testing in Clink, but do not present it as having happened unless it was actually performed.
