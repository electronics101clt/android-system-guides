# UJC201 Device Profile - Complete Analysis

## Device Identity

### Core Specifications
- **Model**: UJC201_64
- **Chipset**: MediaTek AC8257 (AC8257V/WAB)
- **Architecture**: ARM64-v8a (AArch64, Cortex-A53 quad-core)
- **CPU**: ARM Cortex-A53 (0xd03) rev 4
- **Cores**: 4
- **RAM**: 4 GB
- **Storage**: 64 GB eMMC
- **Android Version**: 9 (API 28) - *masquerading as Android 12 in UI*
- **Display**: 1280×720, 160 dpi

### Build Information
- **Firmware**: `UJC201-V1.0.66R3-231020_0857`
- **Build Date**: **Friday, October 20, 2023 at 08:57:49 CST**
- **Build Timestamp (UTC)**: 1697763469
- **Build Type**: `userdebug` with `test-keys`
- **Security Patch**: 2021-10-05
- **Manufacturer**: alps (generic MediaTek)
- **Board**: ac8257_demo
- **SELinux**: Permissive
- **Debuggable**: Yes (`ro.debuggable=1`)

### Device Serial Numbers
- **ADB Serial**: O7VODQ9HR48LDE89
- **Boot Serial**: O7VODQ9HR48LDE89

## Age & Timeline Analysis

### Flash Date / Birth Date
- **ROM Built**: October 20, 2023 08:57 CST
- **First Boot** (persistent_properties): October 19, 2023 20:58
- **User Data Initialized**: October 19, 2023 20:58

### Device Age (as of October 5, 2026)
- **~3 years old** since manufacture
- Firmware has NOT been reflashed since factory (original Oct 2023 build)

### Last Activity
- **Most Recent Access**: August 26, 2026 20:45
- **Timezone**: America/New_York (US Eastern)
- **Last Boot Reason**: reboot,userrequested

## Where This Was Purchased

### Purchase Source Analysis
Based on model number `UJC201_64` and build characteristics:

**Most Likely**: Generic Chinese Android head unit from:
- **eBay** (most common)
- **AliExpress**
- **Amazon** (various Chinese sellers)
- Generic car stereo importers

### Search Terms That Would Find This Unit
1. `AC8257 android car radio 4GB 64GB`
2. `AC8257 1280x720 android car stereo 4+64`
3. `MTK AC8257 double din android`
4. `UJC201` (exact but rare in listings)

