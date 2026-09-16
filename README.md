# Scan to PDF

A standalone, single-page tool: take or pick photos on your phone, reorder/rotate them, and save a single PDF — entirely in the browser, no app install and no server round-trip.

Built for FinParse staff who need to get scanned documents onto a computer without depending on the same Wi-Fi network as that computer (phone-to-PC LAN links can be blocked by firewalls, client isolation on managed/campus networks, or plain unreachability).

Live at: https://lerlau.github.io/finparse-scan-tool/

## How it works

- `index.html` is a fully self-contained page (styles and script inline, icons as embedded data URIs) except for two Google Fonts and the [jsPDF](https://github.com/parallax/jsPDF) library, loaded from cdnjs.
- Photo capture uses plain `<input type="file" capture="environment">` (camera) and `<input type="file" multiple>` (library) — no `getUserMedia`, so it works over plain HTTP too, unlike a live camera preview.
- Saving offers the built PDF via the Web Share API (`navigator.share({ files })`) where supported — the native "Save to Files / AirDrop / Mail" sheet on iOS — falling back to a plain browser download elsewhere.
- Deployed to GitHub Pages automatically on every push to `main` via `.github/workflows/pages.yml`.

## Add to iPhone home screen

Open the live link in Safari → Share → Add to Home Screen. It installs with its own icon and opens full-screen, no browser chrome.
