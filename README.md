<p align="center">
  <img src="assets/logo.svg" width="160" alt="ESPsoup logo: a soup bowl with a ladle scooping a clean signal out of a noisy spectrum">
</p>

<h1 align="center">ESPsoup</h1>
<p align="center"><b>Scoop signals from the frequency soup.</b><br>
A receive-only radio scanner app for the ESP32-C5 — Android, Windows and the browser.</p>

<p align="center"><i>🍲 Public beta 0.2 (app 0.12.9) · <a href="https://github.com/pit711/ESPsoup/releases/latest">Android APK</a> · <a href="https://app.espsoup.com/">web app</a> · Windows app coming soon.</i></p>

<p align="center">
  <a href="https://app.espsoup.com/"><img src="https://img.shields.io/badge/web%20app-app.espsoup.com-e8590c" alt="Web app"></a>
  <a href="https://espsoup.com/"><img src="https://img.shields.io/badge/website-espsoup.com-1f6feb" alt="Website"></a>
  <a href="https://ko-fi.com/711it"><img src="https://img.shields.io/badge/Ko--fi-support-ff5e5b?logo=ko-fi&logoColor=white" alt="Ko-fi"></a>
  <a href="https://paypal.me/711IT"><img src="https://img.shields.io/badge/PayPal-tip-00457C?logo=paypal&logoColor=white" alt="PayPal"></a>
</p>

---

The air around you is a soup of radio signals. ESPsoup turns a cheap **ESP32-C5** board, plugged into your phone or PC by USB,
into a pocket spectrum scanner for the **2.4 GHz and 5 GHz bands**. It shows what's cooking and scoops out whatever it can decode —
Bluetooth, Wi-Fi, Zigbee, Thread, drones, mobile cells, cars (ITS-G5) and live analog FPV video on its own little TV.
Everything is decoded locally on your device, and ESPsoup never transmits.

**23 languages:** English, Deutsch, Українська, Български, Čeština, Ελληνικά, Español, Français, हिन्दी, Hrvatski, Magyar, Bahasa Indonesia,
Italiano, 日本語, 한국어, Nederlands, Polski, Português (Brasil), Română, Svenska, Türkçe, Tiếng Việt, 简体中文 — picked from the phone's or browser's language, or under Device → Language.

## Four tabs, two or three taps

The 0.12 interface has four areas. Every function is at most two or three taps away.

| Tab | What's in it |
|---|---|
| **Scan** | Type a signal type (*ELRS*, *AirTag*, *HDZero* …) and search it in one tap — or tap ingredients and hit **Search ingredients (n)**, or just **Search everything**. Every find has **Find** and ▶. |
| **Spectrum** | Live spectrum and waterfall. Type a frequency like in SDR software — `2437`, `5.8G`, `2437.5`. Frequencies the chip can't reach are marked, with the reason and the nearest receivable one. |
| **Tools** | **TV**, Panorama (live, with its own start/stop), Wi-Fi channels (now and over 24 h), Find on any frequency with a GPS heatmap, Burst catcher, Map, Recordings, Identify. |
| **Device** | Firmware flasher (backup first, every write verified), calibration, second board, notifications, MQTT export, settings. |

### Scan

| Ingredients | Signal-type search | Finds |
|---|---|---|
| <img src="assets/screenshots/scan-ingredients.png" width="250"> | <img src="assets/screenshots/scan-search-elrs.png" width="250"> | <img src="assets/screenshots/scan-finds.png" width="250"> |
| *Tap ingredients → “Search ingredients (3)”* | *Type “ELRS” — band, classifier, one-tap search* | *Wi-Fi, Bluetooth, trackers — each with Find* |

### Spectrum and Tools

| Type a frequency | Honest tuning | Panorama |
|---|---|---|
| <img src="assets/screenshots/freq-typing.png" width="250"> | <img src="assets/screenshots/freq-gap.png" width="250"> | <img src="assets/screenshots/pano-all.png" width="250"> |
| *`5.8G` → 5800 MHz, UNII-3* | *3500 MHz is in the chip's gap — marked, with the nearest frequency* | *Live sweep over everything receivable* |

