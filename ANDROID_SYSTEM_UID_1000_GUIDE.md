# Android System UID 1000 Guide

## Overview
This guide explains how to create Android apps that run with system privileges (UID 1000), giving them full system-level access and permissions.

## What is UID 1000?
- **UID 1000** = `android.uid.system`
- System-level privileges
- Access to protected system APIs
- Can modify system settings
- Can access all device resources

## Real-World Examples from Device
Apps currently running as UID 1000 on AC8227L head unit:
```
com.jancar.monster           - System app
com.jancar.audiosettings     - Audio settings
com.autochips.quickbootmanager - Boot manager
com.jancar.hd2cam            - Camera app
com.mediatek.simprocessor    - SIM processor
com.mediatek.location.lppe.main - Location services
com.jancar.steeringwheelkeys - Steering wheel controls
```

## Method 1: Using sharedUserId (Primary Method)

### Step 1: Modify AndroidManifest.xml
Add `android:sharedUserId="android.uid.system"` to the manifest tag:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    android:sharedUserId="android.uid.system"
    package="com.yourcompany.yourapp"
    android:versionCode="1"
    android:versionName="1.0">

    <!-- Your app content -->

</manifest>
```

### Step 2: Sign with Platform Certificate
**CRITICAL:** Apps with `sharedUserId` MUST be signed with the platform/system certificate.

```bash
# Using signapk.jar
java -jar signapk.jar platform.x509.pem platform.pk8 app-unsigned.apk app-signed.apk

# Or using apksigner (newer method)
apksigner sign --key platform.pk8 --cert platform.x509.pem app-unsigned.apk
```

**Where to get platform keys:**
- Extract from device `/system/build/security/` or `/vendor/build/security/`
- From device manufacturer
- From custom ROM source code
- For testing: Use AOSP test keys (NOT for production!)

### Step 3: Install to System Partition

```bash
# Enable root
adb root

# Remount system as read-write
adb remount
# Or manually:
adb shell mount -o rw,remount /vendor
adb shell mount -o rw,remount /system

# Create app directory
adb shell mkdir -p /vendor/app/YourAppName

# Push APK
adb push app-signed.apk /vendor/app/YourAppName/YourAppName.apk

# Set correct permissions
adb shell chmod 644 /vendor/app/YourAppName/YourAppName.apk
adb shell chown root:root /vendor/app/YourAppName/YourAppName.apk

# Reboot to apply
adb reboot
```

## Method 2: Install as Privileged App

### Install to priv-app Directory
Apps in `/system/priv-app/` or `/vendor/priv-app/` get additional privileges:

```bash
adb root
adb remount
adb push app-signed.apk /vendor/priv-app/YourApp/YourApp.apk
adb shell chmod 644 /vendor/priv-app/YourApp/YourApp.apk
adb reboot
```

## Verification Methods

### Check if App is Running as System
```bash
# Method 1: Check running processes
adb shell "ps -A | grep your.package.name"
# Look for UID 1000 or "system" in the output

# Method 2: Dumpsys package info
adb shell "dumpsys package your.package.name | grep userId"
# Should show: userId=1000

# Method 3: Check app info
adb shell "pm dump your.package.name | grep -E '(userId|sharedUserId)'"
```

### Verify Installation Location
```bash
# Check where app is installed
adb shell "pm path your.package.name"
# Should show /system/ or /vendor/ path

# List system apps with UID 1000
adb shell "dumpsys package | grep -B 2 'userId=1000'"
```

## Permissions Granted to System UID

Apps running as UID 1000 automatically get:
- Access to protected broadcasts
- System-level file access
- Hardware control (GPIO, I2C, SPI, etc.)
- Audio routing control
- Display management
- Network configuration
- Bluetooth stack access
- All signature-level permissions

## Example: Analyzed System App

Pulled from device: `com.jancar.audiosettings`
```
Location: /vendor/app/ivi-audio-settings/ivi-audio-settings.apk
UID: 1000
Manifest: android:sharedUserId="android.uid.system"
Signature: Signed with platform certificate
```

Manifest structure:
```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    android:sharedUserId="android.uid.system"
    android:versionCode="126"
    android:versionName="1.2.6.ac8257.fe9aa6c.20231012"
    package="com.jancar.audiosettings">
```

## Important Notes and Warnings

### Security Implications
- System apps have unrestricted access to device
- Can brick device if misconfigured
- Can access all user data
- Can modify critical system settings

### Development Considerations
1. **Cannot change sharedUserId after first install**
   - Must uninstall completely to change
   - Changing sharedUserId requires different signature

2. **Platform signature is device-specific**
   - Different manufacturers use different keys
   - App signed for one device won't work on another

3. **Play Store restrictions**
   - Cannot upload apps with sharedUserId to Play Store
   - Only for system/vendor pre-installed apps

4. **Debugging**
   - Can still debug via ADB
   - May need root for some operations
   - Use `adb shell run-as` won't work (system apps don't need it)

## Modern Alternatives (Android 10+)

For newer Android versions, consider:
- **Signature permissions**: Define your own signature-level permissions
- **System API access**: Use `@SystemApi` annotations
- **Privileged permissions**: Use privileged permission whitelist
- **SELinux policies**: Custom security policies

## Partition Locations by Android Version

### Android 7-9 (Older)
```
/system/app/         - Regular system apps
/system/priv-app/    - Privileged system apps
```

### Android 10+ (Modern)
```
/vendor/app/         - Vendor apps (recommended)
/vendor/priv-app/    - Privileged vendor apps
/system/app/         - AOSP system apps
/system/priv-app/    - Privileged AOSP apps
/product/app/        - Product-specific apps
```

## Quick Reference Commands

```bash
# Check device connectivity
adb devices

# Enable root
adb root

# Pull existing system app for analysis
adb shell pm path com.android.settings
adb pull /system/priv-app/Settings/Settings.apk

# Check app signature
apksigner verify -v app.apk

# View manifest
aapt dump xmltree app.apk AndroidManifest.xml | grep sharedUserId

# Install system app
adb remount
adb push app.apk /vendor/app/AppName/app.apk
adb reboot

# Verify running UID
adb shell "ps -A | grep package.name"
adb shell "dumpsys package package.name | grep userId"
```

## Troubleshooting

### App Won't Install
- Check signature matches platform keys
- Verify sharedUserId is exactly: `android.uid.system`
- Ensure proper file permissions (644)

### App Crashes on Launch
- Check SELinux policies: `adb shell getenforce`
- Review logcat: `adb logcat | grep your.package`
- Verify all required libraries are present

### Wrong UID Assigned
- App not signed with platform keys
- Not installed to system partition
- Conflicting existing installation (uninstall first)

## Testing Without Platform Keys

For development/testing only:
```bash
# Install as regular app first
adb install app.apk

# Check what UID it gets (will NOT be 1000)
adb shell "ps -A | grep your.package"

# Note: App won't have system privileges without proper signature
```

## Date Created
2026-10-05

## Device Tested
- **Device**: AC8227L Android Head Unit
- **Android Version**: 8.1
- **Build**: Autochips AC8257
- **ADB ID**: O7VODQ9HR48LDE89

---

## Additional Resources
- [Android Platform Security](https://source.android.com/security/overview/app-security)
- [Package Manager Permissions](https://developer.android.com/guide/topics/permissions/overview)
- [System App Development](https://source.android.com/devices/tech/config)
