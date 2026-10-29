# Labi-Sat-payload

KiCad 10 design for a sample payload board for the Labi Sat PocketQube platform. The
schematic includes two RP2040 MCU boards and the `PQ_bus` interface.

## Schematic notes

- GP18 is available for use, but is also internally connected to an LED.
- Unassigned GPIOs can be used for any function.
- If the HDUART interface is used, do not connect anything else to GPIO0 / GPIO4.
- Net names may be changed as needed, but **do not connect**
  `REG_BUS_PROTECTED_1` and `REG_BUS_PROTECTED_2` together.

## PQ_bus pinout

2×8, 2.54 mm card-edge connector (`pq:PinHeader_2x8_2.54_PCB_edge`).

| Pin | Signal              | Pin | Signal              |
|-----|---------------------|-----|---------------------|
| 1   | GND                 | 2   | DNC                 |
| 3   | DNC                 | 4   | HDUART_2            |
| 5   | DNC                 | 6   | CAN2_H              |
| 7   | REG_BUS_PROTECTED_1 | 8   | CAN2_L              |
| 9   | CAN1_L              | 10  | REG_BUS_PROTECTED_2 |
| 11  | CAN1_H              | 12  | DNC                 |
| 13  | HDUART_1            | 14  | DNC                 |
| 15  | DNC                 | 16  | GND                 |

Pins marked DNC (do not connect) are reserved for future use and must be left
unconnected on the payload board. The board is powered from the bus, so the
supply pins of the `PQ_bus` symbol are power outputs and no `PWR_FLAG` is needed.

## Design files

- `payoad_board.kicad_sch` — schematic
- `payoad_board.kicad_pcb` — PCB layout
- `payoad_board.kicad_pro` — KiCad project settings
- `pq.kicad_sym` — project symbol library (`MCU_1`, `PQ_bus`)
- `pq.pretty/` — project footprint library
- `3dmodels/` — 3D models used by the footprints
- `sym-lib-table`, `fp-lib-table` — project library tables (paths relative to `${KIPRJMOD}`)

Open `payoad_board.kicad_pro` in KiCad to view the project. All libraries and 3D models
are part of the repository, so no extra library setup is needed.
