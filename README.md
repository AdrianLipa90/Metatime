
# PBH Detection Framework (CIEL/0)

## Overview

This repository contains tools for processing Planck Satellite FITS files to verify the existence of a Primordial Black Hole (PBH) or Planet X within the Solar System. The analysis is based on the CIEL/0 unified framework developed by Adrian Lipa, which integrates gravitational dynamics, metatime theory, and CMB anomalies.

## Project Objective

Analyze specific regions of the Cosmic Microwave Background (CMB) for point-source anomalies or gravitational lensing signatures. Based on 100,000-year orbital simulations (using the REBOUND integrator), the predicted coordinates for the PBH are:

- **RA:** 07^h 10^m 18.395^s
- **Dec:** -25° 54' 27.284''
- **Constellation:** Puppis

## Repository Structure

```
.
├── data/
│   └── .fits files (Planck 100, 143, 217 GHz, Releases 1–3)
├── src/
│   └── Python scripts for image processing and statistical analysis
├── docs/
│   └── PDF documentation (Neutrinotime, CMB Dynamics papers)
└── cielnofft.txt
    └── CIEL/0 Theory of Everything framework implementation
```

## Key Features

- **Multi-Rel Cross-Correlation:** Compares Rel1 vs Rel3 to detect temporal changes or moving sources
- **Background Subtraction:** Uses `sigma_clipped_stats` to remove CMB noise and isolate anomalies
- **WCS Mapping:** Translates celestial coordinates (RA/Dec) to pixel coordinates in Planck maps
- **Automated Source Detection:** Implements DAOStarFinder to flag objects exceeding 5σ threshold

## Quick Start

### Installation

```
pip install numpy astropy matplotlib photutils
```

### Usage

Place FITS files in root directory and execute:

```
import src.pbh_analyzer as pbh
pbh.run_full_scan(target_ra=107.5766, target_dec=-25.9075)
```

## Analysis Parameters

| Parameter | Value | Source |
|-----------|-------|--------|
| Semi-major axis | 430 AU | Lipa (2025) |
| Eccentricity | 0.78 | TNO Perturbation Model |
| Inclination | 27° | Puppis-Sector Calculation |
| Detection Sigma | > 5.0 | Point Source Threshold |

## Scientific Background

The scripts utilize the **LPEG Model** (Lipa-Penrose-Ebrahimi-Greene), which proposes that the cosmological constant (Λ) is dynamic and can be influenced by local informational coherence. The search for the PBH represents a critical test of this theoretical framework.

**Note:** For theoretical foundations on time as a tensor-scalar field, refer to `docs/Neutrinotime.pdf`.

---

**Author:** Adrian Lipa  
**Framework:** CIEL/0  
**Last Updated:** 2025
```

