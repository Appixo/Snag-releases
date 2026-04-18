# Snag releases

This repo hosts signed installer binaries and the `latest.json` updater manifest for **Snag**.

The source code lives in a private sibling repo — this one exists so the Tauri auto-updater (running in installed clients) can fetch release metadata without a GitHub account.

## Downloads

Go to [Releases](https://github.com/Appixo/Snag-releases/releases) and grab the latest `snap_*_x64_en-US.msi` (or `snap_*_x64-setup.exe`).

Installed v0.1.3+ builds auto-update from here on launch.
