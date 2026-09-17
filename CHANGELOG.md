# Changelog

Release history for **DRR VIS** (`wts_bloc`), from the first public release onward.

- App Store: https://apps.apple.com/th/app/drr-vis/id6747107330
- Google Play: https://play.google.com/store/apps/details?id=th.go.drr.vis

Format based on [Keep a Changelog](https://keepachangelog.com/).

**Sources and caveats**
- Versions **1.0 – 1.4** predate this git repository (the first commit is 10 Oct 2025, and the current project code was imported on 25 Nov 2025), so those entries come from the App Store release notes only.
- From **1.5** onward, entries combine store release notes with the git history.
- Store version numbers and `pubspec.yaml` versions do not always line up — the `pubspec` version is noted per entry where it is known. Where a store release has no matching version bump in git, the mapping is inferred from commit dates and is marked as such.

---

## [1.6.2] — 11 Sep 2026 (Play) · 12 Sep 2026 (App Store)
`pubspec 1.6.2+25`

### Fixed
- Auto-fill of route name and location on the weigh station record screen — now uses `waysDetailRes.name` for the route name (previously `subdistrict`) and renders the location as "district, province"

### Changed
- Route selection screen wording — hid the "only routes with a submitted plan are shown" note and changed the empty state to "ไม่พบข้อมูลแผน" (No plan data found)

## [1.6.1] — 15 May 2026
No version bump in git; shipped from commit `d9bca719`.

### Changed
- Improved new-version notifications — set Upgrader's `durationUntilAlertAgain` to zero so the alert shows every time the Dashboard is opened

## [1.6.0] — 15 May 2026
`pubspec 1.6.0+23`

### Added
- `GetWayPlan` — filters the route list down to routes that already have an operation plan, with an explanatory notice on screen

## [1.5.6] — internal build (22 Apr 2026)
`pubspec 1.5.6+22` — no separate store release; shipped as part of 1.6.

### Security
- SSL certificate validation (pinning) for a specific host in the Dio client

## [1.5.5] — 2 Apr 2026
`pubspec 1.5.5+21`

### Added
- Automatic update notifications with a custom upgrade alert, so users are prompted to move to the latest version

### Changed
- Dependency updates

## [1.5.4] — 15 Jan 2026
`pubspec 1.5.4+20`

### Added
- Weight unit labels on input fields

### Changed
- Converted all weight units to kilograms and right-aligned the unit text

## [1.5.3] — 15 Jan 2026
`pubspec 1.5.3+19`

### Added
- Automatic token refresh every 20 minutes and on app resume (`AppLifecycleState.resumed`)
- `AuthHelper` for token expiry validation

### Changed
- Longer session duration and improved error handling
- Replaced contact details with the DRR hotline and phone number
- Removed redundant token checks from load-more and pull-to-refresh actions

### Fixed
- Force UI updates when the token expires

## [1.5.2] — 9 Jan 2026
`pubspec 1.5.2+17`

### Added
- Improved location handling with pull-to-refresh
- Automatic data refresh when switching between pages

### Fixed
- Double login issue resolved with `AuthInterceptor`
- Data now refreshes when switching to the arrest / weigh station tabs

## [1.5.1] — 9 Jan 2026
Mapping inferred — `pubspec` build 16 was never committed.

### Added
- PDF export, including sharing on iOS (permissions + share sheet support)

### Changed
- Further performance work and clearer error messages

## [1.5.0] — 6 Jan 2026
`pubspec 1.5.0+14` / `+15`. Carries the December 2025 performance and refactoring work, which was developed under `pubspec 1.4.0+1` but never shipped under that store version.

### Added
- PDF export with authentication
- Image compression before upload
- Location permission disclosure for Google Play policy compliance

### Changed
- Major performance work — ~62% faster app launch and ~38% less RAM usage, via lazy bloc initialization, theme caching, `IndexedStack` for bottom navigation, and batched Dashboard loading
- Race condition prevention in token refresh
- Numeric keypad for weight entry
- Updated iOS / macOS / Flutter dependencies and refreshed the Dashboard UI
- Refactored every BLoC (Arrest, Collaborative, Dashboard, Establish, Product, Login, Province, ProvinceMaster, Profile, VehicleCar, Ways, WeightCar, WeightUnit) to cut duplication and adopt `Equatable`

### Removed
- Dropped the Android background location permission in favor of a disclosure dialog

### Fixed
- State mutation bugs in MaterialsBloc, NewsBloc, WaysBloc, WeightUnitBloc and EstablishBloc
- Shaft weight validation and violation tracking
- 400 error when creating a weigh station record
- Duplicate snackbars and inconsistent error handling across screens

---

The entries below predate this repository; notes are taken from the App Store listing.

## [1.4] — 16 Dec 2025

### Changed
- Reworked the news detail page layout with a sticky header
- Reorganized attachment labeling

## [1.3] — 9 Aug 2025

### Fixed
- JSON parsing errors
- Numeric data handling

## [1.2.1] — 11 Jul 2025

### Changed
- Switched the map to the CartoDB Voyager style, with support for multiple tile servers

## [1.2] — 10 Jul 2025

### Added
- Data pagination
- Automatic status indicators

### Changed
- Improved screen responsiveness

## [1.1] — 5 Jul 2025

### Added
- Automatic GPS location detection with the current location shown on the map
- Location status management and validation

## [1.0] — 30 Jun 2025

- Initial release
