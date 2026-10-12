
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

[MiciMike Nest Mini](https://github.com/iMike78/nest-mini-drop-in-pcb) is a drop-in PCB replacement for the ["Google Nest Mini" (Google's second-generation smart speaker with a barrel connector charging port)](https://en.wikipedia.org/wiki/Google_Nest_(smart_speakers)), built around ESP32-S3, ESP32-C6, and ESP32-P4 microcontrollers for running open-source firmware.

Tip! If you are instead looking for a similar drop-in PCB replacement for the "Google Home Mini" (Google's first-generation smart speaker hardware with a Micro-USB charging port) then check out the sister-project at https://github.com/iMike78/home-mini-v1-drop-in-pcb

Both of these are fully open-source hardware projects, taking some concept inspiration from the [Onju Voice](https://github.com/justLV/onju-voice) however aiming to follow [Open Home Foundation's open voice assistants standard  with Home Assistant Voice Preview Edition as reference](https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/) for PCB designs and specifications.

# Project scope

The goal of this project and repository (which is similar to the [Onju Voice](https://github.com/justLV/onju-voice) but under a fully open-source hardware license) is to design a custom drop-in replacement PCB (Printed Circuit Board) for the Google Nest Mini (2nd Gen).

This is primarly targeting people looking to convert/repurpose their old Google Nest Mini smart speakers into open-source hardware for [Voice Control of Home Assistant](https://www.home-assistant.io/voice_control/) and/or media player speaker output for [Music Assistant](https://www.music-assistant.io), (the hardware can however probably also be used with other applications as well with other firmware as it is based on the popular Espressif ESP32 platform).

The current architecture uses an ESP32-S3 for Wi-Fi, Bluetooth LE, and [onboard wake-word detection](https://www.home-assistant.io/voice_control/about_wake_word/), with an ESP32-P4 as the high-performance audio and signal-processing controller. The ESP32-P4 replaces the previously planned XMOS XU316 and is intended to handle the microphone/audio pipeline and future local processing such as noise suppression, acoustic echo cancellation, interference cancellation, and automatic gain control. Firmware for this revised architecture is still under development.

Two hardware variants are planned. The full version includes an ESP32-C6 for Wi-Fi 6, Bluetooth LE, and 802.15.4, enabling OpenThread Border Router (OTBR) functionality. A second version omits the ESP32-C6 for installations that do not require OTBR/Thread border-router support.

Functionality-wise it is made to mostly hardware comatible with the [Home Assistant Voice Preview Edition (a.k.a. Home Assistant Voice PE](https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/) reference design (which has been released as open-source hardware design from Open Home Foundation in coolaboration with Nabu Casa). The main difference will be due to constraints defined by the Google Nest Mini enclosure and comonents, (i.e. the nest-mini-drop-in-pcb project hardware design will be limited by the same type of physical capacity inputs as the original hardware from Google).

As such the scope of this project/repository is not to develop new features/functions for the ESPHome firmware, so if you want that then you instead need to turn to the firmware development of the Home Assistant Voice Preview Edition as well as to the upstream ESPHome mainline code:

- https://github.com/esphome/home-assistant-voice-pe
  - https://github.com/esphome/esphome
      - https://github.com/esphome/feature-requests

## Request for collaboration

If you have some experience with PCB layout design, (and epecially with PCB routing, ground pouring, or noise-sensitive digital+analog layouts), **your help is highly appreciated**! Please feel free to open a new issue, submit suggestions/requests, and add input/feedback to existing issues, or fork this repository.

For more information about the concept/idea see and contribute to related discussion also see this Home Assistant community forum thread:

- https://community.home-assistant.io/t/any-news-on-alternative-to-onju-voice-pcb-repacement-design-for-google-nest-home-mini-speakers-with-added-xmos-chip-to-match-official-home-assistant-voice-preview-edition-reference-hardware/860001/

### Current status

> [!CAUTION]
> This project is under active development and is **not ready for fabrication or general use**. I do not recommend using the current files to manufacture a PCB.

The hardware has undergone a major redesign across every hierarchical schematic sheet and the PCB. The optional ESP32-C6 section has been integrated for the OTBR-capable variant, and the former XMOS audio-processing section has been replaced by an ESP32-P4-based design. Power, audio, LED, ESP32-S3, ESP32-C6, ESP32-P4, and PCB placement/routing data have all changed.

The design is still incomplete: some connections remain unrouted, the schematic and PCB require further consistency review, and the ESP32-P4 audio firmware and end-to-end signal path have not yet been validated on hardware.

The current ESPHome configuration also targets an earlier hardware revision and does not match the present schematic. It should not be treated as working firmware for the current board design.

Several hardware areas still require review before another prototype revision is considered, including the ESP32-P4 power and boot configuration, microphone and audio routing, mute detection, ESP32-C6 integration, power sequencing, signal integrity, and remaining PCB routing and clearance findings.

Development and documentation updates have been slower recently due to limited availability and work on the related Home Mini project. The README and design files will be updated as the review and redesign progress.

## Tools used

- 🛠️ KiCad 10
- 🧰 SnapEDA / LCSC for footprint sourcing

## Known hardware specifications

- 4-layer PCB
- ESP32-S3R8 bare chip (Wi-Fi, Bluetooth LE, and onboard wake-word detection)
- Two planned variants:
  - OTBR variant with an ESP32-C6FH8 bare chip (Wi-Fi 6, Bluetooth LE, and 802.15.4 radio for Thread/Zigbee connectivity; 8 MB in-package flash)
  - non-OTBR variant without the ESP32-C6
- ESP32-P4 bare chip (high-performance RISC-V application/audio processor; no integrated radio)
- 16 MB external SPI flash for the ESP32-S3
- 16 MB external SPI flash for the ESP32-P4
- Dual I²S buses (simultaneous audio input and output)
- TAS5805M (TAS5805MPWPR) stereo Class-D amplifier with integrated DSP (I2S audio, I2C control), configured for mono BTL speaker output
- 3x TDK MMICT390200012 MEMS microphones
- 6x addressable RGB LEDs: 4x SK6805-EC20 and 2x SK6812D-EC3210R
- USB-C and 14 V power inputs (do not connect at the same time)
- MPR121 capacitive touch controller (used for touch input instead of ESP32-S3 native touch sensing)

---

> ⚠️ Flashing via USB-C requires disconnecting the main 14V power input. See silkscreen note on PCB for details.

## References

### Home Assistant Voice Preview Edition resources including PCB design files
- https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/
  - https://voice-pe.home-assistant.io/resources/
    - https://support.nabucasa.com/hc/en-us/articles/26195279589277-Home-Assistant-Voice-Preview-Edition-PCB-design-files
      - https://raw.githubusercontent.com/NabuCasa/support/refs/heads/main/static/docs/voice/home_assistant_voice_pe_schematic_v1.0_241009.pdf

#### ESPHome firmware for Home Assistant Voice PE:

- https://github.com/esphome/home-assistant-voice-pe
  - https://esphome.github.io/home-assistant-voice-pe/
- https://voice-pe.home-assistant.io/

### ESP32-P4 resources

- https://www.espressif.com/en/products/socs/esp32-p4
- https://documentation.espressif.com/esp32-p4_datasheet_en.html
- https://docs.espressif.com/projects/esp-idf/en/latest/esp32p4/

## License

This project is licensed under the [CERN Open Hardware License Version 2 - Strongly Reciprocal (CERN-OHL-S v2)]
Any modified version of this hardware must also be distributed under the same license.

☕ If you’d like to support this project, feel free to [buy me a coffee on Ko-fi](https://ko-fi.com/imike78)!


