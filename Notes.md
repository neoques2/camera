# Notes from Conversation

## Hardware Ideas
1. **Build #1: LED-Strobed Multispectral Camera** - use discrete LEDs or LED engines to sequentially illuminate and capture with a mono camera. Requires strobe controller, diffuser, calibration of each LED.
2. **Build #2: Linear Variable Filter (LVF) Push-broom** - continuous spectrum captured via scanning LVF in front of the camera. Needs linear stage, careful alignment.
3. **Build #3: Liquid Crystal Tunable Filter (LCTF)** - electronically selects band, slower switching. Works without moving parts. Requires dedicated controller.
4. **Build #4: Acousto-Optic Tunable Filter (AOTF)** - fast microsecond tuning with narrow bands. Needs RF driver and bright broadband source (e.g. supercontinuum).
5. **Build #5: SWIR Extension** - use a SWIR sensor (e.g., Sony IMX990) to extend coverage to 400-1700 nm. Pair with above filtering approaches.
6. **Build #6: MEMS Fabry-Pérot (FPI) System** - compact tunable filter using MEMS-actuated mirrors for 5–20 nm bands with millisecond switching.

## Potential Markets / Use Cases
1. Food & agriculture QA/QC
2. Precision agriculture & agronomy
3. Recycling & waste sorting
4. Mining & geological exploration
5. Environmental monitoring & water quality
6. Oil & gas leak detection
7. Art conservation & cultural heritage
8. Biomedical research & dermatology
9. Defense, surveillance & satellite imagery
10. Forensics & search applications
11. Medical wound care and tissue perfusion imaging

## Medical Device Landscape
- Devices like HyperMed HyperView, Kent SnapshotNIR, Modulim Ox-Imager, ViOptix Intra.Ox, Moor Instruments LDI, Diaspective Vision TIVITA.
- FDA clearances and CPT reimbursement codes exist (e.g., 0061U, 0640T-0642T).
- Opportunities around calibration software, analytics, and reimbursement toolkits.

HyperView and SnapshotNIR rely on LED illumination for portable tissue oxygenation mapping, while Ox-Imager and TIVITA offer higher-end cart-based systems focused on surgical use.
## Summary
The hardware approaches can be grouped into two categories: illumination-based and filter-based techniques. LED strobes provide a simple sequential illumination strategy, while LVF, LCTF, and AOTF methods vary the wavelength with optical elements. A SWIR sensor can extend these methods into the infrared.

Potential markets span industrial, scientific, and medical fields. Food inspection, recycling, environmental monitoring, art restoration, and defense each benefit from spectral imaging. Medical oximetry leverages existing FDA-cleared devices and reimbursement pathways.

Existing medical imaging systems like HyperView and SnapshotNIR demonstrate clinical interest in tissue oxygenation monitoring. Future products should consider calibration software and regulatory documentation to compete.

## Color Filter Array Manufacturing
- CFA layers are patterned on the wafer using photolithography. Each color resist is spin coated, exposed with a photomask, developed, and cured in sequence.
- Microlenses are then formed by reflowing a transparent resist, improving light collection.
- Pigmented vs. dyed resists affect thermal stability and UV process compatibility. Some sensors use dielectric Fabry-Pérot stacks instead of organic resists.
- Emerging research explores metasurface color routers for sharper spectral separation.
- Crosstalk reduction relies on deep trench isolation and complex microlens stacks precisely aligned to the pixels.

## Tunable Light Sources
- Discrete LEDs or multi-channel LED engines provide quasi-monochromatic illumination with FWHM typically 15–50 nm.
- Laser diodes and external-cavity lasers offer sub-nanometer bandwidth but may need speckle reduction.
- Supercontinuum sources paired with an AOTF enable electronically selectable bands across 400–2000 nm.
- Optical parametric oscillators cover very wide ranges but require complex alignment and a pump laser.
- MEMS-VCSEL swept sources provide 50 kHz–1 MHz tuning near 1060/1300 nm for OCT-style imaging.
- External-cavity diode lasers offer narrow linewidth with tens of nanometers tuning per module.

## Calibration Methods
- **Direct spectral calibration** captures each band with a known monochromator or certified filters to build the response matrix.
- **Reflectance-target calibration** uses a panel with known spectra under a reference light source to regress an effective response.
- **Data-driven refinement** starts from vendor data (e.g., mosaic sensors) and corrects using your own measurements.

## Build Comparison Summary
- **LED Strobe:** 400–1000 nm, ~20–50 nm bands, fast (<0.5 s per sweep), $1.5k–$3.5k.
- **LVF Push-broom:** 550–1000 nm, 7–20 nm bands, requires scanning, $3k–$6k.
- **LCTF:** 420–730 nm or 650–1100 nm, selectable 10/18/32 nm bands, 70–750 ms switching, $9k–$10k.
- **AOTF:** 351–4500 nm depending on crystal, 0.3–12 nm bands with µs tuning, $10k–$40k plus source.
- **SWIR Extension:** pair any approach with a 400–1700 nm sensor (IMX990 or InGaAs) for extended coverage.

## Other Imaging Approaches
- 3-sensor prism cameras split the scene to RGB sensors, avoiding on-sensor CFAs.
- Foveon X3 sensors stack photodiodes so each pixel senses all colors by depth.
- Snapshot mosaic imagers tile many spectral bands on-chip for instant cubes.
- Faraday Anomalous Dispersion Optical Filters (FADOF) provide GHz-wide atomic-line passbands for specialized imaging.
