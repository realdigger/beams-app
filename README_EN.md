# BEAMS App

[![Version](https://img.shields.io/github/v/release/realdigger/beams-app?display_name=tag&label=version)](https://github.com/realdigger/beams-app/releases/latest)
[![APK downloads](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Frealdigger%2Fbeams-app%2Fmain%2Fdownloads.json)](https://github.com/realdigger/beams-app/releases)
![Android](https://img.shields.io/badge/Android-5.0%2B-brightgreen?logo=android)
![Status](https://img.shields.io/badge/status-testing-orange)
![Languages](https://img.shields.io/badge/languages-RU%20%7C%20EN-4fc3f7)

BEAMS App is an Android application for local control of BEAMS aquarium
lights.

> This is an independent, unofficial project. It is not affiliated with
> the manufacturer of BEAMS lights. BEAMS and related names may be
> trademarks of their respective owners.

[Русская версия](README.md)

[Changelog](CHANGELOG_EN.md)

## Testing status and liability

The application is currently in testing. Its operation has been confirmed with
the **BEAMS 2 PRO R-8**, **BEAMS 2 MAX R-10**, **BEAMS 2 PRO F-6**, and
**BEAMS 2 MAX F-8** and **BEAMS MAX F-8** light models.

Before testing, it is strongly recommended to save all stored spectra and
cycles from the light locally to avoid their possible loss.

The author accepts no responsibility for possible loss of saved settings,
spectra, or cycles, or for possible damage to light hardware. You use the
application at your own risk.

## Diagnostic report

The diagnostic report is the primary way to send the developer information
about a light problem. To create it:

1. Connect the app to the light.
2. Open Settings using the gear icon at the top of the screen.
3. At the bottom of the Application section, tap Create diagnostic report.
4. When needed, enter the PPFD@25 and DLI values shown in the light's built-in
   web interface. These fields are optional: leave them empty if the readings
   are not shown or were not recorded.
5. Tap Create report, then use the Android system sheet to save or send the
   JSON file together with a problem description and the Android device model.
6. Preferably send two reports with different channel levels—for example, one
   in automatic mode and one in manual mode.

The report does not contain the light's IP address or host name. It includes
diagnostic data, technical information, and built-in web-interface data needed
to investigate a problem.

If the app cannot connect to the light and create a report, copy its technical
information from the light's built-in web interface by tapping TrueSpectrum at
the bottom of the page, then attach it to the problem description.

## Screenshots

<p align="center">
  <img src="docs/screenshots/connection.jpg" alt="Connection screen" width="220">
  <img src="docs/screenshots/access-point-discovery.jpg" alt="Access-point discovery" width="220">
  <img src="docs/screenshots/control-auto.jpg" alt="Automatic mode controls" width="220">
</p>

<p align="center">
  <img src="docs/screenshots/control-service.jpg" alt="Service mode" width="220">
  <img src="docs/screenshots/control-manual.jpg" alt="Manual mode" width="220">
  <img src="docs/screenshots/spectrum-selection.jpg" alt="Spectrum selection" width="220">
</p>

<p align="center">
  <img src="docs/screenshots/spectrum-overwrite-confirmation.jpg" alt="Spectrum overwrite confirmation" width="220">
  <img src="docs/screenshots/spectrum-applied.jpg" alt="Applied spectrum" width="220">
  <img src="docs/screenshots/spectrum-delete-confirmation.jpg" alt="Spectrum deletion confirmation" width="220">
</p>

<p align="center">
  <img src="docs/screenshots/daily-cycle.jpg" alt="Daily-cycle graph" width="220">
  <img src="docs/screenshots/device-information.jpg" alt="Device information" width="220">
  <img src="docs/screenshots/channel-details.jpg" alt="Channel detail card" width="220">
</p>

<p align="center">
  <img src="docs/screenshots/current-spectrum.jpg" alt="Current-spectrum graph" width="220">
  <img src="docs/screenshots/aquarium-details.jpg" alt="Aquarium setup details" width="220">
  <img src="docs/screenshots/settings.jpg" alt="App settings" width="220">
</p>

<p align="center">
  <img src="docs/screenshots/spectra-library.jpg" alt="Saved spectra" width="220">
  <img src="docs/screenshots/manual-control-10-channels.jpg" alt="Ten-channel manual control" width="220">
</p>

<p align="center">
  <img src="docs/screenshots/backup.jpg" alt="Backup" width="220">
  <img src="docs/screenshots/spectrum-import-preview.jpg" alt="Spectrum import and preview" width="220">
  <img src="docs/screenshots/spectrum-qr-share.jpg" alt="Spectrum QR code" width="220">
</p>

## Features

- Discovers compatible controllers through mDNS and, when necessary, by
  scanning the local Wi-Fi IPv4 range with visible scan progress.
- Can also find and directly connect to BEAMS light access points. This is an
  alternative connection method when the light is not on the main local network.
  Android requires location permission to search for access points.
- Connects directly by IP address, host name, or full controller URL and
  remembers up to ten recent successful connections. A light can be assigned a
  custom name bound to its model and controller ID, so it remains available
  after an IP-address change.
- Restores the most recent connection at launch.
- Pauses automatic polling when the app is inactive or Wi-Fi is unavailable,
  then fully refreshes controller data after the app or Wi-Fi returns.
- Opens the controller's native web interface from the dedicated link icon.
- Supports Russian and English, using the system language by default. A manual
  language selection is available in the app and is remembered.
- Checks for a new version manually and automatically no more than once every
  24 hours through GitHub Releases, and opens the release page. A detected
  update remains visible in Settings until the app is updated or a successful
  check finds no newer version.
- Shows light model, controller role, hardware and software information,
  diagnostics, controller time and uptime, and a copyable technical-information
  bundle for manufacturer support requests.
- Shows aquarium setup parameters from the controller questionnaire: completion,
  dimensions, type, light count, and placement density.
- Creates a JSON diagnostic report containing app readings, brief technical
  information, responses from known light APIs, and the light's built-in web
  interface HTML and JavaScript. When needed, the PPFD@25 and DLI values shown
  by the web interface can be entered manually into the report. The report does
  not include the IP address or host name.
- Creates a portable backup of all light spectra, daily cycles, and long
  cycles except built-in protected cycles. Before restoring, the app shows the
  archive source, date, contents, and channel count; it identifies a backup
  from the same light and blocks restore when the channel counts differ. A
  safety copy of the current settings is created in `Downloads/BEAMS App`
  before data is deleted. All three object types are restored. The archive
  manifest contains the controller model and ID, channel configuration, and
  technical specification. Separate descriptions below the save and restore
  buttons explain each action.
- Shows the current daily-cycle graph, DLI, PPFD at 25, 35, and 45 cm, and
  power consumption. PPFD and channel-contribution calculations account for
  aquarium dimensions and light configuration from the controller questionnaire.
- Shows a current-spectrum graph calculated from LED spectral data, LED counts
  in channels, and current channel levels.
- Switches between automatic, manual, and service modes, keeping the selected
  mode visible while the controller applies its intermediate state changes. In
  service mode, all channels are set to 20%.
- Controls individual LED channels and total brightness in manual mode. As in
  the controller's web interface, total brightness equals the highest current
  channel level and changes scale all channels proportionally.
- Applies the controller's power limit to manual channel changes, total
  brightness, and spectra, so the application does not send an over-limit
  channel set.
- Adapts the channel-slider layout for controllers with 6 to 14 channels while
  keeping all channels visible in no more than two rows.
- Displays channel wavelengths and controller-reported colors. A channel card
  provides its full name, wavelength, level, and PPFD contribution at all three
  displayed heights; the level can be edited to hundredths of a percent in
  manual mode.
- Lists saved spectra in a compact grid with graphs. Tapping a graph asks for
  confirmation before applying its spectrum; favourite and delete actions are
  on the card, while file and QR export are in its menu. Current manual channel
  levels can also be saved as a new spectrum or an overwrite of the selected
  one.

## Requirements

- Android 5.0 (API 21) or later.

## Local operation

The application communicates directly with the light controller through its
REST API on the local network. No cloud account or external service is
required for operation. The controller's built-in web interface opens
in the device browser when requested. Only update checks contact GitHub
Releases.

## License

This project is licensed under the
[PolyForm Perimeter License 1.0.1](LICENSE).
