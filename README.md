# Entware Repository for Keenetic

Custom Entware package repository for Keenetic routers.

## Supported Architectures

| Architecture | Devices |
|--------------|---------|
| `mipsel-3.4-kn` | Keenetic with MIPS (MT7621, etc.) |
| `aarch64-3.10-kn` | Keenetic with ARM64 (KN-1811, etc.) |

## Installation

### 1. Determine your architecture

```bash
uname -m
# mipsel -> use mipsel-3.4-kn
# aarch64 -> use aarch64-3.10-kn
```

### 2. Add repository

Create file `/opt/etc/opkg/custom.conf`:

```bash
# For mipsel:
echo "src/gz keenetic_custom https://hoaxisr.github.io/entware-repo/mipsel-3.4-kn" > /opt/etc/opkg/custom.conf

# For aarch64:
echo "src/gz keenetic_custom https://hoaxisr.github.io/entware-repo/aarch64-3.10-kn" > /opt/etc/opkg/custom.conf
```

### 3. Update and install

```bash
opkg update
opkg install awg-manager          # Web-интерфейс для AmneziaWG
opkg install sing-box-awg         # sing-box stable
opkg install sing-box-awg-beta    # sing-box beta
opkg install smtp-tunnel-client   # SOCKS5 proxy через SMTP
```

## Available Packages

| Package | Version | Description |
|---------|---------|-------------|
| **awg-manager** | 1.3.7 | AmneziaWG tunnel manager with web interface |
| **sing-box-awg** | 1.12.18-awg2.0 | sing-box proxy platform with AmneziaWG 2.0 support (stable) |
| **sing-box-awg-beta** | 1.13.0-beta.8-awg2.0 | sing-box proxy platform with AmneziaWG 2.0 support (beta) |
| **smtp-tunnel-client** | 1.0.0 | SOCKS5 proxy over SMTP protocol for DPI bypass |

## Use only if understand what are you doing
