# Bundle Bridge v1.1.5 Beta 6

This is a **beta/pre-release** of Bundle Bridge, an independent Windows companion app for FL Studio. Save selected Generator, Audio Clip, and Layer channels together with associated Mixer track settings, then reuse them in another project.

## Requirements

- Windows 10/11 x64; .NET Framework 4.8
- FL Studio MIDI scripting API 38 or newer
- A separately installed virtual MIDI driver (e.g. loopMIDI) with ports `FLBundleBridge` and `FLBundleBridge_Return`

## Installing

1. Download `BundleBridge_Setup_v1.1.5_Windows_x64.exe` from **Assets** below.
2. Run the Windows installer.
3. Follow the [SETUP guide](https://github.com/geranouifersjhfio/BundleBridge-Downloads/blob/main/SETUP.md) to install the FL Studio Python controller script and configure the virtual MIDI ports.

The installer does not install loopMIDI and does not automatically register the controller script inside FL Studio.

## Beta notice

**Back up important FL Studio projects and test with a disposable project first.** Channel cleanup and Mixer restoration are not guaranteed under all FL Studio or plugin states. End-to-end compatibility of this uploaded installer has not been independently verified here.

Bundle Bridge is an independent third-party project, not affiliated with or endorsed by Image-Line.
