# NiPypeTrial
Turning my masters research project on spatial smoothing for fMRI into a NiPype workflow to get use to BIDS and other techniques

# 🧠 Nipype-based fMRI Analysis Pipeline for [Your Project Title]

This repository will eventually contain the complete analysis pipeline for my Master's research project:  
**"Blurred Lines: How Spatial Smoothing
Influences the Statistical Analysis and
Interpretation of fMRI Data"**,  developed using [Nipype](https://nipype.readthedocs.io/en/latest/) to ensure modularity, reproducibility, and compatibility with the BIDS standard.

---

## 📚 Project Summary

This project investigates [brief 1–2 sentence summary of the research goal].

We implemented a BIDS-compliant pipeline using Nipype to integrate [e.g., FSL preprocessing, SPM statistics, custom Python analysis, etc.]. The workflow is container-ready and publicly reproducible.

---

## 🧩 Features

- BIDS-compliant input/output
- Modular Nipype workflow (e.g., FSL + FreeSurfer + custom node)
- Reproducible environment via [Docker / Singularity / Conda]
- Clean, documented codebase for educational use

---

## 📂 Repository Structure

```bash
project/
├── workflow/            # Nipype scripts and nodes
├── env/                 # Environment files (e.g., Dockerfile or .yml)
├── data/                # Empty folder for BIDS dataset
├── outputs/             # Results directory (not included)
├── utils/               # Custom Python modules
├── LICENSE
├── requirements.txt     # Python dependencies
├── README.md
└── run_pipeline.py      # Entry point
