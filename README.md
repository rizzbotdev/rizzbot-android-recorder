# RizzBot Recorder

A Windows app that mirrors your Android phone on the PC over USB, records a profile scroll, and sends it to RizzBot as a new girl.

This repo holds the installer only. It is published here so anyone can download it without a GitHub account.

## What you need

- A Windows 10 or 11 PC.
- An **Android** phone running Android 5 or newer. iPhone is not supported by this app.
- A USB cable that carries **data**, not a charge-only cable. The one that came with the phone is usually fine. If the phone charges but the app never sees it, try another cable or another USB port.
- A RizzBot account.

## 1. Download and install

Download **[RizzBotRecorder-setup.exe](https://github.com/rizzbotdev/rizzbot-recorder/releases/latest/download/RizzBotRecorder-setup.exe)** (latest version). Older versions are on the [releases page](https://github.com/rizzbotdev/rizzbot-recorder/releases).

Run it. It installs for your user only, so Windows asks for no admin rights, and it adds a Start Menu entry, an optional desktop shortcut and an uninstaller. Installing over an older version keeps the PC connected.

Windows warns about an unknown publisher the first time, because the file is not code signed. Click **More info**, then **Run anyway**.

Everything the app needs (the mirror and adb) is bundled. You do not need to install Android Studio or any drivers.

## 2. Set up the phone (once)

### Turn on Developer options

1. Open **Settings > About phone**.
2. Tap **Build number** 7 times in a row. Enter your PIN if asked. You will see "You are now a developer".

Where Build number sits on common phones:

| Phone | Path |
|---|---|
| Google Pixel, most Android One phones | Settings > About phone > Build number |
| Samsung | Settings > About phone > Software information > Build number |
| Xiaomi, Redmi, POCO | Settings > About phone > tap **OS version** (or **MIUI version**) 7 times |
| OnePlus, OPPO, Realme | Settings > About device > Version > Build number |
| Motorola | Settings > About phone > Build number |
| Huawei, Honor | Settings > About phone > Build number |

If your phone is not listed, search Settings for "Build number".

### Turn on USB debugging

1. Open **Developer options**. It is usually in **Settings > System > Developer options**, or at the bottom of the main Settings list (Samsung), or in **Settings > Additional settings > Developer options** (Xiaomi, OnePlus, OPPO, Realme).
2. Make sure the switch at the top of Developer options is **On**.
3. Turn on **USB debugging** and confirm.

### Extra switches on some phones

These let you scroll the phone with the mouse in the mirror. Without them the mirror shows, but clicks and scrolls do nothing.

- **Xiaomi, Redmi, POCO:** in Developer options also turn on **USB debugging (Security settings)**. It needs a Xiaomi account signed in and sometimes a SIM card inserted. Turn off **MIUI optimization** as well if scrolling still does nothing.
- **OPPO, Realme:** in Developer options turn on **Disable permission monitoring** if it is there.
- **Huawei, Honor:** in Developer options turn on **Allow ADB debugging in charge only mode** if it is there.

### Recommended

- **Stay awake** (in Developer options): keeps the screen on while the phone is plugged in, so it does not lock in the middle of a recording.
- Unlock the phone before you start, and keep it unlocked while recording.

## 3. First connection

1. Plug the phone into the PC.
2. Start **RizzBot Recorder** from the Start Menu.
3. The phone shows **"Allow USB debugging?"** with the PC's key fingerprint. Tick **Always allow from this computer**, then tap **Allow**.
   - No popup? Unplug and replug the cable, and unlock the phone. On some phones pull down the notification shade, tap the USB notification and choose **File transfer**, then replug.
   - Still nothing? In Developer options tap **Revoke USB debugging authorizations**, then replug.
4. The phone's screen appears in a window on the PC with a bar docked above it.
5. Press the **gear** in the bar, then **Connect**. Your browser opens the RizzBot site. Press **Connect this PC** there. The bar says `connected as <your email>`. If the browser could not hand the code back to the app, the page shows a code: paste it into the Code field in the gear.

You only do this once per PC. Connected PCs are listed on the site under Me > Phone recorder, where you can disconnect any of them.

## 4. Record a profile

1. Open the dating app on the phone and go to her profile.
2. Press **REC** in the bar and wait for the 3-2-1.
3. Scroll her profile **slowly** in the mirror (mouse wheel, or on the phone itself). Let each photo settle fully on screen before moving on.
4. Press **STOP**.

The bar shows the upload, then the parse, then her name. Click it to open her page. You can record the next one while the previous is still uploading. A failed upload waits in the bar; click the text to retry.

## What the bar is telling you

| Message | What to do |
|---|---|
| plug the phone in with USB debugging on | The PC does not see the phone. Check the cable (data, not charge-only), that USB debugging is on, and try another USB port. |
| allow USB debugging on the phone (the popup on its screen) | Unlock the phone and tap Allow on the popup. Tick Always allow. |
| waiting for the browser - press Connect there | Finish the Connect step in the browser tab that opened. |

## Troubleshooting

- **The mirror shows but the mouse does nothing:** see "Extra switches on some phones" above.
- **The phone is never detected on a Samsung:** install the [Samsung USB driver](https://developer.samsung.com/android-usb-driver), then replug.
- **The mirror window closed:** closing it quits the app. Start RizzBot Recorder again.
- **Unplugged by accident:** plug back in. The app waits for the phone and starts the mirror again by itself.

The mirror is [scrcpy](https://github.com/Genymobile/scrcpy), bundled with the installer. Recording happens entirely on the PC, so the phone does not start a screen recording of its own.
