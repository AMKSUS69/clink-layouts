# Clink layouts

Community keyboard layouts for [Clink](https://github.com/anti-ltd/clink). Browse, download, and keep custom layouts updated from the app.

This repository is also the smallest working example of a layout repository. The two layouts in `Layouts/` are ordinary Clink layout files. When they change, GitHub Actions publishes them and a verified `manifest.json` release automatically.

## Add a layout

The easiest way is to make it in Clink first. Open **Customize → Layout**, make or edit a layout, then export it. Put the exported `.clinklayout` file in the `Layouts` folder and push it to `main`.

You do not need to calculate hashes, make a manifest, tag a release, or upload a file by hand. The workflow does all of that after every push.

If you are starting from scratch, copy either example file in `Layouts`, change its `name`, and arrange the letters in its three rows. Keep the file as valid JSON and give it a different filename. Import it into Clink to test it before pushing.

## What Clink verifies

Clink only downloads the `manifest.json` from this repository's GitHub release. Every layout file must be HTTPS, come from this exact repository release, be a `.clinklayout` file smaller than 500 KB, and match the SHA-256 hash and file size listed in the manifest. Clink then decodes it as a keyboard layout with strict size limits before it can be installed. Layout repositories contain data only: they cannot run code in Clink.

## Publishing your own repository

Fork this repository, keep the `Layouts/` folder and `.github/workflows/release.yml`, then add your layouts and push to `main`. In Clink, open **General → Repositories**, add the public GitHub repository URL, and choose what to download. Community repositories are never silently added or recommended by Clink: choosing one is always the user's decision.