| Tools | Find (hot/cold) | Wi-Fi channels |
|---|---|---|
| <img src="assets/screenshots/tools-tv.png" width="250"> | <img src="assets/screenshots/find.png" width="250"> | <img src="assets/screenshots/wifi-channels.png" width="250"> |
| *TV, Panorama, Find, Burst catcher, Map, Recordings* | *Walk around — the pot gets hotter as you get closer* | *Occupancy now and over 24 h* |

| Identify | Light theme | Measuring tip |
|---|---|---|
| <img src="assets/screenshots/identify.png" width="250"> | <img src="assets/screenshots/light-scan.png" width="250"> | <img src="assets/screenshots/airplane-hint.png" width="250"> |
| *“What is this?” — classifier on any frequency* | *Light and dark* | *Airplane mode before measuring* |

## 📺 ESPsoup TV

**Tools → TV** is an analog video receiver. Pick a channel table — **Raceband, Fatshark, Boscam A / B / E, Lowband, 2.4 GHz AV** —
or type any frequency. The picture starts at once (snow when there's nothing on air), with PAL / NTSC / auto,
channel ◀ ▶, seek, an auto cycle with adjustable interval and *stop on a picture*, and fullscreen.

| Raceband R5 | No signal = snow | Any frequency |
|---|---|---|
| <img src="assets/screenshots/tv-r5.png" width="250"> | <img src="assets/screenshots/tv-snow.png" width="250"> | <img src="assets/screenshots/tv-free-5800.png" width="250"> |
| *5806 MHz, PAL, ~25 fps* | *Picture right away, even without a sender* | *5800 MHz typed in, NTSC detected* |

| 2.4 GHz AV sender | Switching channels | Colour (rough) |
|---|---|---|
| <img src="assets/screenshots/tv-av-2414.png" width="250"> | <img src="assets/screenshots/tv-switch.gif" width="250"> | <img src="assets/screenshots/tv-colour-pal.png" width="250"> |
| *AV1, 2414 MHz* | *R5 → R6 (empty) → R5* | *PAL colour bars, ESPsoup firmware* |

| Colour in fullscreen | Live video, 2.4 GHz AV |
|---|---|
| <img src="assets/screenshots/tv-colour-fullscreen.jpg" width="400"> | <img src="assets/screenshots/live-video.gif" width="400"> |
| *Rough PAL colour — NTSC works too* | *2434 MHz, demodulated on the ESP32 itself* |

<img src="assets/screenshots/tv-52-channels.jpg" width="760" alt="Grid of 52 TV screenshots, one per receivable FPV and 2.4 GHz AV channel, each showing the ESPsoup test picture">

*All 52 receivable channels with a picture: Raceband, Fatshark, Boscam A/B/E, Lowband (5362–5945 MHz) and 2.4 GHz AV (2414–2468 MHz).*

**Tested with a lab signal generator:** 52 of 52 receivable channels gave a picture, about **25 frames/s** and **~7,900 lines/s**.
The ESP32 demodulates the video itself (ESPsoup firmware 0.7.1), in black and white or with rough colour (PAL and NTSC).
The 1.2/1.3 GHz FPV band can't be received by the ESP32-C5, and digital systems (DJI, HDZero, Walksnail) are only recognised, without a picture.

### Recording

**● Record** saves the picture as a WebM video (plays in VLC, browsers and most players): channel, frequency, norm, SNR and time
burned in, the original picture also in red night mode, long recordings split into 10-minute files. **⟲ Last 30 s** saves the
last 30 seconds from memory — after the drone has already flown by. With several boards, *All pictures in one video* records the
whole Multi-TV grid.

<img src="assets/screenshots/tv-recording-multi.png" width="760" alt="Frame of a Multi-TV recording: left picture snow on AV2 2432 MHz, right picture the ESPsoup test picture on 2462 MHz, with burned-in channel, frequency, SNR and time">

*Frame of a two-board recording: left 2432 MHz (no sender), right 2462 MHz test picture, with the burned-in info line.*

<sub>Phone screenshots from an Android phone with an ESP32-C5 on USB-OTG. Addresses of real neighbours are masked, and no map or heatmap of a real location is shown.</sub>

## What works, what partly works, what doesn't

The ESP32-C5 is a Wi-Fi chip, not a lab SDR. This is what ESPsoup really does with it — tested on real air and
with recorded signals (October 2026).

✅ works · ◐ partly (recognised, but not fully decoded or not reliable yet) · ❌ not possible

| | Signal / feature | Frequency | Notes |
|---|---|---|---|
| | **Spectrum and tools** | | |
| ✅ | Live spectrum, waterfall, frequency entry | 2.13–2.73 · 4.79–5.99 GHz | Up to 80 MHz wide; unreachable frequencies are refused with the reason |
| ✅ | Panorama live, own start/stop | any receivable range | About 15 sweeps/s over 2.4 GHz; gaps are skipped |
| ✅ | Find (hot/cold) with GPS heatmap | any receivable frequency | Usable over about 25–30 dB; the heatmap stays on your device |
| ✅ | Find locks on a Bluetooth device by its address or payload ID | 2402 · 2426 · 2480 MHz | Tracker ID, iBeacon, Eddystone, Auracast; follows a rotating private address; about 13 readings/s |
| ✅ | Gap-free reception, burst catcher | same ranges | |
| ✅ | Alarm tool: alerts for new signals, watch and ignore lists, critical alarms | all | On Android also in the background and with the screen off |
| | **Bluetooth** | | |
| ✅ | BLE advertising: names, sensors (BTHome, Xiaomi, Govee, Ruuvi), iBeacon, Eddystone | 2402 · 2426 · 2480 MHz | |
| ✅ | AirTag and tracker warning | 2.4 GHz | AirTag, SmartTag, Tile, Google trackers — warns if one keeps showing up around you |
| ✅ | BLE 2M and extended advertising | 2.4 GHz | |
| ✅ | Bluetooth packet catcher, 60–120 packets/s | 2.4 GHz | Demodulated on the chip |
| ◐ | BLE Coded (Long Range) | 2.4 GHz | Seen in the spectrum, not decoded yet |
| ◐ | Bluetooth Classic | 2.4 GHz | Device address part (LAP) from the access code |
| ◐ | AirPods battery and case, Apple Nearby / Handoff / AirDrop / HomeKit, Bluetooth Mesh, Windows Swift Pair | 2402 · 2426 · 2480 MHz | |
| | **Wi-Fi and cars** | | |
| ✅ | Wi-Fi 802.11b/g/a (incl. 5 GHz OFDM): network names from beacons | 2.4 · 5 GHz | Including the channels above 5.75 GHz |
| ✅ | ESP-NOW, searching phones (anonymous count), deauth alarm | 2.4 GHz | |
| ✅ | Wi-Fi channel occupancy | 2.4 · 5 GHz | Now and over 24 hours |
| ◐ | Wi-Fi details: security, Wi-Fi 6/7, WPS, Apple AWDL, Wi-Fi Direct, OpenIPC / wfb-ng FPV | 2.4 · 5 GHz | |
| ✅ | ITS-G5 / 802.11p (car-to-car V2X) | 5.855–5.925 GHz | |
| | **Smart home and sensors** | | |
| ✅ | Zigbee, Zigbee Green Power, Thread (802.15.4) | 2405–2480 MHz | |
| ✅ | nRF24, Hoymiles solar inverters | 2.4 GHz | |
| ◐ | MiLight remotes, wireless mice and keyboards (ESB 2 Mbit/s) | 2.4 GHz | Keystrokes stay encrypted |
| ✅ | ANT+ fitness sensors | 2457 MHz | |
| ✅ | Microwave oven | ≈ 2.45 GHz | Recognised while it runs |
| | **Drones and remote controls** | | |
| ✅ | Drone Remote ID (Bluetooth, Wi-Fi beacon, Wi-Fi NAN) | 2.4 · 5 GHz | Drone and pilot position on the map |
| ✅ | LoRa 2.4 GHz decoder, ExpressLRS with packet rate | 2.4 GHz | Spreading factor, bandwidth, sync word; ELRS control data stays unreadable |
| ◐ | RC links: FLRC, Ghost, Tracer, FrSky, FlySky, DSMX | 2.4 GHz | Recognised by the classifier; exact link type sometimes unsure; control data not decoded |
| ✅ | DJI DroneID (OcuSync 2/3) | 2.4 · 5.8 GHz | Serial number, model, drone and pilot position on the map |
| ✅ | DJI O4 video link | 2.4 · 5.8 GHz | Recognised by its 30 kHz OFDM signature; DroneID of O4 drones is encrypted |
| ◐ | Autel drones (SkyLink) | 2.4 · 5.8 GHz | Video and control link, told apart from DJI; encrypted, detect only |
| | **Video** | | |
| ✅ | ESPsoup TV: Raceband, Fatshark, Boscam A/B/E, Lowband, 2.4 GHz AV or any frequency | 5362–5945 · 2414–2468 MHz | 52 of 52 channels with a picture, ~25 fps; seek, auto cycle, fullscreen |
| ◐ | Colour in the TV picture (PAL / NTSC) | same | Rough colour; black and white is the reliable default |
| ✅ | Analog FPV video and 2.4 GHz wireless cameras, live | 5.36–5.95 · 2.41–2.47 GHz | Demodulated on the ESP32 |
| ◐ | Digital video: HDZero, Walksnail, OcuSync, DVB-T senders | 2.4 · 5.8 GHz | Recognised, but no picture — digital video is too much for the ESP32 |
| | **Mobile network and the rest** | | |
| ◐ | LTE / 5G NR cell towers | B1, B7, B38, B40, B41, n1, n7, n38, n40, n41, n79 | Cell identities and TDD frame pattern; depends on your surroundings; also calibrates the board's crystal |
| ◐ | Phones nearby (LTE / 5G uplink) | band 7 uplink (2.50–2.57 GHz) | Transmitting phones by their uplink bursts; no identities |
| ◐ | Pulse radar (weather radar, DFS patterns), road-toll beacons (CEN-DSRC) | 5.6 · 5.8 · 2.7 GHz | Pulse width and repetition rate |
| ✅ | Radar, FMCW, CW and NBFM carriers | 2.4 · 5 GHz | Recognised by their shape; nothing to decode |
| | **Not possible with the ESP32-C5** | | |
| ❌ | FM, DAB+, 433/868 MHz sensors, LoRa below 1 GHz, 1.2/1.3 GHz FPV, ADS-B, GPS, DECT, LTE bands 3/8/20 | below 2.1 GHz | The chip can't tune there |
| ❌ | 5G n78 (3.5 GHz), C-band | 2.75–4.79 GHz | A gap in the tuning range |
| ❌ | Wi-Fi 6E, 10 GHz, QO-100 | above 6 GHz | The radio ends below 6 GHz |
| ❌ | Calls, audio, message contents | – | By design: ESPsoup only shows public broadcast information |

**Bottom line:** a good 2.4/5 GHz scanner and decoder for about **2.13–2.73 GHz and 4.79–5.99 GHz** — with live analog video, drone Remote ID and LTE/5G cell identities. It is not a broadband SDR.

> **Measuring?** Put your phone in **airplane mode**, or at least switch off its Wi-Fi and Bluetooth — they transmit a few centimetres
> from the ESP32 and would be the loudest ingredient in the soup. USB-OTG and GPS keep working. The app reminds you.

## Firmware

ESPsoup needs the **[ESPsoup firmware 0.7.1](https://github.com/pit711/espsoup-firmware/releases/tag/v0.7.1)** on the board —
open source under GPL-3.0, a fork of the **[ESP-SDR firmware by ESPARGOS](https://github.com/ESPARGOS/esp-sdr)**, which turns the
ESP32-C5's Wi-Fi radio into an I/Q receiver. Both the Android app and the browser app ship it: **Device → Firmware** backs up the board first,
flashes and verifies every image. Compared with ESP-SDR it adds:

- **gap-free reception** instead of snapshots (burst catcher, packet catcher),
- the **5.9 GHz extension** up to 5990 MHz (upper 5.8 GHz band, ITS-G5),
- **video and Bluetooth demodulation on the chip** — that's what makes the live TV at ~25 frames/s possible.

## Coming next

- **Windows app** — coming soon. Android: [beta APK](https://github.com/pit711/ESPsoup/releases/latest); browser: [app.espsoup.com](https://app.espsoup.com/).
- Better colour in the TV picture.
- Decoding BLE Long Range, surer identification of RC links.

## What you need

Any **ESP32-C5** board works — it is the only ESP32 with the 5 GHz radio ESPsoup needs. Three boards we test with:

| <a href="https://espsoup.com/go/c5-ext"><img src="https://espsoup.com/amzimg/c5-ext" width="170" alt="Waveshare ESP32-C5 board with external antenna connector"></a> | <a href="https://espsoup.com/go/c5-xiao"><img src="https://espsoup.com/amzimg/c5-xiao" width="170" alt="Seeed Studio XIAO ESP32-C5"></a> | <a href="https://espsoup.com/go/c5-pcb"><img src="https://espsoup.com/amzimg/c5-pcb" width="170" alt="Waveshare ESP32-C5 board with PCB antenna"></a> |
|:---:|:---:|:---:|
| **Dev board + antenna connector** ⭐ | **Mini · Seeed XIAO ESP32-C5** | **Dev board, PCB antenna** |
| ESP32-C5-WROOM-1U with U.FL — best reception, room for a better 2.4/5 GHz antenna | thumb-sized, U.FL connector — great as a second board | simplest option, fine for the 2.4/5 GHz recipes |
| [View on Amazon](https://espsoup.com/go/c5-ext) | [View on Amazon](https://espsoup.com/go/c5-xiao) | [View on Amazon](https://espsoup.com/go/c5-pcb) |

<sub>Affiliate links (ad). As an Amazon Associate I earn from qualifying purchases — it costs you nothing extra and keeps the soup cooking.
Product photos come from Amazon.</sub>

**Multi-TV:** one board shows one analog channel at a time, so it's one board per channel — 8 boards for a whole band (e.g. Raceband R1–R8).
Tested with 8 boards on one StarTech ST4300USB3V2-UE hub. Kit calculator (boards, antennas, cables, USB hub): https://espsoup.com/#multi-tv

Also needed:
- A USB-C data cable — plug into the board's **native USB** port, not the UART bridge port (CH340 etc.), which is too slow. On Android, a USB-OTG cable or adapter that carries data.
- The ESPsoup firmware 0.7.1 — the app installs it for you, see [Firmware](#firmware).
- On the PC: Chrome, Edge or another Chromium browser (Web Serial).

## Support

ESPsoup is a hobby project. If you like it, a small tip pays for test boards, antennas and coffee:

- ☕ **Ko-fi:** https://ko-fi.com/711it
- 💸 **PayPal:** https://paypal.me/711IT

## Credits

ESPsoup stands on the shoulders of these projects — thank you!

- **[ESPARGOS ESP-SDR](https://github.com/ESPARGOS/esp-sdr)** (GPL-3.0-or-later) — the I/Q receiver firmware for ESP32 chips that everything here builds on.
  The ESPsoup firmware is a fork of it; its hardware DC calibration is ported from ESP-SDR's ESP32-S31 streaming code.
- **[eSpDR](https://github.com/h0m3us3r/eSpDR)** by h0m3us3r (0BSD) — an ESP32-S3 software-defined radio that streams raw baseband I/Q samples
  at 80 MS/s with lossless compression and integrity checking. Thanks for the groundwork and for sharing it openly.
- **[C5VRX](https://github.com/konradit/C5VRX)** by konradit (GPL-3.0-only) — the idea of the gap-free capture path
  (modem diagnostic bus → GPIO loopback → PARLIO → circular DMA) and a tuning experiment (`phy_set_freq`). ESPsoup's implementation is
  independent; no C5VRX code was copied (see the firmware's NOTICE).
- **[FutureSDR](https://github.com/FutureSDR/FutureSDR)** (Apache-2.0) — the 802.11a/g/p OFDM receiver in the app is ported from its WLAN example.
- Formats and tables from **bthome-ble**, **xiaomi-ble**, **ble_monitor**, **ruuvitag-sensor**, **AirGuard** (SEEMOO / TU Darmstadt),
  **OpenThread**, **zigbee-herdsman**, **classg**, **ESP-NOW** and others — full list with licences in [THIRD_PARTY.md](THIRD_PARTY.md).

## Status

Public beta. The web app at [app.espsoup.com](https://app.espsoup.com/) and the Android beta are free to use.
A license for the ESPsoup app itself has not been chosen yet. The firmware is GPL-3.0: ESP-SDR by ESPARGOS is GPL-3.0,
and the ESPsoup firmware based on it is published under GPL-3.0 with full source.

ESPsoup only receives. Rules on receiving radio signals and on what you may do with the information differ between countries — use it responsibly.
ESPsoup is an independent project. It is not affiliated with Espressif Systems or with the ESPARGOS / ESP-SDR project. ESP32 is a trademark of Espressif Systems.
