# AGENTS.md

This repository is a static ESP Web Tools firmware flasher. Keep AI changes small, local, and aligned with the existing single-page structure. See [readme.md](readme.md) for the public project summary.

## What matters here

- The main app lives in [index.html](index.html); there is no package manager or build pipeline in the repo.
- Firmware selection is driven by [firmware/index.json](firmware/index.json); each entry should point to a manifest file that exists under `firmware/`.
- When adding a new firmware option, update both the manifest file and `firmware/index.json` so the dropdown stays in sync.
- Keep paths compatible with the current GitHub Pages-style deployment, including the `/BinaryBearx-esp-web-tool/` and root-path fallbacks already used for images and favicon links.
- Preserve the Web Serial availability check and the current ESP Web Tools / Improv Wi-Fi integration unless the user explicitly asks for a behavior change.

## Editing guidance

- Prefer direct edits to the existing HTML and JSON files rather than introducing new abstractions.
- Do not duplicate README content in this file; link to docs instead of re-embedding them.
- Keep manifest names user-facing and descriptive, since they populate the firmware dropdown directly.

## Verification

- Open [index.html](index.html) in Chrome or another Chromium-based browser and confirm the firmware list loads and the install button updates when a firmware is selected.
- If a change touches manifest data, confirm the referenced file exists under `firmware/` and the dropdown label still matches the intended firmware.