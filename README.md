<p align="center">
  <img src="https://raw.githubusercontent.com/anti-ltd/clink-language-packs/main/icon-1024.png" width="96" alt="Clink app icon">
</p>

<h1 align="center">Clink layouts</h1>

<p align="center">Open keyboard layouts for Clink.</p>

Clink ships familiar layouts in the app. This repository contains extra layouts that people can browse, download, and keep updated. Each layout is ordinary JSON data, not code, and remains available offline after download.

## Official Clink repositories

[Language packs](https://github.com/anti-ltd/clink-language-packs) · [Layouts](https://github.com/anti-ltd/clink-layouts) · [Profiles](https://github.com/anti-ltd/clink-profiles) · [Themes](https://github.com/anti-ltd/clink-themes) · [Panels](https://github.com/anti-ltd/clink-panels) · [Actions](https://github.com/anti-ltd/clink-actions) · [Fonts](https://github.com/anti-ltd/clink-fonts) · [Sounds](https://github.com/anti-ltd/clink-sounds)

## Included layouts

The official repository currently includes:

| Layout | What it is |
|---|---|
| Clink Flow | Clink's two-thumb optimized letter arrangement. |

Clink Flow lives in [`Layouts/`](Layouts). It is deliberately small and readable, so it is a good place to start when making your own.

## Make your first layout

You do not need to write JSON if you do not want to.

1. Open Clink and go to **Customize → Layout**.
2. Make a new layout or edit a copy of one you already use.
3. Export it from Clink. You will get a `.clinklayout` file.
4. Put the file in [`Layouts/`](Layouts).
5. Give the file a clear name, such as `my-community-layout.clinklayout`.
6. Run the repository validation tools if they are present.
7. Push your changes to `main`. GitHub Actions publishes the layouts and manifest to the `latest` release.

If you would rather start with a file, copy `Layouts/clink-flow.clinklayout`, rename it, change the visible `name`, and edit the letters in its three `rows`. Import the file into Clink to test it before publishing.

```json
{
  "id": "custom-my-layout",
  "name": "My layout",
  "rows": [
    ["q", "w", "e", "r", "t", "y", "u", "i", "o", "p"],
    ["a", "s", "d", "f", "g", "h", "j", "k", "l"],
    ["z", "x", "c", "v", "b", "n", "m"]
  ]
}
```

Keep the `id` starting with `custom-`, give every layout a different file name, and use valid JSON. That is all a basic layout needs.

## Add your repository to Clink

After GitHub publishes the first release, open **General → Repositories** in Clink and add your repository, for example:

```text
your-name/my-clink-layouts
```

Then open **Customize → Layout → Layout packs**. Your repository's layouts appear in a separate repository source. Download one to add it to **Yours**. Later releases update that installed layout rather than creating duplicates.

## Make a layout with an AI agent

[`PROMPT.md`](PROMPT.md) is a ready-to-use brief for an AI coding agent. Fork the repository, open the fork in your agent, and say:

```text
Read PROMPT.md and create a [describe the language, arrangement, or ergonomic goal] layout.
```

The prompt directs the agent to the real layout schema and asks it to preserve your intended key order. Review the rows and import the file into Clink before publishing.

## What Clink verifies

Clink accepts only public HTTPS GitHub release manifests. Every layout must come from that repository's release, be a `.clinklayout` file smaller than 500 KB, and match the SHA-256 hash and byte count in the manifest.

Clink downloads each file into a temporary directory, verifies it, checks that it is a safe keyboard layout, and only then makes it available. A layout repository contains data only and cannot run code in Clink.

Adding a repository is a trust decision. Only add repositories whose release contents you trust.

## Publishing is automatic

Keep `Layouts/`, `tools/`, and `.github/workflows/` in your fork. Add or update a layout and push to `main`. GitHub Actions builds the manifest and refreshes the `latest` release.
