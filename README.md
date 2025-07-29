# MiciMike Nest Mini drop-in PCB

A drop-in PCB replacement for the [Google Nest Mini (WiFi voice assistant / smart speaker)](https://en.wikipedia.org/wiki/Google_Nest_(smart_speakers)), based on ESP32 and XMOS microcontrollers.

This is an open-source hardware project, taking inspiration from both [Onju Voice](https://github.com/justLV/onju-voice) and [Home Assistant Voice Preview Edition](https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/) PCB designs.

# Project scope

The goal of this project and repository (which is similar to the [Onju Voice](https://github.com/justLV/onju-voice) but under a fully open-source hardware license) is to design a drop-in replacement PCB (Printed Circuit Board) with hardware schematics that anyone can make/build or order from a one-stop PCB manufacturer as a custom drop-in replacement PCB for the Google Nest Mini (2nd Gen).

This is primarly targeting people looking to convert/repurpose their old Google Nest Mini smart speakers into open-source hardware for [Voice Control of Home Assistant](https://www.home-assistant.io/voice_control/) and/or media player speaker output for [Music Assistant](https://www.music-assistant.io), (the hardware can however probably also be used with other applications as well with other firmware as it is based on the popular Espressif ESP32 platform).

The hardware design will (similar to [Home Assistant Voice Preview Edition](https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/)) integrate an ESP32-S3 SoC for WiFi, BLE, and [onboard wake-word detection](https://www.home-assistant.io/voice_control/about_wake_word/) (using no-code [ESPHome firmware](https://esphome.io/)) + an XMOS xCORE XU316 chip for advanced audio processing (with custom firmware for microphone cleanup offloading for better voice recognition capabilities by using using locally running algorithms for Noise Suppression, Acoustic Echo Cancellation, Interference Cancellation, and Automatic Gain Control).

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

- ✅ Schematic completed
- ✅ Component placement done
- 🕓 Routing in progress
- 🚧 Ground pour, shielding strategy, and EMI considerations pending



## Tools used

- 🛠️ KiCad 9
- 🧰 SnapEDA / LCSC for footprint sourcing

## Known hardware specifications

- 4-layer PCB
- ESP32-S3R8 bare chip (ESP32-S3 for WiFi, BLE, and onboard wake-word detection)
- XMOS XU316-1024-QF60B-C32 (XMOS XU316 xCORE DSP audio processing)
- Dual SPI flash
- Dual I²S buses (to allow I2S interfaces at the same time, i.e. simultaneous audio output and audio input)
- MAX98357 for speaker output (I2S Class-D Mono Audio Amplifyer)
- 2x MEMS microphones (dual MSM261DHP with 68mm inter-mic spacing)
- 4x SK6812 RGB LEDs
- Custom USB-C and 14V power input

---

> ⚠️ Flashing via USB-C requires disconnecting the main 14V power input. See silkscreen note on PCB for details.

## References

### Home Assistant Voice Preview Edition resources including PCB design files
- https://www.home-assistant.io/blog/2024/12/19/voice-preview-edition-the-era-of-open-voice/
  - https://voice-pe.home-assistant.io/resources/
    - https://support.nabucasa.com/hc/en-us/articles/26195279589277-Home-Assistant-Voice-Preview-Edition-PCB-design-files
      - https://raw.githubusercontent.com/NabuCasa/support/refs/heads/main/static/docs/voice/home_assistant_voice_pe_schematic_v1.0_241009.pdf
     
#### ESPHome firmware for Home Assistant Voice PE (which also use the same ESP32-S3 + XMOS XU316 combination):

- https://github.com/esphome/home-assistant-voice-pe
  - https://esphome.github.io/home-assistant-voice-pe/
- https://voice-pe.home-assistant.io/

### XMOS xCORE DSP (XU316-1024-QF60B-C32) MCU IC chip

- https://www.xmos.com/download/XU316-1024-QF60B-xcore.ai-Datasheet(3).pdf
- https://www.xmos.com/software-tools/
  - https://www.xmos.com/develop/xcore-voice
  - https://www.xmos.com/usb-multichannel-audio/
  - https://www.xmos.com/xcore-ai
 
#### XMOS firmware from the ESPHome prokect for the Home Assistant Voice Preview Edition hardware:

- https://github.com/esphome/voice-kit-xmos-firmware
  - https://github.com/esphome/xmos_fwk_rtos
  - https://github.com/esphome/xmos_fwk_io

## License

This project is licensed under the [CERN Open Hardware License Version 2 - Strongly Reciprocal (CERN-OHL-S v2)]
Any modified version of this hardware must also be distributed under the same license.

☕ If you’d like to support this project, feel free to [buy me a coffee on Ko-fi](https://ko-fi.com/yourname)!

