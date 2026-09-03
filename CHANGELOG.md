# Changelog

A plain-language history of every AmpKeeper firmware release, written for the people who
own one. The format follows [Keep a Changelog](https://keepachangelog.com/), and versions
follow [semantic versioning](https://semver.org/).

Signed firmware images are attached to each version's entry on the
[Releases](https://github.com/ampkeeper/ampkeeper-releases/releases) page.

A version marked `-beta.N` is a pre-release. Only devices opted into the beta channel are
offered one; a device on the normal stable channel skips them and waits for the next
stable version.

## [0.13.0-beta.1] - 2026-09-03

The first public beta of AmpKeeper.

### Added

- **Solar-following charge control.** AmpKeeper watches what your solar is exporting and
  sets your car's charging current to match, so the car charges on sunshine rather than
  the grid. Five modes: *Solar only*, *Solar + grid* (holds a minimum current from the
  grid and lets solar push it higher), *Grid top-up*, *Manual*, and *Off*.
- **Schedules.** Set windows across the week, each with its own mode and current limit,
  for time-of-use tariffs or a guaranteed overnight top-up. A window's current can track
  your configured maximum or be pinned to a fixed value.
- **Tesla support over Bluetooth.** Pair AmpKeeper directly to a Tesla and it controls
  charging on the car itself — no wallbox required, and no Tesla API subscription.
- **Wallbox and inverter support.** Sigenergy meters and batteries, and Fronius inverters
  over SunSpec.
- **History.** Five-minute and daily records kept on the device, with charts for energy
  flow and charging, and CSV export. Thirteen months of five-minute detail and twenty
  years of daily totals.
- **A local web app.** Everything runs on the device over your own network, including the
  built-in Help, which works with no internet connection at all.
- **Settings backup and restore**, so a replacement device can be brought up as the old
  one was.
- **Signed over-the-air updates.** AmpKeeper checks for new firmware, tells you what has
  changed, and installs it when you ask. Every image is signed, and the device verifies
  that signature against a key built into its own firmware before writing anything.
- **A recovery system** alongside the main firmware, so a device can be brought back
  without opening it up or connecting a cable.
- **AmpKeeper Connect (optional).** Link the device to an account for access away from
  home and longer cloud history. AmpKeeper works fully without it.

[0.13.0-beta.1]: https://github.com/ampkeeper/ampkeeper-releases/releases/tag/v0.13.0-beta.1
