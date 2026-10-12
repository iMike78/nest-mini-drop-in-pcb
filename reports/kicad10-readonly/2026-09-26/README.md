# KiCad 10 read-only ERC/DRC baseline

Generated with KiCad CLI 10.0.6 on 2026-09-26. No repair, zone refill, board save, or design-file write was requested.

## ERC

- Source: `nest-mini-v2-drop-in-pcb.kicad_sch`
- Total violations: 225
- Errors: 32
- Warnings: 193
- Excluded/ignored check definitions present: 4

Most frequent categories:

| Type | Count |
| --- | ---: |
| Missing symbol library | 103 |
| Missing footprint library link | 38 |
| Power input not driven | 25 |
| Unconnected wire endpoint | 21 |
| Pin-to-pin rule conflict | 16 |
| Isolated pin label | 7 |
| Multiple net names | 5 |

## DRC

- Source: `nest-mini-v2-drop-in-pcb.kicad_pcb`
- Board-rule violations: 237
- Unconnected items: 64
- Schematic parity findings: 12
- Combined findings: 313
- Errors: 275
- Warnings: 38
- Excluded/ignored check definitions present: 13

Most frequent categories:

| Type | Count |
| --- | ---: |
| Clearance | 158 |
| Unconnected items | 64 |
| Pad stack | 24 |
| Malformed courtyard | 20 |
| Hole clearance | 12 |
| Schematic/PCB net conflict | 12 |
| Copper-to-edge clearance | 6 |
| Shorting items | 6 |
| Solder-mask bridge | 6 |

## Notes

- DRC included schematic parity and all track errors.
- All severities and excluded findings were included in the raw reports.
- Zones were not refilled and the board was not saved.
- KiCad could not find the `Agency FB` font and used `Verdana Bold` while checking.
- Several ERC findings are caused by missing local symbol and footprint library registrations. They should be separated from electrical design findings during triage.

The `.rpt` files are human-readable KiCad reports. The `.json` files contain the same run in machine-readable form for later agent analysis.
