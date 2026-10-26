# Universal Patcher

A static browser app for applying available executable patch sets locally, without uploading files to a server.

Live demo: https://dev.th3.ovh/universal-patcher-web/

## How it works

- Open the page in a modern browser.
- Choose an executable (`.exe`) file.
- The app automatically selects a patch set when the executable filename exactly matches a key in the `Patches` object (case-insensitive).
- If there is no filename match, choose a patch set from the selector.
- Apply the patch and download the resulting executable.

## Features

- Local in-browser patching; files stay on your device.
- Patch-set selector populated directly from the keys in `Patches`.
- Automatic patch-set selection by executable filename, with manual selection as a fallback.
- Wildcard byte-pattern matching.
- Dry-run preview of patch matches.
- Optional output filename and filename-preservation setting.
- No server backend or external dependencies.

## Usage

1. Select an executable file. A matching patch set is selected automatically when available.
2. If the filename does not match a patch-set key, select the patch set you want to use.
3. Optionally enter an output filename. By default, the original filename is used with an `.exe` extension.
4. Enable `Dry run` to preview patch counts without changing the file.
5. Enable `Keep original filename` to use the entered output filename exactly as entered.
6. Select `Apply patch` and download the patched executable.

## Notes

- Add or update patch sets in the `Patches` object in `app.js`; the selector is generated from its keys.
- This project is designed as a static GitHub Pages / browser-hosted app.
- All patching is performed locally in the browser.
