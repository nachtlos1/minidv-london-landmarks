# Filming London Landmarks on MiniDV and Transferring to PC over FireWire

I bought a **Sony DCR-TRV19E** MiniDV camcorder from the early 2000s, filmed landmarks across London on tape, then transferred the footage to my Windows 11 PC using **FireWire (IEEE 1394)**.

Getting video off a 20-year-old tape camcorder and onto a modern PC turned out to be a proper hardware and software troubleshooting project: old interfaces, missing ports, driver choices and large video files.

---

## Contents

1. [The kit](#the-kit)
2. [Why FireWire, not USB](#why-firewire-not-usb)
3. [Connecting the camera](#connecting-the-camera)
4. [Capturing the footage](#capturing-the-footage)
5. [After capture: storing and sharing](#after-capture-storing-and-sharing)
6. [Troubleshooting](#troubleshooting)
7. [What I learned](#what-i-learned)

---

## The kit

| Item | Detail |
|---|---|
| Camcorder | Sony Handycam **DCR-TRV19E** (PAL/European model) |
| Recording format | **MiniDV** tape: digital video (DV) recorded onto a cassette |
| Camera's digital output | **i.LINK**, Sony's name for FireWire / IEEE 1394 (4-pin port) |
| Cable | FireWire cable: 4-pin at the camera end, to match the PC's FireWire port |
| PC | Ryzen 7 7800X3D, RTX 5070, Windows 11 |
| Footage | Landmarks around London |

---

## Why FireWire, not USB

The DCR-TRV19E has a USB port, but on these camcorders USB is mainly for still photos and webcam use. It **does not transfer the tape video at full quality**.

MiniDV records video **digitally** on the tape. Over FireWire the camera sends that exact digital stream to the PC, so the copy is identical to what's on the tape, with **no quality loss**. That's why FireWire is the right way to transfer MiniDV.

**The catch:** modern PCs and motherboards no longer come with FireWire ports. A desktop needs a **PCIe FireWire (IEEE 1394a) card** added to provide the port.

---

## Connecting the camera

1. **Power the camera from its AC adapter**, not the battery, so it doesn't die mid-transfer.
2. **Connect the cable with everything switched off.** FireWire ports can be damaged by plugging in while devices are powered on ("hot-plugging"), so connect first, then power on.
3. **Put the camera in PLAY/VCR mode** with the tape inserted. Capture software controls playback over the FireWire link.
4. **Check Device Manager** in Windows: the FireWire controller appears under *IEEE 1394 host controllers*.

### FireWire drivers on Windows 11

Windows 11 includes its own 1394 driver, and there is also an older **"1394 OHCI Compliant Host Controller (Legacy)"** driver. If the camera isn't detected with one driver, switching to the other is a common fix. You can see which one is active in Device Manager: the legacy one has "(Legacy)" at the end of its name.

---

## Capturing the footage

Free, lightweight capture tools such as **WinDV** or **Scenalyzer** talk directly to the camera:

1. Open the capture software. It should show the camera's video when the tape plays.
2. Rewind the tape to the start.
3. Start capture. The software plays the tape and records the DV stream to the PC.
4. Captured files are saved as **DV AVI**, an exact copy of the tape.

**File sizes are large.** DV runs at about **25 Mbit/s**, which is roughly **13 GB per hour** of footage, so capture to a drive with plenty of free space.

---

## After capture: storing and sharing

| Step | Why |
|---|---|
| **Keep the original DV AVI files** as the master copy | They're lossless copies of the tape. Tapes degrade over time, so these are the archive |
| **Back them up** to a second drive | One copy is no copy |
| **Convert copies to MP4 (H.264)** for sharing | Much smaller files that play everywhere and upload easily |
| **Deinterlace when converting** | MiniDV video is interlaced (made for old TVs). Without deinterlacing, fast motion shows "comb" lines on modern screens |
| **Keep the 4:3 aspect ratio** | The footage is standard definition (PAL, 720×576). Stretching it to 16:9 makes everything look wide |
| **Organise files by landmark and date** | Makes clips easy to find later |

---

## Troubleshooting

| Problem | Likely cause | Fix |
|---|---|---|
| PC has nowhere to plug the cable in | Modern PCs have no FireWire port | Install a PCIe FireWire (IEEE 1394a) card |
| Camera not detected | Wrong driver, or camera not in PLAY/VCR mode | Check the camera mode, try the other Windows 1394 driver (standard or Legacy) |
| Capture software sees the camera but no picture | Driver or software quirk | Try a different capture program (e.g. WinDV vs Scenalyzer); restart with a tape playing |
| Transfer stops partway | Battery died, or a tape dropout | Use the AC adapter; clean the heads if dropouts repeat |
| Video looks stretched | 4:3 footage shown as 16:9 | Set 4:3 aspect ratio when converting |
| Lines on moving objects | Interlaced video | Deinterlace during conversion |

---

## What I learned

- **Legacy hardware still needs modern support.** Getting old and new hardware to talk meant adding the right expansion card and choosing the right driver.
- **Digital vs analogue transfer:** MiniDV over FireWire gives a perfect digital copy, which is why it beats capturing from the analogue AV output.
- **Device Manager and drivers:** checking which driver a device uses, and switching drivers when one doesn't work.
- **Video basics:** codecs, interlacing, aspect ratios and how much storage video needs.
- **Data preservation:** keep a master copy, back it up, and only share converted copies.

---

*Author: [nachtlos1](https://github.com/nachtlos1) · CompTIA A+ · CompTIA Network+*
