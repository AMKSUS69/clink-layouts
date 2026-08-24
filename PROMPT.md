# Create a Clink layout

You are contributing one keyboard layout to this repository. Read `README.md`, `Layouts/clink-flow.clinklayout`, and `.github/workflows/release.yml` before editing. Create or update exactly one `.clinklayout` file in `Layouts/`.

If the requested arrangement is not specific enough, ask which language, typing style, or ergonomic goal it serves. Otherwise preserve the requested order precisely. A layout is JSON data with a unique `id`, visible `name`, and three `rows` of lowercase key labels. Use a stable `custom-`-prefixed id and a clear kebab-case filename. Keep the layout deliberately readable; do not add code, manifest assets, or unrelated settings.

Use the included layout as the schema source of truth. Validate that the file is valid JSON, the rows are arrays, and no key is accidentally duplicated or omitted unless the requested layout intentionally requires it. Do not manually create `manifest.json`: the GitHub workflow builds it from `Layouts/*.clinklayout` on release.

Finish with the file created or changed, the exact key arrangement, and the checks performed. If practical, recommend importing the file into Clink for ergonomic testing before publishing.
