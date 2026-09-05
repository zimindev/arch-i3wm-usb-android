# **Install Android Tools & MTP Support on Arch Linux** 🐧📱

### **1. Update System** 🔄

First, update your system packages:

```bash
sudo pacman -Syu
```

### **2. Install Android Tools & MTP Support** 🛠️

Install the Android Platform Tools and MTP support:

```bash
sudo pacman -S android-tools gvfs-mtp
```

This installs:

* 🔧 **android-tools** — Provides `adb` and `fastboot` for working with Android devices.
* 📂 **gvfs-mtp** — Adds MTP support for accessing Android phone storage through Linux file managers.

### **3. Enable USB Debugging** 🔌

On your Android phone, enable:

**Settings → Developer options → USB debugging**

If **Developer options** are hidden:

**Settings → About phone → Build number**

Tap **Build number** several times until Developer options are enabled.

### **4. Connect Your Android Phone** 📱

Connect the phone to your computer using a USB cable.

Unlock the phone and select:

**File Transfer / Android Auto**

instead of:

**Charging only**

### **5. Check USB Detection** 🔍

Check whether Arch Linux detects the phone:

```bash
lsusb
```

Your Android device should appear in the list.

### **6. Check ADB Connection** 🔧

Run:

```bash
adb devices
```

A correctly connected device should appear as:

```text
List of devices attached
XXXXXXXX    device
```

If you see:

```text
XXXXXXXX    unauthorized
```

unlock your phone and accept the **Allow USB debugging** prompt.

### **7. Check MTP File Transfer** 📂

Open your file manager and look for your Android phone under **Devices** or **Other Locations**.

You should be able to access folders such as:

* 📷 **DCIM**
* 🖼️ **Pictures**
* 📥 **Download**
* 🎵 **Music**
* 🎬 **Videos**
* 📁 **Internal Storage**

### **8. Useful ADB Commands** ⚡

Check connected devices:

```bash
adb devices
```

Open an Android shell:

```bash
adb shell
```

Install an APK:

```bash
adb install app.apk
```

Copy a file from Android to Arch:

```bash
adb pull /sdcard/file.txt
```

Copy a file from Arch to Android:

```bash
adb push file.txt /sdcard/
```

### **9. Fastboot** 🚀

Check whether Fastboot is available:

```bash
fastboot --version
```

Fastboot is mainly used when the Android device is in **Bootloader/Fastboot mode**.

### **Done!** 🎉

Android Tools and MTP support are now installed on your Arch Linux system.

You can use:

* 🔧 **ADB** — Android debugging and device management
* 🚀 **Fastboot** — Bootloader and firmware operations
* 📂 **MTP** — File transfer between Android and Arch Linux
* 💻 **ADB Shell** — Command-line access to Android

---

## **Resources & Links** 🔗

* 📚 **Arch Linux Wiki:** https://wiki.archlinux.org/
* 🤖 **Android Developers — ADB:** https://developer.android.com/tools/adb
* 🛠️ **Android Developers — Fastboot:** https://developer.android.com/tools/releases/platform-tools
