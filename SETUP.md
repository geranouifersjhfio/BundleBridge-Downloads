# Bundle Bridge v1.1.5 Beta 6 — Setup Guide

This guide is for Windows users installing the prebuilt installer. You do **not** need to compile the app.

## 1. Requirements and beta precautions

- Windows 10/11, 64-bit and .NET Framework 4.8
- FL Studio with MIDI scripting API version 38 or newer
- Bundle Bridge's supplied FL Studio controller script v0.5.4
- A virtual MIDI driver (for example loopMIDI) installed separately

**Use a disposable FL Studio project for your first test and back up important projects.** The beta has not been confirmed on every system and plug-in setup.

## 2. Install Bundle Bridge

1. Open the [Releases page](https://github.com/geranouifersjhfio/BundleBridge-Downloads/releases) and select the beta release.
2. Under **Assets**, download `BundleBridge_Setup_v1.1.5_Windows_x64.exe`.
3. Run the installer and start Bundle Bridge.
4. If Windows warns about an unfamiliar or unsigned installer, verify that it came from the expected Release before deciding whether to proceed.

The default installation path is `%LOCALAPPDATA%\Programs\BundleBridge`.

**The installer does not install a MIDI driver or automatically copy the FL Studio script into FL Studio's data folder.**

## 3. Create the two virtual MIDI ports

1. Install a compatible virtual MIDI driver separately, such as [loopMIDI (official website)](https://www.tobias-erichsen.de/software/loopmidi.html). Check the third-party driver's terms for your intended use.
2. Create these two ports with the exact names:
   - `FLBundleBridge`
   - `FLBundleBridge_Return`
3. Keep the virtual MIDI driver running when using Bundle Bridge.

Open **Bundle Bridge > Settings** and choose:

| Bundle Bridge setting | MIDI device |
| --- | --- |
| Output (to FL Studio) | `FLBundleBridge` |
| Input (from FL Studio) | `FLBundleBridge_Return` |

These are device **names**, not the numeric ports configured inside FL Studio.

## 4. Install the FL Studio controller script

1. Press **Win + R** and open `%LOCALAPPDATA%\Programs\BundleBridge\FLBundleBridgeDesktop`.
2. Copy the entire `FLBundleBridgeDesktop` folder, including `device_BundleBridgeDesktop.py`.
3. Open your FL Studio user-data `Settings\Hardware` folder. A typical path is `%USERPROFILE%\Documents\Image-Line\FL Studio\Settings\Hardware`.
4. Paste the folder so it ends in `Hardware\FLBundleBridgeDesktop\device_BundleBridgeDesktop.py`.
5. If your Documents folder uses OneDrive or your FL Studio user-data location is customized, use the **actual FL Studio user-data folder**.
6. Restart FL Studio.

## 5. Configure MIDI devices in FL Studio

1. Open **Options > MIDI settings**.
2. Under **Output**, select `FLBundleBridge_Return` and enable it.
3. Under **Input**, select `FLBundleBridge`, enable it, and select **Controller type: BundleBridge Desktop**.
4. Give both FL Studio MIDI devices the **same numeric Port** (for example `102`, if available).
5. Check that Bundle Bridge uses the MIDI device names described in section 3.

The number 102 is only an example; matching input/output numeric port values are what matters.

## 6. First save/load test

1. Open a **test project** in FL Studio and stop playback.
2. Select Generator, Audio Clip, or Layer channels in the Channel Rack. Automation Clips are not supported. For a Layer, select the Layer and its children together.
3. Click **SAVE CURRENT FL** in Bundle Bridge.
4. To load, drag a saved Bundle from Bundle Bridge to FL Studio's **Channel Rack**.
5. When the Mixer starting-insert dialog appears, select where the Mixer tracks should be restored and confirm.
6. Verify imported channels and Mixer states before saving your FL Studio project.

If you cancel the Mixer starting-insert dialog, Bundle Bridge attempts to remove the channels imported by that load. If it cannot safely verify cleanup, it stops and reports that recovery is incomplete. Mixer loading/recovery is also best-effort.

## 7. Troubleshooting

- Make sure the virtual MIDI driver is running and both correctly named ports exist.
- Verify the selected FL Studio input controller type and that FL Studio MIDI port numbers match.
- Verify the Python script is in the actual FL Studio user-data `Hardware` folder, then restart FL Studio.
- API version error: FL Studio needs MIDI scripting API 38 or later.
- Script version error: reinstall the supplied v0.5.4 script into FL Studio's `Hardware` folder, then reconnect.
- For loading problems, stop playback and close other FL Studio dialogs and plugin windows before retrying.

## 8. Data and uninstall

By default, saved Bundles are kept in `Documents\BundleBridge`, outside the application installation folder. App settings are also stored separately under Local AppData. The installer/uninstaller does not intentionally delete these folders. Windows Recycle Bin availability varies and is not a guaranteed backup.
