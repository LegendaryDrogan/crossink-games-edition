# CrossInk Games Edition

Firmware releases for the **Xteink X4 Pro** pocket e-reader — a personal fork of
[CrossInk](https://github.com/uxjulia/crossink) that adds games and quality-of-life
improvements while keeping everything CrossInk does intact.

This repository hosts the release binaries. It exists so the reader can check for and
install its own updates over Wi-Fi.

---

## ⛔ X4 Pro only

These images are for the **Xteink X4 Pro** (ESP32-S3). They are **not** interchangeable with
the X3, the X4, or the X4 Classic — those are different hardware, and the X3/X4 use a
different chip entirely (ESP32-C3).

Every image carries an embedded board tag, and the firmware validates it before writing a
single byte, so a wrong-device image is refused rather than installed. Don't rely on that as
a plan, but it is there.

---

## Install

**On the device (easiest):** Settings → System → **Check for updates**. The reader finds the
newest release here, downloads it, verifies it, and installs it.

**From the SD card:** download `firmware.bin` below, copy it to the card, then on the device
go to Settings → System → **SD Card Firmware Update** and pick the file.

> **Latest image:** [`firmware.bin`](../../releases/latest/download/firmware.bin)

Each release ships the same image under more than one name:

| Asset | Why |
|---|---|
| `firmware.bin` | The stable name the one-tap link above points at. |
| `firmware-<version>.bin` | So a file sitting on an SD card can be identified later. |
| `firmware-x4-pro-v<version>.bin` | The name the device's own updater looks for. |

They are byte-identical — same image, three names.

---

## Recovery

Updates are written to the **inactive** slot, so the firmware you are currently running is
never overwritten by an install. If a new image misbehaves, hold **Down + Power** at boot to
reach the SD-card firmware picker and select a known-good `firmware.bin`.

**Keep a working `firmware.bin` on the SD card.** Automatic rollback is not reliable on this
hardware, and the device has no USB-C port — recovery goes through the SD picker.

---

## Built on

- **[CrossInk](https://github.com/uxjulia/crossink)** by Julia Nguyen — the firmware this is
  forked from, and where all the credit for the reader itself belongs.
- **[CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader)** — which
  CrossInk is in turn forked from.

Both are MIT licensed, as is this fork. See [LICENSE](LICENSE).

Games are deliberately out of scope upstream, which is why they live in a fork rather than in
a pull request. Nothing here is a criticism of either project — this is a personal build for
one device.
