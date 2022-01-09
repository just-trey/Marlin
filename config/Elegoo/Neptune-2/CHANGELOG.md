# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [2.0.9.3-N2-rc1] - 2021-01-09

### Added

- Enabled G-code `M575`
- Added Elegoo Neptune 2D courtesy of [mlee12382](https://github.com/mlee12382)
- Set filament runout script to be able to identify the tool that failed (2D ehnancement)
- Enabled fan kickstart
- Added UTF-8 Filename support
- Enabled `TOOLCHANGE_FILAMENT_SWAP` (2D ehnancement)
- Enabled `AUTO_REPORT_POSITION`
- Enabled `HOST_ACTION_COMMANDS` for Remote printing and reporting back to the host (Octoprint)

### Changed

- Update and linked issue in `TESTING_STATUS.md` and fixed typo in `README.MD`
- Moved FAQ's to main `README.MD` and added how to find the board version
- Disabled TOUCH_IDLE_SLEEP due to screen still reacting to touches when clicked to wake
- Simplified down to one config with multiple switches.
- Reduced probing margin
- Increased Probing Grid to 5x5
- Updated PLA preheat temp to 200
- Reduced hot end idle timeout to 5 minuates
- 
### Fixed

- User unable to Home printer of boot (AKA Red Screen Issue)

## [2.0.9.3-N2-beta1] - 2021-01-02

### Added
- This changelog
- Enabled `SD_CHECK_AND_RETRY`
- Enabled `ADAPTIVE_STEP_SMOOTHING`
- Enabled `STATUS_MESSAGE_SCROLLING`
- Enabled `LONG_FILENAME_HOST_SUPPORT`
- Enabled `SCROLL_LONG_FILENAMES`
- Enabled `TOUCH_IDLE_SLEEP`after 2 minutes- from [@P4ND4-1100010](https://github.com/P4ND4-1100010)

### Changed
- Updated [README.md](README.md)
- Updated BLTOUCH auto level to a 5x5 grid
- Updated `Z_MAX_POS` from `260` to `250`
- Renamed TESTING_STATUS.MD to TESTING_STATUS.md

### Fixed
- Found a reliable way around the `Homing Failed` configuration issue on install. I still think it's an odd fix but thank you [@P4ND4-1100010](https://github.com/P4ND4-1100010)!

## [Marlin-2.0.9.3-elegoo] - 2021-01-01

### Added
- Implemntaiton of COLOR-UI instan of LVGL
- Custom Theme for COLOR-UI
- Enabled [S-Curve Acceleration](https://github.com/synthetos/TinyG/wiki/Jerk-Controlled-Motion-Explained)
- Enabled Adaptive Step Smoothing
- Enabled ARC Support Enabled
- Enabled **M600** Change filament at layer.

**BLTouch COnfigurations**
- Enabled Z Level Offset Wizard
- Enabled **Live Z** Support
- Enabled Bed tramming wizard option (I mean, you still need to level every once and a while)

Unreleased: https://github.com/just-trey/Marlin/compare/2.0.9.3-N2-rc1...elegoo-neptune-2

2.0.9.3-N2-$1-RC1: https://github.com/just-trey/Marlin/compare/Marlin-2.0.9.3-elegoo...2.0.9.3-N2-rc1

2.0.9.3-N2-$1-beta1: https://github.com/just-trey/Marlin/compare/Marlin-2.0.9.3-elegoo...2.0.9.3-N2-beta1

Marlin-2.0.9.3-elegoo: https://github.com/just-trey/Marlin/releases/tag/Marlin-2.0.9.3-elegoo
