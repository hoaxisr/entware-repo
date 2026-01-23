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
opkg install awg-manager      # Web-интерфейс для AmneziaWG
opkg install sing-box-awg     # sing-box с поддержкой AmneziaWG
```

## Available Packages

| Package | Version | Description |
|---------|---------|-------------|
| **awg-manager** | 1.2.1 | AmneziaWG tunnel manager with web interface |
| **sing-box-awg** | 1.13.0-beta.7-awg2.0 | sing-box proxy platform with AmneziaWG 2.0 support |

## For Developers

To add a new package:
1. Build `.ipk` for target architecture
2. Place it in the corresponding folder (`mipsel-3.4-kn/` or `aarch64-3.10-kn/`)
3. Push to repository
4. GitHub Actions will automatically regenerate `Packages` index
