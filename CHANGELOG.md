# Changelog

All notable changes to ZAPPing will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.2] - 2025-09-01

### Fixed
- Updated help documentation to include all current features
- Added dynamic column resizing so all columns are displayed

## [1.0.1] - 2025-08-30

### Added
- DMG installer for easier distribution and installation
- Signed by Apple
- Automatic column width optimization based on content
- Double-click column dividers to auto-resize to optimal width
- IP version filtering (All/IPv4/IPv6)
- Status filtering (All/Success/Failed)
- Remove failed hosts button with deletion progress window
- Context menu with copy options (Cell Contents, IP Addresses, Selected Rows)
- Edit menu additions (Copy Cell Contents, Copy Selected IP Addresses)
- DNS resolution progress window with cancellation support
- Shutdown progress window for clean app termination
- Status bar with aggregate statistics (Overall/IPv4/IPv6 RTT)
- Performance warnings for large host lists (>1,000) and high ping rates (>100/sec)

### Changed
- First public release on GitHub
- Switched to in-process pinging with thread pools (replaced subprocess architecture)
- Default ping interval is 30 seconds
- Packaged as DMG instead of standalone app file

### Fixed
- Installation and code signing issues from v1.0.0
- Memory management and socket cleanup
- Performance with large host lists

## [1.0.0] - 2025-08-29

### Added
- Initial release of ZAPPing
- Multi-host ping monitoring with real-time updates
- Support for IPv4, IPv6, and hostnames
- CIDR subnet notation with automatic expansion (capped at 65,536 hosts)
- Real-time statistics display with round-trip time measurements
- CSV export functionality for data analysis
- Copy table data as TSV for spreadsheet compatibility
- Settings window for host configuration
- Configurable ping interval
- Multiple independent monitoring windows
- No root privileges required

### Notes
- Internal release (not distributed publicly)

[1.0.2]: https://github.com/adpgu/ZAPPing/releases/tag/v1.0.2
[1.0.1]: https://github.com/adpgu/ZAPPing/releases/tag/v1.0.1
