# Shizuku - ADB Bypass Fork

This is a modified fork of the official Shizuku application designed specifically for devices where the operating system forcibly disables wireless debugging, hides the ADB status, or restricts access to developer settings (e.g., restricted profiles or MDM locks).

## What does this fork do?
The official Shizuku app checks the system's `adbEnabled` global setting before allowing the service to start. If the system reports that ADB is disabled, the app blocks the "Start" and "Pair" buttons.

This fork bypasses that UI validation by forcing the internal `adbEnabled` variable to always return `1` (true). This allows you to initiate the pairing and connection process even if the OS attempts to mask the real ADB status.

No other changes have been made to the original codebase. The only modifications are located in:
* `manager/src/main/java/moe/shizuku/manager/utils/SettingsHelper.kt`
* `manager/src/main/java/moe/shizuku/manager/adb/AdbStarter.kt`
* `manager/src/main/java/moe/shizuku/manager/home/StartWirelessAdbViewHolder.kt`

## Download
You can download the compiled APK from the **Releases** section on the right side of this page.
