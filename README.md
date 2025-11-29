# RDAP CLI

A fast, modern command-line tool for querying RDAP (Registration Data Access Protocol) servers. Built for developers, sysadmins, and security researchers.

## Features

- 🌐 **Domain Queries** - Retrieve registration information including nameservers, status, and registrar details
- 📡 **IP Lookups** - Query IP address allocation from regional internet registries
- 🔢 **ASN Information** - Look up Autonomous System Number registration and routing info
- 🚀 **Auto-Discovery** - Automatically discovers appropriate RDAP servers using bootstrap

## Installation

RDAP CLI is distributed as self-contained executables with no runtime dependencies. Download the latest release for your platform:

### Windows

1. Download `rdap-win-x64.zip` from the [latest release](https://github.com/xg5-simon/reconcti-tools/releases/latest)
2. Extract and install:
   ```powershell
   Expand-Archive rdap-win-x64.zip -DestinationPath C:\Tools\rdap
   $env:Path += ";C:\Tools\rdap"
   ```
3. Verify installation:
   ```powershell
   rdap --version
   ```

### Linux

1. Download `rdap-linux-x64.tar.gz` from the [latest release](https://github.com/xg5-simon/reconcti-tools/releases/latest)
2. Extract and install:
   ```bash
   sudo tar -xzf rdap-linux-x64.tar.gz -C /usr/local/bin/
   sudo chmod +x /usr/local/bin/rdap
   ```
3. Verify installation:
   ```bash
   rdap --version
   ```

### macOS

1. Download `rdap-osx-x64.tar.gz` (Intel) or `rdap-osx-arm64.tar.gz` (Apple Silicon) from the [latest release](https://github.com/xg5-simon/reconcti-tools/releases/latest)
2. Extract and install:
   ```bash
   sudo tar -xzf rdap-osx-*.tar.gz -C /usr/local/bin/
   sudo chmod +x /usr/local/bin/rdap
   sudo xattr -d com.apple.quarantine /usr/local/bin/rdap
   ```
3. Verify installation:
   ```bash
   rdap --version
   ```

> **Note:** All binaries are self-contained with Native AOT compilation. No .NET runtime installation needed.

## Quick Start

### Domain Lookup

Query domain registration information:

```bash
rdap domain example.com
```

Returns information including:
- Domain status and registration dates
- Nameserver configuration
- Registrar details
- DNSSEC status

### IP Address Lookup

Query IP address allocation:

```bash
rdap ip 8.8.8.8
```

Returns information including:
- IP range and CIDR notation
- Network name and type
- Organization details
- Geographic location

### ASN Lookup

Query Autonomous System Number information:

```bash
rdap asn 15169
```

Returns information including:
- AS name and description
- Registration details
- Organization information

## Advanced Usage

### JSON Output

Get raw JSON output for scripting:

```bash
rdap domain example.com --json
```

### Custom Server

Query a specific RDAP server directly:

```bash
rdap domain example.com --server https://rdap.verisign.com/com/v1/
```

### Verbose Output

Enable detailed logging:

```bash
rdap domain example.com --verbose
```

## Documentation

For full documentation, visit: https://xg5-simon.github.io/reconcti-tools/

## License

This work is licensed under a [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](http://creativecommons.org/licenses/by-nc-nd/4.0/).

You are free to:
- **Share** — copy and redistribute the material in any medium or format

Under the following terms:
- **Attribution** — You must give appropriate credit
- **NonCommercial** — You may not use the material for commercial purposes
- **NoDerivatives** — If you remix, transform, or build upon the material, you may not distribute the modified material

See [LICENSE.md](LICENSE.md) for full details.
