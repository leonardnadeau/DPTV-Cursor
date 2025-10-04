---
---


[![Latest Release](https://img.shields.io/github/v/release/Crealivity/DPTV-Cursor?style=for-the-badge)](https://github.com/Crealivity/DPTV-Cursor/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Crealivity/DPTV-Cursor/latest/total?style=for-the-badge)](https://github.com/Crealivity/DPTV-Cursor/releases/latest)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black)](https://www.buymeacoffee.com/Crealivity)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-FF5E5B?style=for-the-badge&logo=kofi&logoColor=white)](https://ko-fi.com/Crealivity)

---

<p align="center">
  <img src="https://github.com/Crealivity/DPTV-Cursor/blob/main/meta/DPTV-Cursor_BANNER.png" alt="DPTV Cursor - A mouse cursor for dumbphones and TVs" width="100%"/>
</p>

---

⚠️ **WARNING FOR TV USERS:**  
Before setting anything up, follow the [Installation instructions](#installation) carefully.
If you enable the accessibility service without first granting overlay permissions, your TV remote may stop responding and you could temporarily soft-brick navigation.  
It’s recoverable (via USB mouse or ADB), but avoid the hassle, follow the setup steps in the installation section.

---

### INTRODUCTION

DPTV Cursor is a small utility that gives Android TVs and flip phones a real, usable mouse cursor, no touchscreen required.  
It’s meant for devices where navigation is limited to a D-pad or remote and some apps simply can’t be used properly without touch input.

Whether you want to scroll through a web page, tap small buttons, or access areas a D-pad can’t reach, DPTV Cursor makes it possible.  
The cursor appears as a floating overlay that you move with your remote or keypad, letting you click, long press, and scroll inside almost any app.

It works great for controlling apps that don’t support remote navigation, or for bringing old flip phones and TV boxes back to life.  
You don’t need to pair a mouse, connect your phone, or use any external hardware, everything runs directly on the device.

👉 **Download the latest stable release here:** **[Releases ›](https://github.com/Crealivity/DPTV-Cursor/releases/latest)**

---

### HOW TO USE

Once installed and properly set up, DPTV Cursor runs as a background accessibility service.
You’ll see a small on-screen pointer that can be moved using your remote or keypad.

- Use the D-pad or navigation keys to move the cursor around the screen
- Press the OK / Center button to click
- Hold the OK button for a long press (useful for drag or context menus)
- The color buttons or function keys (red, green, yellow, blue) can be used to perform swipe gestures:
- Red / Green → scroll up / down- Yellow / Blue → scroll left / right
- The shortcut key toggles mouse visibility on or off
- The shortcut key (default: mute button) switches between cursor, scroll, and D-pad modes.
- You can customize this shortcut inside the app’s settings
- In scroll mode, the D-pad works as smooth page scrolling
- In cursor mode, you get full pointer control, just like a real mouse
- The cursor will auto-hide after a short idle period and reappear when you press a navigation key

#### SETTINGS
You can adjust all the behavior in the Settings screen:


| Section | Options |
| - | - |
| Appearance | • Cursor size (small → large)<br>• Cursor style (choose from preset icons)<br>• Edit or replace custom cursor image |
| Movement | • Pointer speed (slow → fast)<br>• Scroll speed (slow → fast)<br>• Disable scroll inertia or acceleration (useful on small |
| Behaviour | • Keep cursor inside screen edges<br>• Hide cursor on home screens or launchers<br>• Auto-hide after 1 minute of inactivity<br>• Disable toasts or pop-up tips |
| Shortcut | • Disable shortcut key (for full-size remotes)<br>• Set short-press or long-press behavior<br>• Enter custom key code manually<br>• Detect and assign any remote key automatically |

#### OLDER ANDROID VERSIONS (4.4 – 6.x)

DPTV Cursor still runs on older Android builds, but due to system restrictions, functionality is limited:
- The cursor can only interact with native (non-web) apps
- It won’t click or scroll inside webviews, browsers, or hybrid apps
- Some gestures and overlays may behave inconsistently
- Scroll speed cannot be changed

From Android 7 and newer, everything works as intended, full motion, clicks, long-presses, and scrolling are supported across almost all apps.

---

### INSTALLATION

#### ANDROID PHONES

There’s a single APK for all devices. If your phone exposes Accessibility settings, do this:

1. Install the APK from the [Releases](https://github.com/Crealivity/DPTV-Cursor/releases/latest) page.
2. Open system settings → Special app access → Display over other apps → allow DPTV Cursor.
3. Now go to Settings → Accessibility → DPTV Cursor → enable the *Mouse toggle service*.

If your device **hides** Accessibility (common on ultra-minimal flip phones), enable it with ADB:

```
adb -d shell appops set io.github.crealivity.dptvcursor SYSTEM_ALERT_WINDOW allow
adb -d shell settings put secure accessibility_enabled 1
adb -d shell settings put secure enabled_accessibility_services io.github.crealivity.dptvcursor/io.github.crealivity.dptvcursor.services.MouseEventService
adb -d shell am startservice io.github.crealivity.dptvcursor/io.github.crealivity.dptvcursor.services.MouseEventService
```

Once done, the cursor should respond as soon as you use the D-pad/keys.


#### ANDROID TV'S

1. Download the latest release APK from the [Releases](https://github.com/Crealivity/DPTV-Cursor/releases/latest) page.
2. Side-load the APK on your TV using a USB drive, ADB, or any app installer.
3. After installation, don’t enable the accessibility service yet.
4. First, open your TV’s system settings → Special App Permissions → Display over other apps → and allow DPTV Cursor.
5. Once overlay permission is granted, go to Accessibility settings and enable the *Mouse toggle service*.

That’s it. You’ll now be able to toggle and use the cursor with your remote.
If you skip the overlay permission step and enable the service first, you might lock your remote controls until you plug in a physical mouse or use ADB, so follow the order carefully.

#### RECOVERY (IF YOU SOFT-BRICK THE TV)

If you enabled the service before overlay permission and inputs seem “stuck”:

1. Plug in a USB/Bluetooth mouse (and keyboard if needed).
2. Go to Settings → Accessibility → disable DPTV Cursor.
3. Go to Special app access → Display over other apps → allow DPTV Cursor.
4. Re-enable the accessibility service.

---

### CONTRIBUTING & REPORTING BUGS

DPTV Cursor is an open and community-driven project, but not a commercial one.
It’s developed and maintained in personal free time, it has no sponsors, no ads, no tracking, and no profit model.

If you’d like to contribute, there are several ways to help:

* **Code contributions:** improvements, fixes, or new ideas are always welcome. Just fork the repo, open a pull request, and give it a short description.
* **Bug reports:** if something doesn’t work, please check you’re on the latest release first, then open an issue with as much detail as possible (device model, Android version, steps to reproduce).
* **Testing:** different Android versions and TV firmwares behave differently, real-world feedback helps a lot.
* **Support the project:** if you find the app useful and want to help keep it alive, consider donating through [Ko-fi](https://ko-fi.com/Crealivity) or [Buy Me a Coffee](https://www.buymeacoffee.com/Crealivity). Every bit helps me dedicate more time to fixes, updates, and personal support.

---

### CREDITS

This project is based on the original **[MATVT (Mouse for Android TV Toggle)](https://github.com/virresh/matvt)** by [@virresh](https://github.com/virresh).
Their open work laid the foundation that made DPTV Cursor possible.

Special thanks to the MATVT community and contributors for their earlier work on accessibility-based mouse control for Android TVs, this project is meant to extend and adapt this idea to older and modern devices.

---

### LICENSE

This project is licensed under the **[PolyForm Noncommercial License 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0/)**.

You are free to **use, modify, and share** the code for **non-commercial purposes only**.
Commercial redistribution, sale, or use in monetized apps is **not permitted**.

If you’d like to discuss other forms of usage or collaboration, please open an issue or contact me directly through the repository.

---
---
