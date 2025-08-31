# ZAP Ping

A native macOS network utility for monitoring multiple hosts with real-time ICMP ping statistics.

![macOS](https://img.shields.io/badge/macOS-14.0%2B-blue)
![Version](https://img.shields.io/github/v/release/adpgu/ZAPPing)
![License](https://img.shields.io/badge/license-Proprietary-orange)
![Freeware](https://img.shields.io/badge/price-FREE-brightgreen)

## Features

- **Batch Ping Operations** - Monitor hundreds of hosts simultaneously
- **Real-time Statistics** - Live RTT measurements, packet loss, and success rates
- **IPv4 & IPv6 Support** - Full dual-stack capability with scope ID support
- **CIDR Subnet Expansion** - Input entire subnets (e.g., 10.0.0.0/24)
- **DNS Resolution** - Automatically resolves hostnames to both A and AAAA records
- **Smart Filtering** - Filter by IP version (IPv4/IPv6) or status (Success/Failed)
- **Export Capabilities** - Export results to CSV or copy as TSV for spreadsheets
- **Visual Status Indicators** - Color-coded status for quick issue identification
- **Concurrent Processing** - Optimized threading for high-performance monitoring

## System Requirements

- macOS 14.0 (Sonoma) or later
- Apple Silicon or Intel processor
- 50MB free disk space

## Installation

1. Download the latest DMG from the [Releases]([https://github.com/yourusername/zap-ping/releases) page
2. Open the downloaded DMG file
3. Drag ZAP Ping to your Applications folder
4. Launch from Applications or Spotlight

**First Launch:** macOS may show a security warning. Right-click the app and select "Open" to bypass Gatekeeper.

## Usage

1. Click **Settings** to configure hosts
2. Enter hosts (one per line):
   - IPv4 addresses: `8.8.8.8`
   - IPv6 addresses: `2001:4860:4860::8888`
   - Hostnames: `google.com`
   - CIDR subnets: `192.168.1.0/24`
3. Set ping interval (default: 30 seconds)
4. Click **Apply** to save configuration
5. Click **Start** to begin monitoring

### Keyboard Shortcuts

- `⌘N` - New Window
- `⌘C` - Copy selected rows
- `⌘E` - Export to CSV
- `⌘A` - Select all rows
- `⌘⇧A` - Copy all rows

### Filtering Options

- **IP Version Filter**: Show All, IPv4 only, or IPv6 only
- **Status Filter**: Show All, Success only, or Failed only
- **Remove Failed**: Clean up hosts that have never responded

## Technical Details

ZAP Ping uses low-level ICMP sockets for accurate ping measurements without requiring root privileges. Hosts are processed in parallel groups for optimal performance while respecting system resource limits.

NOTE: When a lot of sockets are opened (pinging many hosts), it can take the app quite some time to completely close. If you try to force quit, it might throw a beachball because the MacOS cleans up the sockets. Give it some time and the beachball will go away once the OS finishes closing the ping sockets. 

## Privacy & Network Access

This application:
- Only makes outbound ICMP echo requests to configured hosts
- Does not collect or transmit any user data
- Does not communicate with any external services
- Stores configuration locally in application preferences while running
- Saves nothing to local disc unless using export to csv option, when app closes all collected ping stats are gone

## Troubleshooting

**"Application cannot be opened" error**
- Right-click the app and select "Open" instead of double-clicking

**No ping responses**
- Verify the target host allows ICMP
- Check your network firewall settings
- Some hosts block ping requests by policy

**High CPU usage with many hosts**
- Increase the ping interval
- Reduce the number of monitored hosts
- Close unused monitoring windows

## Known Limitations

- Maximum recommended hosts: 500 per window
- CIDR expansion limited to 65,536 addresses (a /16 most likely wont work unless you really space out the ping interval)
- Some IPv6 link-local addresses may require manual scope ID entry

## License & Disclaimer

Copyright © 2025. All rights reserved.

This software is provided **"AS IS"**, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.

**USE AT YOUR OWN RISK.** This software performs network operations that may be restricted or monitored in certain environments. Users are responsible for ensuring compliance with all applicable laws, regulations, and network policies. The developer assumes no liability for any misuse, damage to systems, network policy violations, or any other consequences resulting from the use of this software.

## Distribution

This is proprietary software distributed as freeware. The source code is not publicly available. Redistribution of the binary is permitted only in unmodified form with all original files intact. Please include this readme and a link to this repo if distributing. 

## Support

This software is provided without formal support. Issues may be reported via GitHub Issues but responses are not guaranteed.

## Feature Requests

If there is something you would like this app to do, please request via github. 

## Credits

Developed with native macOS technologies including AppKit and Swift.

---

*Not affiliated with or endorsed by Apple Inc.* Ping utility for MacOS. Simple. Freeware. No Ads. Provided as-is, which some say is pretty good. Developed by a network engineer for network engineers.
