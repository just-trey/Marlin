# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.9.3-N2-rc3] - 2021-03-21

### Added
- Enabled FAN_KICKSTART_TIME as some users reported fan not kicking on for slower speeds

### Changed

- Removed custom colors - no longer needed
- Updated HEATER_0_MAXTEMP from 270 to 275 per request
- Updated BED_MAXTEMP from 110 to 120 per request
- Updated DEFAULT_ZJERK from 0.4 to 0.3 to match other ender clones
- Updated Z_PROBE_FEEDRATE_SLOW from 300 to match Marlin defaults (it ends up being the same value)
- Updated Z_PROBE_OFFSET_RANGE_MAX from 60 to 65 per request
- Updated Z_PROBE_END_SCRIPT to add acceleration setting per user comment
- Updated HOMING_FEEDRATE_MM_M to match other ender clones
- Disabled define NO_WORKSPACE_OFFSETS since we don't need a leaner Marlin build and allows this feature (per request)
- Updated THERMAL_PROTECTION_BED_PERIOD from 40 to 20 to match other ender clones

### Fixed

- Found proper definition for LCD to allow for better screen contrast by disabling MKS_ROBIN_TFT35 and enabling TFT_GENERIC, and set its child values to fix screen color issues (Closes #13)
- Changed ADVANCED_PAUSE_RESUME_PRIME to 0 to prevent extra purge on filament change mid-print (M600).

## [2.0.9.3-N2-rc2] - 2021-01-16

### Added
- Keep Z Stepper active to prevent nozzle dropping
- Turn on fan animation (I know, just minor eye candy)
- Turn on Classic Jerk vs. using EJerk (recommended for use on cartesian printers)
- Enabled bed leveling to be probed twice for higher accuracy
- Make homing required after stepper motors are enabled (prevents inaccurate readings and moving axis points beyond limits)
- Changed logic for bed mesh to extrapolate calculations beyond bed probe grid.
- Center bed after probing (allows touch screen access after probing)

### Changed
- set `BAUDRATE` to `115200` due to some reliability issues reported by users 
- Set `ESTEPS` to 2S and 2D Elegoo defaults
- set extruder min temperature to `180` 

### Removed
- `POWER_LOSS_PIN` removed from custom section since power loss does not work

## [2.0.9.3-N2-rc1] - 2021-01-09

### Added

- Enabled G-code `M575`
- Added Elegoo Neptune 2D courtesy of [mlee12382](https://github.com/mlee12382)
- Set filament runout script to be able to identify the tool that failed (2D enhancement)
- Enabled fan kickstart
- Added UTF-8 Filename support
- Enabled `TOOLCHANGE_FILAMENT_SWAP` (2D enhancement)
- Enabled `AUTO_REPORT_POSITION`
- Enabled `HOST_ACTION_COMMANDS` for Remote printing and reporting back to the host (Octoprint)

### Changed

- Update and linked issue in `TESTING_STATUS.md` and fixed typo in `README.MD`
- Moved FAQ's to main `README.MD` and added how to find the board version
- Disabled TOUCH_IDLE_SLEEP due to the screen still reacting to touches when clicked to wake
- Simplified down to one config with multiple switches.
- Reduced probing margin
- Increased Probing Grid to 5x5
- Updated PLA preheat temp to 200
- Reduced hot end idle timeout to 5 minutes
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
