# Third-party formats and code ported into the web decoders

Belongs with NOTICE.md ("Third-party components bundled in the app"). Only permissively licensed sources
(MIT / Apache-2.0 / BSD) were ported; GPL/AGPL projects were used at most as algorithm or specification
references, never copied.

| File | Ported from | Licence | What |
|---|---|---|---|
| `web/wifiofdm.js` | FutureSDR `examples/wlan` (https://github.com/FutureSDR/FutureSDR), © the FutureSDR authors | Apache-2.0 | 802.11a/g/p OFDM receiver and transmitter structure: STF lag-16 plateau detector and threshold (`sync_short.rs`), L-LTF correlation / fine CFO (`sync_long.rs`), channel estimate, pilot phase, SIGNAL decode and rate table (`frame_equalizer.rs`), deinterleaver / descrambler / FCS (`decoder.rs`), convolutional code polynomials and puncturing (`viterbi_decoder.rs`), encoder / mapper / pilots / L-LTF (`encoder.rs`, `mapper.rs`, `lib.rs`). Changed: soft-decision demapping and Viterbi, DC removal, extra false-frame checks, JavaScript. |
| `web/bleads.js` | bthome-ble (https://github.com/Bluetooth-Devices/bthome-ble) | MIT | BTHome v2 object table (IDs, lengths, factors, events); test vectors in `tools/test_bleads.mjs` |
| `web/bleads.js` | xiaomi-ble (https://github.com/Bluetooth-Devices/xiaomi-ble) | Apache-2.0 | MiBeacon frame-control layout, object IDs, device-ID table excerpt; test vectors in `tools/test_bleads.mjs` |
| `web/bleads.js` | ble_monitor (https://github.com/custom-components/ble_monitor) | MIT | pvvx / ATC1441 0x181A layouts, Govee H5xxx layouts |
| `web/bleads.js` | ruuvitag-sensor (https://github.com/ttu/ruuvitag-sensor) + docs.ruuvi.com | MIT | Ruuvi data formats 3 and 5 |
| `web/bleads.js` | AirGuard (https://github.com/seemoo-lab/AirGuard), © SEEMOO / TU Darmstadt | Apache-2.0 | Tracker types and status bits (Apple Find My status byte, Samsung SmartTag state / privacy ID / aging counter, Google FMDN 0x40/0x41, Tile 0xFEED, Chipolo 0xFE33) and the tracking criteria (≥ 3 sightings, minimum tracking time, 150 min for Apple devices, Samsung aging-counter linking) |
| `web/thread.js` | OpenThread (https://github.com/openthread/openthread) | BSD-3-Clause | MLE command / TLV numbers, MeshCoP TLV numbers, discovery TLV flag layout, 802.15.4-2015 PAN-ID compression table, header IE IDs |
| `web/thread.js` | zigbee-herdsman / zigbee-herdsman-converters (https://github.com/Koenkk) | MIT | ZCL cluster IDs/names, Green Power command IDs |
| `web/remoteid.js` | classg (https://github.com/lnorton89/classg), `parsers/dji.py`, `docs/research/04-protocol-dji.md` | MIT | Legacy DJI Wi-Fi DroneID vendor IE (OUI 26:37:12) field layout and scale hypotheses |
| `web/wifib.js` | espressif/esp-now (https://github.com/espressif/esp-now) / ESP-IDF docs | Apache-2.0 | ESP-NOW action-frame format (category 127, OUI 18:FE:34, type 4) |

Specifications used directly (no code): Bluetooth Core 5.4 Vol 6 Part B (2M / Coded PHY, extended advertising),
Bluetooth Assigned Numbers (Auracast 0x1852 / 0x1856, AD type 0x30), IEEE 802.11-2020 clause 17, IEEE 802.15.4-2015,
RFC 4944 / RFC 6282, Zigbee PRO / Green Power, ASTM F3411-22a, Eddystone / iBeacon, Matter core spec (BLE commissioning
advertisement), Google Fast Pair and Find My Device Network, Microsoft Swift Pair. Apple Continuity message names:
Martin et al., "Handoff All Your Privacy", PETS 2019.

Apache-2.0 sources: the notices above satisfy the attribution requirement; no NOTICE files were shipped by those
projects for the ported parts.
