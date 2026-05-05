# LiPo Battery Decoder

A client-side calculator designed to decode standard 3.7V Lithium Polymer pouch cell codes and verify their actual capacity against manufacturer claims.

## Live Demo
[View the Calculator](https://cheetoss-dev.github.io/lipo-battery-decoder/)

## Motivation
The primary motivation for this tool is the prevalence of exaggerated capacity claims printed on generic lithium polymer batteries. When designing embedded power systems, relying on unverified manufacturer specifications can lead to severe miscalculations in runtime and mass budgets. Because physical volume strictly dictates the maximum chemical energy a pouch cell can hold, these false claims can be mathematically disproven. This calculator automates the process of deriving realistic capacity bounds based on actual physical dimensions and established volumetric energy density limits (Wh/L).

## Core Functions
* **Code Parsing:** Decodes standard 6-digit (e.g., 402030) and 7-digit (e.g., 1003048) cell nomenclature.
* **Dimensional Correction:** Automatically handles the industry naming anomaly for 10-19mm thicknesses, where standard fractional formatting is bypassed.
* **Volumetric Calculation:** Computes exact spatial volume to determine the structural limits of the active material.
* **Capacity Verification:** Generates a realistic mAh estimate based on standard energy density tiers (250 Wh/L to 650 Wh/L). The algorithm automatically penalizes the efficiency of smaller cells to account for non-active packaging overhead.
* **Reference Plotting:** Graphs the calculated data against a dataset of verified commercial LiPo cells to provide an immediate comparative baseline.

## Usage
Enter the code printed on the battery sleeve to output the physical dimensions and verify the theoretical capacity limits.

Examples:
* **402030** -> 4.0mm x 20mm x 30mm (Theoretical limit ~196 mAh)
* **103048** -> 10.0mm x 30mm x 48mm (Theoretical limit ~1500 mAh)
* **5025100** -> 5.0mm x 25mm x 100mm (Theoretical limit ~1350 mAh)

## License
Distributed under the MIT License.
