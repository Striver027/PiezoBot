# Documentation — PiezoBot

Supporting documentation for building, operating and reproducing the PiezoBot robot.

Everything in this folder is released under the
**Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)** licence.
See the repository root [`LICENSE`](../LICENSE) for the full text.

---

## Contents

| File | Description | Status |
|---|---|---|
| [`BOM.csv`](BOM.csv) | Editable bill of materials, using the same columns as the article | included |
| `assembly.md` + `assembly-figures/` | Step-by-step assembly notes with labelled photographs | to be added |
| `wiring.md` | Wiring and connector pin-out between the stacked boards | to be added |
| `operation.md` | Operating notes: start-up, changing the driving frequency, turning, safety | to be added |
| `measurements/` | Raw records of the speed measurement reported in the article | to be added |
| `photos/` | Photographs of the assembled robot and of individual boards | to be added |

The build and operating instructions are described in full in the accompanying
HardwareX article; the files above are intended to complement the article rather than
replace it.

---

## The bill of materials — `BOM.csv`

The CSV uses exactly the columns of the *Bill of materials summary* in the article:

```
Designator, Component, Number of units, Cost per unit - currency,
Total cost - currency, Source of materials, Material type
```

### What still has to be filled in

- **Cost per unit** and **Total cost** — not yet filled in.
- **Source of materials** — add a purchase link or supplier for each part.
- **Material type** — choose one of the journal's options:
  *Metal, Semiconductor, Ceramic, Polymer, Biomaterial, Organic, Inorganic, Composite,
  Nanomaterial, Non-specific, Other.*

  Suggested values for the current parts (please confirm):

  | Part | Suggested material type |
  |---|---|
  | NdFeB magnet (N52) | Metal |
  | Piezoelectric stack | Ceramic |
  | Shell | Polymer |
  | LCD retaining ring | Polymer |
  | Base (CNC machined aluminium) | Metal |
  | Brass cap screw | Metal |
  | Brass ball plunger | Metal |
  | FPC | Composite |
  | Instant adhesive (401) | Polymer |
  | Magnetic pole indicator card | Other |

### What is missing from the table

The table currently lists the parts **other than the PCBs**. Before submission the
following should be added, because the journal asks for *all* components associated with
a cost:

- the fabrication cost of the seven boards (power, controller, function, PZT, LCD, DAP, BAT);
- any purchased electronic components that are not already covered by the board
  fabrication cost (microcontroller, boost converter, power operational amplifier,
  battery, display, wireless module, IMU, connectors, fasteners).

Any bill of materials of this kind can also be uploaded as an editable spreadsheet, as
noted in the article's *Bill of materials* section.
