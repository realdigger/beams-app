# Changelog

All notable changes to BEAMS App are documented in this file.

[Русская версия](CHANGELOG.md)

## 1.8.0 (build 116)

- Expanded the diagnostic report to better investigate PPFD and DLI
  discrepancies.
- Refined PPFD and DLI calculations for the confirmed `BEAMS F 4 v2.0`.

## 1.7.0 (build 115)

- The diagnostic report now saves the light's built-in web interface HTML and
  JavaScript. PPFD@25 and DLI values shown by the web interface can also be
  added manually.
## 1.6.0 (build 114)

- Improved light connections and history: a summary API response listing daily
  cycles no longer interrupts loading, and custom names are saved by the
  controller model and ID.
- Backup restore was significantly expanded: it supports long cycles, checks
  the source, contents, model, and channel count before restoring, preserves
  controller system cycles, and saves the current data to a safety backup.
- Added a full Spectra section with favourites, protected deletion, file and
  QR-code export, file and QR-code import, and a 5-second preview before
  import. Fixed spectrum graphs in saved-spectrum cards.
- Bottom navigation was refreshed with compact icons for Light, Cycles,
  Spectra, and More.
- Saved-spectrum cards are more compact: tapping a graph applies its spectrum
  after confirmation, while export actions are available from the card menu.
## 1.4.4 (build 96)

- Corrected PPFD and channel-contribution calculations using aquarium
  dimensions and light configuration from the controller questionnaire.
- Added a current-spectrum graph based on LED data and backups for spectra,
  daily cycles, and long cycles.
- Added aquarium setup details and improved diagnostic tools.

## 1.3.2 (build 90)

- The Aquarium section now shows only actually selected lights.

## 1.3.1 (build 89)

- Added an Aquarium section to the Device tab with the setup parameters that
  affect light calculations.
- Moved Application information, update checks, and diagnostic-report creation
  to Settings.

## 1.3.0 (build 88)

- Split the Device tab into “Device and diagnostics” and “Application” blocks;
  added the controller ID and reduced spacing for a more compact layout.
- Added JSON diagnostic-report creation with app readings, brief technical
  information, and responses from known light APIs. The report does not include
  the IP address or host name.

## 1.2.0 (build 86)

- A detected update is saved and remains visible in Settings until the app is
  updated or a successful check finds no newer version.

## 1.1.0 (build 85)

- Added manual and once-per-24-hours automatic update checks through GitHub
  Releases with a link to the release page.

## 1.0.0 (build 84)

- First stable Android release for local control of BEAMS aquarium lights.
- Added Russian and English localization, automatic system-language selection,
  and a persistent manual language choice.
- Added discovery through mDNS, local IPv4 scanning with progress feedback, and
  discovery of BEAMS light access points for direct connection.
- Added manual connection by IP address, host name, or URL; connection history;
  and automatic reconnection through a saved host name with IPv4 fallback.
- Added local-only operation, background polling control while the app or Wi-Fi
  is unavailable, and a full refresh after returning to the app or network.
- Added automatic, manual, and service modes; responsive batched channel
  updates; total-brightness control; and protection against stale controller
  responses during mode and channel changes, including intermediate states
  while switching to service mode.
- Added controller-aware power limiting for manual channel changes, total
  brightness, and spectra, matching the native interface's power constraints.
- Added adaptive controls for 6 to 14 channels, controller-reported channel
  colors and wavelengths, and channel detail cards with precise manual editing
  and PPFD contributions at 25, 35, and 45 cm.
- Added DLI, PPFD, power, controller information, diagnostics, controller time,
  uptime, and copying of technical information for support requests.
- Added a read-only daily-cycle graph with its PPFD scale and current-time
  marker.
- Added spectrum selection, application, saving, overwrite confirmation, and
  protected deletion.
- Added a marine visual design, consistent dialogs, lists, notifications, a
  connection illustration, and a matching Android app icon.
- Added a link to the controller web interface and external links to the
  project, developer, and license.
