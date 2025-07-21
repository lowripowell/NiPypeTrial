# NiPypeTrial
Turning my masters research project on spatial smoothing for fMRI into a NiPype workflow to get use to BIDS and other techniques

# 🧠 Nipype-based fMRI Analysis Pipeline for Spatial Smoothing Analysis Effect

This repository will eventually contain the complete analysis pipeline for my Master's research project:  
**"Blurred Lines: How Spatial Smoothing
Influences the Statistical Analysis and
Interpretation of fMRI Data"**, developed using NiPype
📄 [Download Research Project (PDF)](Research_Project.pdf)


---

## 📚 Project Summary

This project investigates how changing the spatial smoothing level of a single fMRI dataset can impact the statistcial analysis and interpretation of data.

I will be implementing a BIDS style pipeline using Nipype to integrate statistical analysis and preprocessing techniques. The aim is to get the workflow to be container ready and publivly reporducible.


---

## 🧩 Features

- BIDS-compliant input/output
- Modular Nipype workflow (e.g., FSL + FreeSurfer + custom node)
- Reproducible environment via [Docker / Singularity / Conda]
- Clean, documented codebase for educational use

---

## 📂 Proposed Repository Structure

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
