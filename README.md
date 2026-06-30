# NMOS DC Characterization (180nm) — Cadence Virtuoso

DC characterization of a single NMOS transistor (W = 2µm, L = 180nm) in a 180nm CMOS
process, performed in Cadence Virtuoso (Spectre) Schematic Editor.

## Test Bench
- Transistor: `nmos1`, W = 2µm, L = 180nm, m = 1
- `V1`: drain-to-ground source, `vdc = Vds`
- `Vgs`: gate-to-ground source, `vdc = vgs`
- Source/bulk grounded

## Simulation Setup
- Default bias point: `Vgs = 0.9V`, `Vds = 0.9V`
- Primary DC sweep: `Vds` from 0V to 2V
- Parametric (outer) sweep: `Vgs` from 0V to 2V, step = 0.5V

This produces the classic family of I_D–V_DS output characteristic curves for
Vgs = 0, 0.5, 1.0, 1.5, 2.0 V.

## Contents
- `report.tex` — LaTeX source for the full characterization report
- `report.pdf` — compiled report (cut-off / triode / saturation analysis)
- `figures/schematic.png` — test bench schematic from Virtuoso
- `figures/id_vds.png` — simulated I_D vs V_DS sweep family

## Building the report
```bash
pdflatex report.tex
pdflatex report.tex   # second pass for TOC
```

## Results Summary
| Vgs (V) | Region              | I_D @ Vds = 2V |
|---------|---------------------|----------------|
| 0.0     | Cut-off             | ~0 µA          |
| 0.5     | Near/sub-threshold  | ~10 µA         |
| 1.0     | Saturation          | ~0.38 mA       |
| 1.5     | Saturation          | ~0.90 mA       |
| 2.0     | Saturation          | ~1.41 mA       |
