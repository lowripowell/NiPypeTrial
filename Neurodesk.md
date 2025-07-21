# Neurodesk

## 🧠 **What Neurodesk?**

**Neurodesk** is a project that offers a **portable, container-based, virtual desktop environment** loaded with neuroimaging software. It runs on Linux, macOS, Windows, or even HPC systems and cloud platforms.

It uses containers under the hood (like Docker or Singularity), but **you don’t need to manage containers directly** — Neurodesk handles it for you via a clean desktop interface or command-line tools.

---

## ✅ **Why Neurodesk?**

| Feature | Benefit |
| --- | --- |
| 🧰 Preinstalled software | FSL, SPM, FreeSurfer, ANTs, MRtrix, AFNI, and many more — ready to go |
| 📦 Containerized apps | Clean and reproducible — runs the same everywhere |
| 💻 Easy GUI access | Use full graphical apps (e.g., FSLeyes, MRIcroGL) in a virtual desktop |
| 🖥️ Runs anywhere | Local machines, HPCs, or cloud platforms |
| 🔁 No admin required | You don’t need root privileges to install or run it (especially in Singularity mode) |
| 🧪 BIDS-compatible | Great for running BIDS apps and workflows reproducibly |

---

## 🧭 **How It Works**

There are two main ways to run Neurodesk:

### 1. **Neurodesktop**

- A full **virtual Linux desktop** running inside a container.
- Use GUIs like FSLeyes or FreeView.
- Useful for training, visualization, and interactive analysis.
- Requires **Docker** or **Apptainer/Singularity** depending on platform.

### 2. **Neurocommand**

- Command-line interface for launching specific neuroimaging tools without a GUI.
- You can script and automate workflows.
- Ideal for cluster/HPC use or experienced users.

---

## 🚀 **How to Get Started (Local Example)**

### Step 1: Install Docker

(If you don’t already have it)

https://docs.docker.com/get-docker/

### Step 2: Launch Neurodesk

Run this in the terminal:

```bash
bash
CopyEdit
docker run -it --rm \
  -v $HOME:/neurodesktop-home \
  -p 8080:8080 \
  vnmd/neurodesktop:latest

```

Then open your browser and go to:

👉 [**http://localhost:8080**](http://localhost:8080/)

This gives you a **desktop in your browser** with access to all neuroimaging tools.

---

## 🔒 **No Docker? Use Singularity**

For HPC environments that don’t support Docker:

```bash
bash
CopyEdit
module load singularity
singularity exec neurodesktop.sif bash

```

You can download the `.sif` image from Neurodesk’s website or build it using their tools.

---

## 🛠️ **What’s Included?**

A few examples:

- **FSL**
- **SPM**
- **AFNI**
- **FreeSurfer**
- **MRtrix**
- **ANTs**
- **Dipy**
- **BIDS apps**
- … and more, all pre-configured

---

## 🧠 **Ideal Use Cases**

- Teaching neuroimaging (no software installation headaches)
- Trying new tools before installing them locally
- Working on shared analysis in teams
- Running tools on clusters without local installs
- Combining GUI + CLI tools easily

---

## 🔗 Resources

- Website: [https://www.neurodesk.org](https://www.neurodesk.org/)
- GitHub: [https://github.com/NeuroDesk](https://github.com/NeuroDesk)
- Docs: https://www.neurodesk.org/docs