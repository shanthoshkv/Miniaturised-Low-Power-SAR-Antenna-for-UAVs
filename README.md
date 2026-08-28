# Miniaturised Low-Power SAR Antenna for UAVs

Microstrip patch antenna design for a miniaturized, low-power Synthetic Aperture Radar (SAR) payload on a small UAV, done as an RVCE "Fundamentals of Avionics" course project (AS345AT, 2024-25).

## What it is

A single L-band (2 GHz) rectangular microstrip patch antenna, sized and analyzed by hand using standard transmission-line-model equations, then simulated in ANSYS HFSS (student license) to check the design against the theory. The goal was a patch small and light enough for a UAV payload while still resonating cleanly at 2 GHz with usable bandwidth and gain for SAR imaging.

## Why L-band, why a patch

L-band (roughly 1-2 GHz) penetrates vegetation and light precipitation better than higher SAR bands and is well suited to ocean-surface roughness and general all-weather imaging, which made it a reasonable target for a small demonstrator. A microstrip patch was chosen over other antenna types because it's low-profile (doesn't add aerodynamic drag), can be fabricated on standard PCB processes, and is light enough not to matter on a UAV payload budget.

## Design method

Standard transmission-line model for a rectangular patch:

**Patch width:**
$$W = \frac{v_0}{2f_r}\sqrt{\frac{2}{\varepsilon_r + 1}}$$

**Effective dielectric constant** (accounts for fringing fields partly in air, partly in substrate):
$$\varepsilon_{reff} = \frac{\varepsilon_r + 1}{2} + \frac{\varepsilon_r - 1}{2}\left[1 + 12\frac{h}{W}\right]^{-1/2}$$

**Length extension** (fringing fields make the patch look electrically longer than it is):
$$\Delta L = 0.412h\,\frac{(\varepsilon_{reff}+0.3)\left(\frac{W}{h}+0.264\right)}{(\varepsilon_{reff}-0.258)\left(\frac{W}{h}+0.8\right)}$$

**Physical length:**
$$L = \frac{v_0}{2f_r\sqrt{\varepsilon_{reff}}} - 2\Delta L$$

### Substrate

Compared ceramic, polymer and PTFE-composite substrate families and picked **RT/Duroid 6006** ($\varepsilon_r = 6.0$, $\tan\delta = 0.0019$ at 2 GHz) for its balance of dielectric constant, low loss, and standard PCB-compatible processing. Substrate thickness (h = 3.2 mm) was chosen from the usual bound

$$\frac{0.003\lambda_0}{\sqrt{\varepsilon_r}} \le h \le \frac{0.05\lambda_0}{\sqrt{\varepsilon_r}}$$

which keeps the design well under the surface-wave onset thickness for this substrate (~16.8 mm) while giving enough bandwidth to be usable.

### Final dimensions (theoretical)

| Parameter | Value |
|---|---|
| Operating frequency | 2.0 GHz |
| Patch length (L) | 27.0 mm |
| Patch width (W) | 40.09 mm |
| Substrate thickness (h) | 3.2 mm |
| Substrate | RT/Duroid 6006 |
| Effective dielectric constant | 5.29 |
| Theoretical resonant frequency | 1.945 GHz |
| Feed | Inset feed, 3.5 mm inset, 1.65 mm line width (50 Ω match) |

`Figure_1.png` has the same width/length calculation carried out for a few other candidate substrates (RO4003C, RT/Duroid 5880, FR-4, Taconic TLY-5) for comparison, RT/Duroid 6006 gives the smallest footprint of the set at this εr while staying in a practical thickness range.

## HFSS simulation results

The `.aedt` project simulates the design as a two-port (two-element) layout, so all four S-parameters are reported.

**S11 (input return loss)** — resonance lands right at 2.0 GHz as designed, with a return loss of about **-9.8 dB** at the dip:

![S11 return loss](Report/images/s11.png)

**S22** mirrors S11 closely, as expected for a symmetric two-element layout:

![S22 return loss](Report/images/s22.png)

**S21 / S12 (isolation between the two ports)** stays well below -30 dB across the 2 GHz region (down to about -58 dB near 2.26 GHz), so the two elements are well isolated from each other:

![S21 isolation](Report/images/s21.png)
![S12 isolation](Report/images/s12.png)

## Where the report and the simulation disagree

Worth being upfront about, since the write-up in `Report/main.tex` doesn't fully match the `.aedt` results:

- The report's "expected results" section states a target of **< -20 dB return loss**. The actual HFSS sweep bottoms out at **~-9.8 dB** at 2.0 GHz, a real resonance at the right frequency, but not the depth of match the report implies.
- The written derivation for the physical patch length shows visible "correct to match design" steps (the effective length comes out to 32.6 mm from the formula, gets knocked down to 29.8 mm by the fringing correction, and then the report rounds it to 27.0 mm to align with a stated final value) rather than a single clean pass through the equations. The final dimensions table is consistent internally, it's just worth knowing the length wasn't derived in one straight shot.
- The theory in `main.tex` is written for a single patch element, but the `.aedt` project and the S-parameter results are from a two-port structure. The S11/S22 plots above are what the model actually produced.

None of this invalidates the design (2 GHz resonance is real and confirmed in simulation), but the gain, bandwidth and -20 dB target figures quoted in the abstract and results table are the hand-calculated targets, not confirmed by the S-parameter sweep in this repo.

## Repo layout

- `SAR MINI.aedt` — the ANSYS HFSS (student) project used for the S-parameter simulation
- `Report/main.tex` — full project report (LaTeX) with the derivation, literature review, thermal and power-budget analysis, and references
- `Report/images/` — figures used in the report (S-parameters, RVCE logo)
- `Avioncs Report.pdf`, `Avionics Presentation.pdf` — compiled report and presentation deck submitted for the course
- `Figure_1.png`, `s11.png`, `s12.png`, `s21.png`, `s22.png` (repo root) — same figures as `Report/images/`, kept at root as well from how the report was assembled

## Building the report

```
cd Report
pdflatex main.tex
```

Needs a standard LaTeX distribution with `amsmath`, `tikz`, `pgfplots`, `booktabs`, `natbib` and `hyperref`.

## Limitations

- No physical prototype was built or measured, this is a theoretical/simulated design only (HFSS student license, hand calculations).
- No radiation pattern, gain, or bandwidth plots are included in this repo, only the four S-parameters shown above. The gain (6-8 dBi) and bandwidth (~3.3%) figures in the report are analytical estimates, not simulation output.
- The report's single-element theory and the two-port simulation aren't the same structure (see above), so treat the equations as the design methodology and the S-parameter plots as what was actually simulated.

## References

- Balanis, C. A. (2016). *Antenna Theory: Analysis and Design*, 4th Ed. Wiley.
- Garg, R., Bhartia, P., Bahl, I., Ittipiboon, A. (2001). *Microstrip Antenna Design Handbook*. Artech House.
- James, J. R., Hall, P. S. (1989). *Handbook of Microstrip Antennas*. Peter Peregrinus.
- Curlander, J. C., McDonough, R. N. (1991). *Synthetic Aperture Radar: Systems and Signal Processing*. Wiley.
- Cumming, I. G., Wong, F. H. (2005). *Digital Processing of Synthetic Aperture Radar Data*. Artech House.

Full report (`Report/main.tex`) has the complete reference list.
