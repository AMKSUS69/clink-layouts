<p align="center">
  <img src="icon-1024.png" width="96" alt="Clink app icon">
</p>

<h1 align="center">Clink Layouts</h1>

<p align="center">Open keyboard layouts for Clink.</p>

Clink ships familiar layouts in the app. This repository is where people can browse, download, and keep extra layouts updated. Each layout is ordinary JSON data, not code, and stays available offline after it has been downloaded.

## Included layouts

| Layout | What it is |
|---|---|
| Community Dvorak | A Dvorak letter arrangement, ready to download and edit. |
| Community Colemak | A Colemak letter arrangement, ready to download and edit. |

The examples live in [`Layouts/`](Layouts). They are deliberately small and readable, so they are a good place to start when making your own.

## Make your first layout

You do not need to write JSON if you do not want to.

1. Open Clink and go to **Customize → Layout**.
2. Make a new layout or edit a copy of one you already use.
3. Export it from Clink. You will get a file ending in `.clinklayout`.
4. Put that file inside this repository's `Layouts` folder.
5. Give the file a clear name, for example `my-community-layout.clinklayout`.
6. Push your changes to `main`.

GitHub Actions does the boring release work: it reads each layout, makes `manifest.json`, calculates every file's SHA-256 hash and size, and creates the public release that Clink downloads.

If you would rather start with a file, copy either example in `Layouts`, rename it, change the visible `name`, then change the letters in its three `rows`. Import the file into Clink to test it before you publish it.

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

After the first GitHub Action finishes, open **General → Repositories** in Clink and add your repository URL, for example:

```text
https://github.com/your-name/my-clink-layouts
```

Then open **Customize → Layout → Layout packs**. Your repository's layouts appear in the **Community** section, separate from Clink's own layouts. Download one to add it to **Yours**; later releases update that same installed layout rather than filling the list with duplicates.

## What Clink verifies

Clink only accepts a public HTTPS GitHub release manifest. Every layout must come from that same repository's release, be a `.clinklayout` file smaller than 500 KB, and match the SHA-256 hash and byte count listed in the manifest.

Clink downloads into a temporary folder, verifies the file, checks that it is a safe keyboard layout, and only then makes it available. A layout repository contains data only: it cannot run code in Clink. Adding a community repository is still a trust decision, so only add repositories run by people or communities you trust.

## Publish your own repository

Fork this repository and keep `Layouts/` plus `.github/workflows/release.yml`. Add layouts, push to `main`, and GitHub publishes them automatically. You do not need to create tags, hashes, manifests, or releases by hand.