### Identifying Characteristics for Matching
- AC8257 chipset (NOT AC8227L - that's different/older)
- 4GB RAM / 64GB storage
- 1280×720 resolution
- Build number: `UJC201-V1.0.66R3-*`
- Test-keys build (developer-friendly)

### Brand/Seller Markings
- **No specific branded apps found** (no custom OEM launcher)
- Sold under **many different brand stickers**:
  - "UIS"
  - "Junsun"
  - "Seicane"
  - Generic "Android Car Stereo"
  - Various eBay seller brands

**The chipset and build number are the true identity** - the external branding/logo is meaningless.

## Architecture Details

### CPU Architecture
```
Processor: AArch64 Processor rev 4 (aarch64)
CPU implementer: 0x41 (ARM Limited)
CPU architecture: 8 (ARMv8)
CPU variant: 0x0
CPU part: 0xd03 (Cortex-A53)
CPU revision: 4
```

### Supported ABIs
- **Primary**: arm64-v8a (64-bit)
- **Secondary**: armeabi-v7a, armeabi (32-bit compat)

### Features
- fp (floating point)
- asimd (Advanced SIMD / NEON)
- evtstrm (event stream)
- aes (AES encryption)
- pmull (polynomial multiply)
- sha1 (SHA-1 hashing)
- sha2 (SHA-2 hashing)
- crc32 (CRC32 checksum)

## System Characteristics

### Developer-Friendly Features
✅ **Root over ADB** (`adb root` works)
✅ **Test-keys build** (can sign apps with platform keys)
✅ **SELinux Permissive** (no policy blocking)
✅ **Remountable /system** (can modify system partition)
✅ **USB debugging always available**
✅ **ADB over WiFi** (unit's own hotspot)

### Factory Configuration
- **Platform Key**: Public AOSP test keys
- **Signature**: Can sign apps with matching platform.x509.pem/pk8
- **System Apps**: Can install to /vendor/app or /system/priv-app
- **UID 1000**: Apps can run as system UID with proper signature

## Current System Apps (UID 1000)

Apps running with system privileges on this device:
```
com.jancar.monster
com.jancar.audiosettings
com.autochips.quickbootmanager
com.jancar.hd2cam
com.mediatek.simprocessor
com.mediatek.location.lppe.main
com.jancar.steeringwheelkeys
```

All located in `/vendor/app/` or `/vendor/priv-app/`

## Partition Layout

### Modern (Android 9+) Structure
```
/vendor/app/         - Vendor apps (read-only)
/vendor/priv-app/    - Privileged vendor apps (system UID capable)
/data/               - User data (read-write)
```

### Storage Status
- Battery level: 0% (car stereo - powered by vehicle)
- No actual battery (AC powered unit)

## Network Configuration
- **WiFi Hotspot**: Available (for ADB over WiFi)
- **USB**: ADB enabled over USB
- **Bluetooth**: Available (MediaTek stack)

## Branding & Jancar Apps

The device runs **Jancar** framework apps:
- System UI modifications
- Audio settings integration
- Camera handling (4-camera support)
- Steering wheel key mapping
- Canbus integration

**Jancar** = Common Chinese car stereo firmware framework (not a specific brand)

## Why This Unit Is Valuable

1. **Open by default** - no security bypass needed
2. **Platform-signed apps** - can install privileged apps
3. **System UID access** - full hardware control
4. **Modifiable system** - can replace any component
5. **ADB root** - complete development access
6. **Still available** - can buy identical units on eBay/AliExpress

## Verification Commands

```bash
# Identity check
adb shell getprop ro.product.model          # UJC201_64
adb shell getprop ro.build.display.id       # UJC201-V1.0.66R3-231020_0857
adb shell getprop ro.hardware               # ac8257

# Developer-friendly verification
adb shell getprop ro.build.tags             # test-keys ✓
adb shell getprop ro.debuggable             # 1 ✓
adb shell getenforce                        # Permissive ✓

# Architecture
adb shell getprop ro.product.cpu.abi        # arm64-v8a

# Build date
adb shell getprop ro.build.date             # Fri Oct 20 08:57:49 CST 2023

# Root check
adb root && adb shell id                    # uid=0(root) ✓
```

## Summary

**What it is**: Generic Chinese AC8257 Android car head unit
**When made**: October 20, 2023 (firmware build date)
**When first used**: October 19-20, 2023 (initial boot)
**Age**: ~3 years old (as of Oct 2026)
**Where bought**: Likely eBay/AliExpress (generic import)
**True identity**: UJC201_64, AC8257, 4GB/64GB, test-keys build
**Key value**: Open platform for development, system-level app installation

---

## Date Analyzed
October 5, 2026

## Device Connection
Currently connected via ADB (O7VODQ9HR48LDE89)

## Brand Discovery & Purchase Information

### IMPORTANT: ZScreen Branding
This device has **ZScreen** branding installed via custom launcher (`com.zscreen.metro`).

**ZScreen is NOT a manufacturer** - it's a local Charlotte, NC car audio installation service:
- Website: https://zscreen.net/
- Service: Mobile automotive technician for car audio installation
- They install Android head units and customize them with their branded launcher

### This Means:
**The device was likely purchased from ZScreen Electronics in Charlotte, NC**, who:
1. Sourced a generic UJC201/AC8257 unit
2. Installed their custom "MetroStart" launcher
3. Provided it as part of their installation service

### Finding Identical Units Online

Since this is a generic Chinese unit with ZScreen branding added locally, search for:

#### Brand Names These Are Sold Under:
- **Podofo** (very common on Amazon)
- **AWESAFE**
- **Hikity**  
- **CUSP**
- **Haudio**
- **Seicane**
- **Driauto**
- **Unbranded/Generic** (most common on eBay)

#### Best Search Terms:
```
"10.1 inch universal android car stereo 4GB 64GB"
"double din android head unit 4+64"
"universal android car radio 1280x720"
"android 9 universal car stereo 4GB"
```

#### What NOT to Search:
- ❌ "ZScreen car stereo" (won't find anything - it's a local installer)
- ❌ "AC8257" (rarely marketed by chipset name)
- ❌ "UJC201" (internal model, not advertised)

#### Where to Buy:
- **Amazon**: Search "Podofo 10.1 android car stereo"
- **eBay**: Search "universal double din android 4GB 64GB"
- **AliExpress**: Search "universal android head unit 4+64"

### Warning:
Most units you find will have **release-keys** firmware and will NOT be as open/moddable as this test-keys build. Always verify before purchase if you need root/system access.

---

**Updated**: October 5, 2026
