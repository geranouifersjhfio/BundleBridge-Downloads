# Bundle Bridge — Windows Downloads

**Bundle Bridge v1.1.5 Beta 6** is an independent Windows companion app for FL Studio. It helps you save selected Generator, Audio Clip, and Layer channels with associated Mixer track states, then reuse those Bundles in other projects.

**[Download the Windows installer from Releases](https://github.com/geranouifersjhfio/BundleBridge-Downloads/releases)**

> **Beta software:** This build is for testing. Back up important FL Studio projects and try it on a disposable project first. Mixer restoration and cancellation cleanup are best-effort and are not guaranteed to recover every FL Studio/plugin state.

## Requirements

- Windows 10 or 11, 64-bit
- .NET Framework 4.8
- FL Studio with MIDI scripting API **38 or later**
- FLBundleBridgeDesktop MIDI controller script **v0.5.4** (supplied with the installer)
- A separately installed virtual MIDI driver, such as [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html), with ports named `FLBundleBridge` and `FLBundleBridge_Return`

## Install

1. Download `BundleBridge_Setup_v1.1.5_Windows_x64.exe` from the latest beta Release's **Assets** section.
2. Install and launch Bundle Bridge.
3. Follow the **[setup guide](SETUP.md)** to copy the FL Studio controller script and configure the two MIDI ports.

The installer does **not** install loopMIDI or automatically register the MIDI script with FL Studio.

## Features

- Save and reuse FL Studio Bundles
- Compact window mode and left/right screen-edge snapping
- Dark, Gray, Light, and Custom themes
- Custom background and animation colors
- Send deleted Bundle folders to the Windows Recycle Bin where available

## Distribution and independence

This repository contains **download information and setup documentation only**. The application's development repository and source code are not published here. GitHub's automatic *Source code (zip/tar.gz)* downloads for this repository contain these documentation files, **not the application source**.

The installer contains the compiled Windows application and an FL Studio Python controller script required for operation; the Python script is readable after installation, and compiled .NET software can be inspected or decompiled. This repository's structure does not prevent that.

Bundle Bridge is an independent third-party project, not affiliated with or endorsed by Image-Line. loopMIDI is a separate third-party product and is not included in Bundle Bridge.
