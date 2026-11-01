
<div align="right">
  <details>
    <summary >🌐 Language</summary>
    <div>
      <div align="center">
        <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=en">English</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=zh-CN">简体中文</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=zh-TW">繁體中文</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=ja">日本語</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=ko">한국어</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=hi">हिन्दी</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=th">ไทย</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=fr">Français</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=de">Deutsch</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=es">Español</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=it">Italiano</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=ru">Русский</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=pt">Português</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=nl">Nederlands</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=pl">Polski</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=ar">العربية</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=fa">فارسی</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=tr">Türkçe</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=vi">Tiếng Việt</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=id">Bahasa Indonesia</a>
        | <a href="https://openaitx.github.io/view.html?user=iMike78&project=nest-mini-drop-in-pcb&lang=as">অসমীয়া</
      </div>
    </div>
  </details>

</div>


# MiciMike drop-in PCB replacement for Google Nest Mini

[MiciMike Nest Mini](https://github.com/iMike78/nest-mini-drop-in-pcb) is an open-source drop-in PCB replacement for the ["Google Nest Mini" (Google's second-generation smart speaker with a barrel connector charging port)](https://en.wikipedia.org/wiki/Google_Nest_(smart_speakers)). It is built around the ESP32-S3, ESP32-P4 and (optionally) ESP32-C6 and is meant to run open-source firmware, primarily [ESPHome](https://esphome.io).

Tip! If you are instead looking for a similar drop-in PCB replacement for the "Google Home Mini" (Google's first-generation smart speaker with a Micro-USB charging port), check out the sister project at https://github.com/iMike78/home-mini-v1-drop-in-pcb

Both are fully open-source hardware projects. They take concept inspiration from the [Onju Voice](https://github.com/justLV/onju-voice) and from the [Home Assistant Voice Preview Edition](https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/) by the Open Home Foundation and Nabu Casa.

# Project scope

The goal of this project is a custom replacement PCB for the Google Nest Mini (2nd Gen) that fits the original enclosure and reuses the original speaker, power supply, flex cable, mute switch and touch surface.

It primarily targets people who want to convert their old Google Nest Mini into an open-source [voice satellite for Home Assistant](https://www.home-assistant.io/voice_control/) and/or a media-player speaker for [Music Assistant](https://www.music-assistant.io). Because it is based on the Espressif ESP32 platform, the hardware can be used with other firmware as well.

### Relation to the Home Assistant Voice Preview Edition

Earlier revisions of this board followed the Voice Preview Edition (Voice PE) reference design closely, including its XMOS XU316 audio processor. The goal is still the same kind of device: a local, open voice assistant for Home Assistant running ESPHome, with on-device wake word detection and a cleaned-up microphone signal.

The hardware has since moved away from the Voice PE. Microcontroller technology has evolved beyond the XMOS-based approach, and this revision uses an ESP32-P4 for audio processing instead. The P4 may not outperform the XMOS in every respect, but it is a more open platform: it is programmed with Espressif's open-source ESP-IDF, the same ecosystem as the ESP32-S3 and ESPHome, instead of a separate proprietary toolchain. As a result, this board is **not hardware-compatible** with the Voice PE, and the Voice PE firmware does not run on it unchanged.

Developing new ESPHome features is out of scope for this repository. The Voice PE firmware remains a useful reference, and general features belong upstream in ESPHome:

- https://github.com/esphome/home-assistant-voice-pe
  - https://github.com/esphome/esphome
      - https://github.com/esphome/feature-requests

## Current status

> [!CAUTION]
> The rev 3 schematic and PCB are complete and pass ERC/DRC, but the design has **not yet been validated on hardware**. A prototype run is the next step. Do not order production quantities from these files yet.

- Schematic and layout are complete (KiCad 10), with schematic/PCB parity and no unconnected items.
- The final BOM / MPN review is still in progress.
- Mechanical fit of the 5.1 mm tall amplifier output inductors (L11/L12) must be checked on the prototype.
- The ESPHome configuration in this repository (`MiciMike.yaml`) targets an earlier hardware revision and **does not match** the current board.
- ESP32-P4 audio firmware (microphone processing) is under development.

## Hardware variants

One PCB, two assembly variants. They are defined as KiCad 10 design variants, so the BOM, position file and fabrication outputs can be generated per variant.

| Variant | Description | Radios |
|---|---|---|
| **Full** | ESP32-S3 + ESP32-P4 + ESP32-C6 | Wi-Fi 4 / BLE (S3), Wi-Fi 6 / BLE / 802.15.4 Thread & Zigbee (C6) |
| **No C6** | ESP32-S3 + ESP32-P4, the whole ESP32-C6 section not populated | Wi-Fi 4 / BLE (S3) |

In the **No C6** variant all 27 parts of the ESP32-C6 sheet are DNP (U8, Y2, AE2, its RF matching network, decoupling, FB2 and the C6 boot/reset parts). FB2 is the only feed of the C6 supply rail, so the whole C6 power domain is unpowered. The S3 GPIOs that connect to the C6 (reset, GPIO9/boot, UART) must not be used by the firmware in this variant.

Example exports with `kicad-cli`:

```
kicad-cli sch export bom --variant "No C6" -o bom_noC6.csv nest-mini-v2-drop-in-pcb.kicad_sch
kicad-cli pcb export pos --variant "No C6" --exclude-dnp -o pos_noC6.csv nest-mini-v2-drop-in-pcb.kicad_pcb
```

## Architecture

| Block | Part | Role |
|---|---|---|
| Main MCU | ESP32-S3R8 (8 MB PSRAM) + 16 MB W25Q128 flash | Wi-Fi/BLE, ESPHome, wake word, I²S master to the amplifier, I²C master, LEDs, mute detection, boot/reset and UART control of the P4 and C6 |
| Audio processor | ESP32-P4 + 16 MB W25Q128 flash | Microphone input and audio processing (noise suppression, AEC, AGC; firmware in development) |
| Thread / Zigbee (optional) | ESP32-C6FH8 (8 MB in-package flash) | 802.15.4 radio, e.g. OpenThread Border Router (ESP-IDF `ot_br`) |
| Amplifier | TAS5805M (TAS5805MPWPR) | Class-D amplifier with DSP, I²S audio, I²C control by the S3 |
| Microphones | 3x TDK InvenSense T3902 (MMICT390200012) | PDM MEMS microphones to the ESP32-P4 |
| Touch | MPR121 | Capacitive touch on the original touch surface, I²C with IRQ to the S3 |
| LEDs | 4x SK6805-EC20 + 2x SK6812D-EC3210R (side-emitting, board edge) | Addressable RGB, driven by the S3 through an SN74AHCT1G125 3.3 V to 5 V level shifter |

The ESP32-P4 replaces the XMOS XU316 used in earlier revisions.

### Inter-chip links

- **S3 → amplifier:** I²S (BCLK, LRCK, SDIN) and I²C control.
- **Amplifier → P4 (AEC reference):** the TAS5805M SDOUT goes to the ESP32-P4, which receives BCLK/LRCK from the same I²S bus, so the P4 gets the post-DSP playback signal as the echo-cancellation reference.
- **S3 ↔ P4:** I²S data line from the P4 to the S3 (I2S_DIN_SEC, processed microphone audio) and a second I²S clock pair (I2S2 BCLK/LRCLK), plus UART, P4_BOOT and P4_RST driven by the S3.
- **S3 ↔ C6:** UART plus C6 reset and GPIO9 (boot), driven by the S3, for firmware updates of the C6 from the S3.
- **I²C bus:** S3, TAS5805M and MPR121.

## Power

- **Input:** 14 V from the original Nest Mini power supply (14 V / 1.1 A), through the original flex cable (Hirose FH34SRJ-10S, 14 V on pins 7–10).
- **Protection:** PMEG4030ER Schottky diode in series (reverse polarity) and SMAJ15A TVS on the 14 V rail.
- **Rails:**
  - 14 V → TPS62130 → 5 V (LEDs, microphone LDO, LED level shifter)
  - 5 V → TPS62130 → 3.3 V, then separate filtered branches through ferrite beads for the S3, P4 and C6
  - 3.3 V → TLV62569 → ESP32-P4 core supply (ESP_VDD_HP)
  - 14 V → TAS5805M PVDD
  - 5 V → TLV73333 → microphone supply (switched off by the mute switch)
- **Bench supply / test pads:**

| Pad | Rail | Type | Powers |
|---|---|---|---|
| TP1 (+) / TP4 (GND) | +14 V, **max 15 V** | 3 mm THT pads (front) | the whole board, including the amplifier |
| TP2 | +5 V | 1 mm test pad (back) | everything except the amplifier (TAS5805M PVDD stays off) |
| TP3 | +3.3 V | 1 mm test pad (back) | the ESP32s, flash, touch controller; no LEDs, no microphones, no amplifier |

Use only one supply input at a time. When feeding +5 V or +3.3 V directly, the rail above it is not driven, and the regulator in front of it may be back-powered through its internal switch.

> ⚠️ There is no USB-C port on this revision. The board is powered through the original flex cable or the bench / test pads above.

## Audio

- TAS5805M in **mono PBTL** mode with pre-filter paralleling (OUT_A+ ∥ OUT_A− → L11 and OUT_B+ ∥ OUT_B− → L12, per TI TAS5805M PBTL wiring), output filter with 2x Coilcraft XAL5050-103 (10 µH) inductors.
- Original 4 Ω / 15 W speaker. The original firmware limits the amplifier to about 40 %. The firmware must set PBTL mode (`DAMP_PBTL`) and a gain / power limit that suits the speaker and the 14 V / 1.1 A supply.
- Speaker connection: TE 1775443-2 connector (J5) or the parallel solder pads TP8/TP9.

## Microphones and mute

- 3 PDM microphones, connected to the ESP32-P4 through an SN74LVC125A buffer.
- The original mute slide switch (flex cable pin 2) is read by the S3 and also acts **in hardware**: in the muted position the microphone LDO is switched off and the buffer outputs go high-impedance, so the microphones cannot be enabled from firmware.

## Programming

Each ESP has its own unpopulated 5-pin pogo / header footprint: GND, BOOT, RST, USB D−, USB D+.

| Header | Chip | USB |
|---|---|---|
| J1 | ESP32-S3 | native USB (USB Serial/JTAG) |
| J2 | ESP32-C6 | native USB (USB Serial/JTAG) |
| J3 | ESP32-P4 | USB 1.1 FS (GPIO24/25) |

After the first flash, the S3 can update the P4 and the C6 over UART, controlling their boot and reset lines.

## PCB

- 4 layers, 1.6 mm: F.Cu signal / In1 solid GND / In2 power planes / B.Cu signal.
- All vias 0.4 / 0.3 mm (24 thermal vias under the TAS5805M).
- Two Johanson 2450AT18A100E chip antennas (S3 and C6), each with its own keepout, LC matching network, RF netclass and GND via fence.
- GND stitching vias along the board edge.
- Custom DRC rules (`.kicad_dru`) allow the narrow RF track at the ESP32-S3 and ESP32-C6 antenna pins.
- Intentional DRC exclusions (microphone pads at the acoustic openings, touch pads with NPTH, I²S fan-out, programming footprint overlap) are documented with reasons in the project file.

## Hardware changes compared to rev 2

- XMOS XU316 replaced by ESP32-P4 (with its own flash and TLV62569 core supply).
- ESP32-C6 section added as an assembly option (Full / No C6 variants).
- USB-C input, FUSB302B PD controller, USB mux and the GPIO expander removed. Power comes from the original 14 V input, or from the 14 V / 5 V / 3.3 V bench and test pads.
- Programming moved to per-chip pogo footprints with USB.
- S3 controls the P4 and C6 boot/reset lines and has a UART to both.
- 14 V input protection added (series Schottky + TVS), plus bench supply pads TP1/TP4 (14 V) and test pads TP2 (5 V) / TP3 (3.3 V).
- Speaker solder pads TP8/TP9 added next to the speaker connector.
- TAS5805M changed to mono PBTL with 10 µH / XAL5050 output inductors.
- Microphone buffer and microphone LDO controlled by the hardware mute switch.
- TPS62130 regulators: DEF tied to GND, PG not used.
- Complete re-layout in KiCad 10, with RF keepouts, matching networks and via fencing for both antennas.

## Tools used

- 🛠️ KiCad 10
- 🧰 SnapEDA / LCSC for footprint sourcing

## References

### Home Assistant Voice Preview Edition resources (inspiration)
- https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/
  - https://voice-pe.home-assistant.io/resources/
    - https://support.nabucasa.com/hc/en-us/articles/26195279589277-Home-Assistant-Voice-Preview-Edition-PCB-design-files
      - https://raw.githubusercontent.com/NabuCasa/support/refs/heads/main/static/docs/voice/home_assistant_voice_pe_schematic_v1.0_241009.pdf

#### ESPHome firmware for Home Assistant Voice PE

- https://github.com/esphome/home-assistant-voice-pe
  - https://esphome.github.io/home-assistant-voice-pe/
- https://voice-pe.home-assistant.io/

### ESP32-P4 resources

- https://www.espressif.com/en/products/socs/esp32-p4
- https://documentation.espressif.com/esp32-p4_datasheet_en.html
- https://docs.espressif.com/projects/esp-idf/en/latest/esp32p4/

## License

This project is licensed under the [CERN Open Hardware License Version 2 - Strongly Reciprocal (CERN-OHL-S v2)](LICENCE).
Any modified version of this hardware must also be distributed under the same license.

## Development note

AI agents were used as assistants during the development of this hardware, for design review, verification and documentation. All design decisions and the final design files are the author's own.

☕ If you'd like to support this project, feel free to [buy me a coffee on Ko-fi](https://ko-fi.com/imike78)!
