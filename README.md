# nest-mini-drop-in-pcb
Drop-in PCB replacement for the Google Nest Mini with XMOS integration. Inspired by Onju Voice and Home Assistant Voice PE hardware.
# Nest Mini Drop-In PCB Replacement

This project is a custom drop-in replacement PCB for the Google Nest Mini (2nd Gen), designed to integrate an ESP32-S3 and XMOS XU316 for local voice processing. It's inspired by the Onju Voice project and the Home Assistant Voice Preview Edition reference hardware.

## Current status

- ✅ Schematic completed
- ✅ Component placement done
- 🕓 Routing in progress
- 🚧 Ground pour, shielding strategy, and EMI considerations pending

## Request for collaboration

If you have experience with PCB routing, ground pouring, or noise-sensitive digital+analog layouts, **your help is highly appreciated**! Please feel free to open issues, submit suggestions, or fork the repo.

## Tools used

- 🛠️ KiCad 7
- 🧰 SnapEDA / LCSC for footprint sourcing
- 🖼️ FreeCAD + KiCad StepUp for mechanical validation

## Known hardware specs

- 4-layer PCB
- ESP32-S3R8 bare chip
- XMOS XU316 (audio processing)
- Dual SPI flash
- MAX98357 for speaker output
- 2x MEMS microphones (MSM261DHP)
- SK6812 LEDs (side-emitting)
- Custom USB-C and 14V power input

---

> ⚠️ Flashing via USB-C requires disconnecting the main 14V power input. See silkscreen note on PCB for details.
