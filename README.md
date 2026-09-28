# RizzBot Recorder

A Windows app that mirrors your Android phone on the PC over USB, records a profile scroll, and sends it to RizzBot as a new girl.

This repo holds the installer only. It is published here so anyone can download it without a GitHub account.

## Download

**[RizzBotRecorder-setup.exe](https://github.com/rizzbotdev/rizzbot-recorder/releases/latest/download/RizzBotRecorder-setup.exe)** (latest version). Older versions are on the [releases page](https://github.com/rizzbotdev/rizzbot-recorder/releases).

## Install

Run `RizzBotRecorder-setup.exe`. It installs for your user only, so Windows asks for no admin rights, and it adds a Start Menu entry, an optional desktop shortcut and an uninstaller. Installing over an older version keeps the PC connected.

Windows warns about an unknown publisher the first time, because the file is not code signed. Click "More info", then "Run anyway".

## First run

Turn on USB debugging on the phone, plug it in, and tap Allow on the phone. Press the gear in the bar, then Connect: your browser opens the RizzBot site, you press Connect this PC, done.

## Record

Press REC, wait for the countdown, scroll her profile slowly in the mirror, then press STOP. The bar shows the upload and the parse, then her name. Click it to open her page.

The mirror is [scrcpy](https://github.com/Genymobile/scrcpy), bundled with the installer.
