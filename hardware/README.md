# Hardware — PiezoBot

Editable PCB design files for the PiezoBot robot
(a desktop-scale stick–slip piezoelectric robot for validating swarm-intelligence
algorithms that require fine relative positioning).

All files in this folder are released under the
**Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** licence.
See the repository root [`LICENSE`](../LICENSE) for the full text.

---

## File inventory

### Stack order (bottom → top)

| # | Board |
|---|---|
| 1 (bottom) | PZT board |
| 2 | Power board |
| 3 | Controller board |
| 4 (top) | Function board |

The **LCD board** sits above the stack and is the topmost part of the robot; its FPC
connects to the controller board. The **DAP board** and the **BAT board** are not part of the
stack: the DAPLink-end adapter in the DAP board panel is used only to help flash the firmware,
and the BAT board is the battery adapter that powers the robot.

### Project files (open these first)

| File | Format | Purpose |
|---|---|---|
| `PiezoBot V0.3.PrjPcb` | Altium project | **Master project** — open this in Altium Designer to browse every schematic and PCB layout below |
| `PiezoBot V0.3.OutJob` | Altium output job | Fabrication and documentation output settings for the project |

Altium also keeps local working files in this folder (`History/`, `__Previews/`,
`*.PrjPcbStructure`); they are generated automatically and are not part of the released design
files.

### PZT board (piezoelectric stack carrier and wiring)

Stack position: bottom (1st from the bottom).

| File | Format | Purpose |
|---|---|---|
| `PZT Board.SchDoc` | Altium schematic | Rev. V0.3 |
| `PZT Board.PcbDoc` | Altium PCB | PCB layout |
| `PZT Board.pdf` | PDF | Schematic, for viewing without Altium |
| `PZT Board.zip` | Gerber + drill | Ready for PCB fabrication |

### Power board (boost converter + power operational amplifier)

Stack position: 2nd from the bottom.

| File | Format | Purpose |
|---|---|---|
| `Power Board V0.3.SchDoc` | Altium schematic | Rev. V0.3 |
| `Power Board V0.3.PcbDoc` | Altium PCB | PCB layout |
| `Power Board V0.3.pdf` | PDF | Schematic, for viewing without Altium |
| `Power Board V0.3.zip` | Gerber + drill | Ready for PCB fabrication |

### Controller board (STM32G431 main controller)

Stack position: 3rd from the bottom; the FPC from the LCD board connects here.

| File | Format | Purpose |
|---|---|---|
| `Controller Board V0.3.SchDoc` | Altium schematic | Rev. V0.3 |
| `Controller Board V0.3.PcbDoc` | Altium PCB | PCB layout |
| `Controller Board V0.3.pdf` | PDF | Schematic, for viewing without Altium |
| `Controller Board V0.3.zip` | Gerber + drill | Ready for PCB fabrication |

### Function board (IMU + 433 MHz wireless module)

Stack position: top (4th from the bottom).

| File | Format | Purpose |
|---|---|---|
| `Function Board V0.3.SchDoc` | Altium schematic | Rev. V0.3 |
| `Function Board V0.3.PcbDoc` | Altium PCB | PCB layout |
| `Function Board V0.3.pdf` | PDF | Schematic, for viewing without Altium |
| `Function Board V0.3.zip` | Gerber + drill | Ready for PCB fabrication |

### LCD board (display base board, topmost part of the robot)

The 0.99-inch display is taped onto this board, and the display ribbon cable is soldered to
it. The board acts as the display's base board: it converts the display signals into an FPC
interface, which connects to the controller board. The LCD board sits above the stack and
is the topmost part of the robot (Rev. V0.1).

| File | Format | Purpose |
|---|---|---|
| `LCD Board.SchDoc` | Altium schematic | Rev. V0.1 |
| `LCD Board.PcbDoc` | Altium PCB | PCB layout |
| `LCD Board.pdf` | PDF | Schematic, for viewing without Altium |
| `LCD Board.zip` | Gerber + drill | Ready for PCB fabrication |

### DAP board (DAPLink adapter, panelized)

A simple adapter board for interfacing different types of connectors: connectors of
different families are mated through this board. It adapts a PowerLink 2.54 mm interface
to a 0.8 mm BTB interface.

The layout is **panelized** and has the same structure and layout as the BAT board below: the
larger board of the panel serves as the link-end adapter and connects to a DAPLink programmer,
while the two smaller boards are used for programming and for the two batteries.

| File | Format | Purpose |
|---|---|---|
| `DAP Board.SchDoc` | Altium schematic | Schematic |
| `DAP Board.PcbDoc` | Altium PCB | Panelized layout |
| `DAP Board.pdf` | PDF | Schematic, for viewing without Altium |
| `DAP Board.zip` | Gerber + drill | Gerber/drill output of the panelized layout |

### BAT board (battery adapter, panelized)

Battery adapter board. It has exactly the same structure and layout as the DAP board, but the
lead connections inside the board are thickened, so the **DAP board and the BAT board are not
interchangeable**: the two differ only in their robot ends (the two smaller boards), and the
link end of the BAT panel can still be connected to a DAPLink programmer.

| File | Format | Purpose |
|---|---|---|
| `BAT Board.SchDoc` | Altium schematic | Schematic |
| `BAT Board.PcbDoc` | Altium PCB | Panelized layout |
| `BAT Board.pdf` | PDF | Schematic, for viewing without Altium |
| `BAT Board.zip` | Gerber + drill | Gerber/drill output of the panelized layout |

---

## PCB fabrication parameters

| Board | Layers | Board thickness |
|---|---|---|
| PZT board | 2 | 1.0 mm |
| Power board | 2 | 1.6 mm |
| Controller board | 4 | 1.6 mm |
| Function board | 2 | 1.2 mm |
| LCD board | 2 | 1.2 mm |
| DAP board | 2 | 1.6 mm |
| BAT board | 2 | 1.6 mm |

All boards are two-layer except the controller board, which is a four-layer board with
the stack-up top / mid-layer 1 / mid-layer 2 / bottom.

Copper weight follows the manufacturer's standard process (JLCPCB): **1 oz on the outer
layers and 0.5 oz on the inner layers** — the inner-layer value applies to the four-layer
controller board.

Each `.zip` archive contains the Gerber and drill files for the corresponding board.

---

## How to open these files

- **To edit** the electronics: **Altium Designer** (the `.PrjPcb` project opens all
  schematics and layouts together). A free **Altium 365 Viewer** can also display them in
  a browser.
- **To view without Altium**: use the `.pdf` files (schematics).
- **To fabricate**: send the contents of the corresponding `.zip` (Gerber + drill) to any PCB manufacturer.
