# Docker Bits

- basicall y makes the computer environment portable

## ⚙️ **Why use Docker in Neuroimaging?**

Neuroimaging software is:

- Often complicated to install (many dependencies)
- Version-sensitive (e.g., FSL, AFNI, SPM, FreeSurfer, etc.)
- Difficult to reproduce exactly across labs

Docker solves this by letting you:

- Share your **entire analysis pipeline** as a container
- Run pipelines (e.g., fMRIPrep, MRIQC, QSIPrep) easily
- Avoid the "it worked on my machine" problem
- Support **BIDS Apps**, which are all Dockerized!

---

## 🔧 **Key Concepts**

| Term | Description |
| --- | --- |
| **Image** | A snapshot of a container environment (like a recipe) |
| **Container** | A running instance of an image (like a live kitchen) |
| **Dockerfile** | A script that defines how to build an image |
| **Volumes** | Folder mappings between your host and container |
| **Bind mount** | Way to give a container access to your local files |

---

## 🧠 **Using Docker with BIDS Apps (e.g., fMRIPrep)**

Here’s a basic example of running **fMRIPrep** on a BIDS dataset:

```bash
bash
CopyEdit
docker run -ti --rm \
  -v /my/data/bids:/data:ro \
  -v /my/output:/out \
  -v /my/license:/fs/license.txt \
  nipreps/fmriprep:latest \
  /data /out participant \
  --fs-license-file /fs/license.txt

```

### What that means:

- `v /my/data/bids:/data:ro`: bind your BIDS dataset into the container (read-only)
- `v /my/output:/out`: where to save outputs
- `v /my/license:/fs/license.txt`: FreeSurfer license required by fMRIPrep
- `nipreps/fmriprep:latest`: the Docker image you're using
- `/data /out participant`: positional arguments required by fMRIPrep

---

## 📦 **How to Install Docker**

### On Ubuntu/Linux:

```bash
bash
CopyEdit
sudo apt update
sudo apt install docker.io
sudo systemctl enable --now docker

```

### On macOS or Windows:

- Download Docker Desktop: https://www.docker.com/products/docker-desktop

---

## 🧪 **Other Common Neuroimaging Uses**

- **HeuDiConv** for BIDS conversion
- **MRIQC** for MRI quality control
- **QSIPrep** for diffusion MRI processing
- **Nipype workflows** (run inside containers)
- **Custom container builds** for your own analysis

---

## 🛑 Things to Be Aware Of

- Docker needs admin privileges.
- File access can be tricky (make sure your paths are correct).
- On HPC clusters, **Singularity** is often used instead of Docker (same concept, HPC-friendly).

---

## ✅ Summary

| Benefit | Why it matters |
| --- | --- |
| Reproducibility | Everyone runs the same container |
| Portability | Works on any system (Linux, Mac, Windows) |
| Isolation | Keeps environments clean and separated |
| Automation | Easily integrated into scripts and pipelines |