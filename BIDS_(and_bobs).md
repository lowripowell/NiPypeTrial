# BIDS (and bobs)

**What BIDS?**

- A standardized framework for organizing and describing neuroimaging datasets.
- Designed to improve data sharing, reproducibility, and ease of analysis.

**Why BIDS?**

- Ensures consistency in data formatting and metadata description.
- Makes datasets easier to understand and use by different researchers.
- Enables automated processing using BIDS-compatible software tools.
- Supports multiple neuroimaging modalities (MRI, fMRI, DWI, EEG, MEG, PET).

**Key Features of BIDS:**

- **Folder structure:** Defines a hierarchy for storing participant data, sessions, and scans.
- **File naming conventions:** Standardised filenames encoding participant ID, session, task, acquisition parameters, etc.
- **Metadata files:** JSON and TSV files accompany imaging data, containing acquisition parameters and participant info.
- **Validation tools:** BIDS Validator software checks dataset compliance.

**Common File Types in BIDS:**

- Imaging data: usually in NIfTI (.nii/.nii.gz) format for MRI.
- Metadata: JSON files describing scan parameters.
- Behavioural data: TSV files containing task events or participant info.

**Basic folder hierarchy example (just like the DAfNI module):**

```
bash
CopyEdit
/dataset_root
  /sub-01
    /ses-01
      /anat 
        sub-01_ses-01_T1w.nii.gz
        sub-01_ses-01_T1w.json
      /func
        sub-01_ses-01_task-rest_bold.nii.gz
        sub-01_ses-01_task-rest_bold.json
  /participants.tsv
  /dataset_description.json

```

**How to convert to BIDS (Need to look more into this if i need to use it bevause im honestly not sure):**

- Start with raw neuroimaging data (often DICOM format).
- Use conversion tools like *HeuDiConv* or *dcm2bids* to convert and organise data.
- Add/complete metadata files manually or with tools.
- Validate dataset with BIDS Validator.

**Benefits in neuroimaging research (more for explaining to people why to use it as a standard etc):**

- Simplifies collaboration and data sharing.
- Supports open science initiatives.
- Compatible with major analysis pipelines (e.g., fMRIPrep, MRIQC).
- Promotes reproducibility and transparency.