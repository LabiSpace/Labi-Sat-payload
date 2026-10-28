# Labi-Sat-payload

KiCad 10 design for a sample payload board for the Labi Sat PocketQube platform. The
schematic includes an RP2040 MCU board and an `NMHH-1_bus` interface.

## Schematic notes

- GP18 is available for use, but is also internally connected to an LED.
- Unassigned GPIOs can be used for any function.
- Net names may be changed as needed, but **do not connect**
  `REG_BUS_PROTECTED_1` and `REG_BUS_PROTECTED_2` together.

## Design files

- `payoad_board.kicad_sch` — schematic
- `payoad_board.kicad_pcb` — PCB layout
- `payoad_board.kicad_pro` — KiCad project settings

Open `payoad_board.kicad_pro` in KiCad to view the project.
