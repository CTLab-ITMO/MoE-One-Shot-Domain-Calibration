# Material versions and provenance

Collected on **2026-11-03**. The [manifest](materials-manifest.json) records every imported file and its SHA-256 checksum. Imported content was copied without scientific or code changes.

## Current ICDM materials

`posters/icdm2026/S16207.pdf` is the ARRL / IEEE ICDM 2026 poster with the original KDD author order retained. It includes Telegram @Turukmokto, email esbessonn@gmail.com, and a QR linking to this repository. The single page measures 33.1 × 46.8 inches. `src/` contains the editable source, and `overleaf.zip` contains a ready upload package with the PDF.

## Manuscript version

`paper/preprint.pdf` is the supplied `Final_MOE_Bias.pdf`. Its title is “One-Shot Domain Calibration of MoE Routers via Gradient Bias Steering”; its author block is anonymous. A second local file named `Final_MOE_Bias (1).pdf` was byte-identical and was not duplicated. The manuscript has not been identified as the final ICDM camera-ready version. No manuscript LaTeX source was available in the collected materials.

## Historical KDD materials

`archive/kdd2026/poster.pdf` is the originally supplied KDD poster; `overleaf.zip` preserves the original complete source archive, including intermediate versions. Its old branding, contact details, and QR destinations are historical. Use the current ICDM files for this presentation.

## Code provenance

The four files under `experiments/legacy/` originate from `MoE_Optimization/MoE_auto_bias_experiments`. Their original filenames and contents are preserved. Related expert-fusion code belongs to the separate MoE_Optimization project and is not part of this calibration repository.

## Verification

- Current poster preview inspected; page dimensions and email checked.
- Current GitHub and Telegram QR payloads decoded from the rendered PDF.
- Imported file checksums verified against their sources.
- Python script syntax checked without executing model downloads or GPU experiments.
- Documentation links and ZIP integrity checked.
