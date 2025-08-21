# AI & Water Stress: Mapping U.S. Data Center Risks

[![View Site](https://img.shields.io/badge/GitHub%20Pages-Deployed-brightgreen)](https://chelsearbann.github.io/AI-WaterStress-DataCenter-Analysis/)
[![Author](https://img.shields.io/badge/Author-chelsearbann-blue)](https://github.com/chelsearbann)

## Overview

This project explores the environmental sustainability of U.S. AI infrastructure by mapping the overlap between data center density and baseline water stress. Data centers, especially those supporting AI, consume large amounts of water for cooling and are often sited in regions already under high water stress.
The interactive visualizations and choropleth maps help identify geographic regions where infrastructure risk overlaps with climate vulnerability, offering insights for policy, industry, and sustainability researchers.

Summary:
- **Goal**: Identify U.S. states where high concentrations of data centers coincide with projected long-term water stress.
- **Why it matters**: The environmental footprint of AI infrastructure is growing. Water stress is an emerging risk in site selection and long-term operations.

---

## Research Question

> *To what extent are AI data centers concentrated in water-stressed regions in the U.S.?*

---

## Visuals

- **Bar Chart**: Data center count by state
- **Stacked Bars**: Water stress level distribution
- **Scatter Plot**: Mean water stress vs. data center count
- **Composite Risk Index**: BWS × Data Centers
- **Choropleth Map**: State-level visualization of BWS and infrastructure density

Visualizations were created using **`ggplot2`** and geospatial packages in **R**.

---

## Tools Used
- [`R`](https://www.r-project.org/)
- `ggplot2`, `dplyr`, `tidyr`, `maps`
- [`Quarto`](https://quarto.org/) for publishing
- [`GitHub Pages`](https://pages.github.com/) for hosting

---

## Project Structure
- Data/ # Source CSVs: Water stress, data center counts
- Figures/ # Exported maps and plots
- Libs/ # Supporting JS/CSS (quarto, tippy, popper, etc.)
- FinalProjQuarto.qmd # Quarto analysis + visual generation
- index.html # Deployed landing page
- README.md # This file

---

##  Methodology
This study integrates and analyzes:
- AI **Data Center Quantity by State** (scraped from DataCenterMap.com)
- **Baseline Water Stress Scores** from the World Resources Institute's [Aqueduct 4.0](https://www.wri.org/data/aqueduct-global-maps-40-data)

Approach:
- Cleaned and joined WRI Aqueduct 4.0 data with scraped data center counts from DataCenterMap.com.
- Cleaned and aggregated water stress data (excluding nulls) using R packages: `dplyr`, `ggplot2`, `maps`, and `tidyr`.
- Calculated **Mean**, **Mode**, and **High-Stress Proportion** (BWS ≥ 4)
- Built a **Composite Risk Index** (Data Centers × Mean BWS)
- Merged region-level data and mapped using `ggplot2` + `map_data()` with state polygon overlays for choropleth maps, scatter plots, and stacked bar graphs

---

## Interpretation

- Regions such as **Arizona, California, and Texas** stand out with both high water stress and heavy data center presence. The composite risk analysis suggests that infrastructure investment in these areas may require additional sustainability planning, particularly as water demands rise with AI proliferation.
- Many states with **high concentrations of data centers** are also **projected to experience high water stress**.
- Site selection for data centers often favors **tax incentives and cheap land**, which can lead to **vulnerability in water-scarce regions**.
- **Composite Risk Score** identifies states with critical overlaps between AI infrastructure and water scarcity.

---

## Live Page

[**View GitHub Pages Site**](https://chelsearbann.github.io/AI-WaterStress-DataCenter-Analysis/)

---

## License

This project is licensed under the MIT License. See [`LICENSE`](LICENSE) for details.

---

## References

> Full list of citations available in the Quarto document. Key sources include:

- **Aqueduct 4.0 Dataset** — World Resources Institute
- **AI Infrastructure Reports** — Department of Energy, DataCenterMap
- **News & Case Studies** — New York Times, SELC, University of Tulsa

---

## Future Improvements

- Add granularity (county or watershed level)
- Incorporate time-series water projections (2030, 2050, 2080)
- Separate AI-heavy vs general-use data centers
- Integrate corporate water use disclosures for private-sector accountability

---

*Created by Chelsea Bann | 2025 | Tufts University*

