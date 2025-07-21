# Nipype Workflow Guide for Neuroimaging (mainly MRI)

---

## 📚 Terminology

| Term | Description |
| --- | --- |
| **Interface** | A wrapper around a tool (e.g., FSL's BET, SPM's coregistration) |
| **Node** | A processing unit in a workflow; wraps an interface or function |
| **MapNode** | A Node that maps a single interface over a list of inputs |
| **JoinNode** | Combines multiple outputs into one input for a downstream node |
| **Workflow** | A directed graph (pipeline) of connected nodes |
| **InputSpec/OutputSpec** | Defines expected inputs/outputs for interfaces |

---

## 🛠️ Setup

```bash
pip install nipype

```

### Optional: Install Neuroimaging Toolkits

- FSL
- ANTs
- SPM
- FreeSurfer

Make sure they're in your system's PATH and callable from the terminal.

---

## 🧱 Building Blocks

### 1. Import Modules

```python
from nipype import Node, Workflow
from nipype.interfaces.fsl import BET, IsotropicSmooth

```

### 2. Define Nodes

Each node runs a specific task.

```python
# Skull-stripping with BET
bet = Node(BET(frac=0.5), name="skullstrip")
bet.inputs.in_file = "sub-01_T1w.nii.gz"

# Smoothing with FSL
smooth = Node(IsotropicSmooth(fwhm=4), name="smooth")

```

### 3. Connect Nodes into a Workflow

```python
wf = Workflow(name="preproc")
wf.base_dir = "/output/workdir"

wf.connect([
    (bet, smooth, [("out_file", "in_file")])
])

```

### 4. Run the Workflow

```python
wf.run()

```

---

## 🧪 Example: T1 Preprocessing Pipeline

```python
from nipype import Node, Workflow
from nipype.interfaces.fsl import BET, IsotropicSmooth

# Define Nodes
bet = Node(BET(frac=0.3), name="bet")
smooth = Node(IsotropicSmooth(fwhm=5), name="smooth")

# Set inputs
bet.inputs.in_file = "sub-01_T1w.nii.gz"

# Create Workflow
preproc = Workflow(name="preproc")
preproc.base_dir = "./working_dir"

# Connect
preproc.connect([
    (bet, smooth, [("out_file", "in_file")])
])

# Run it
preproc.run()

```

---

## 🧭 Workflow Execution Details

- `base_dir` is where intermediate and final results are stored
- Nodes create their own directories under `base_dir`
- You can visualize workflows with:

```python
preproc.write_graph(graph2use='colored')

```

---

## 📌 Tips

- Use `Function` interface to wrap custom Python functions
- Use `MapNode` when you need to loop over multiple inputs
- Use `DataSink` to organize outputs
- Check each node’s `.inputs` and `.outputs` fields

---

## 📈 Optional Add-ons

- **Visualization**: `nilearn.plotting` for images
- **Logging**: Nipype logs progress and caching info
- **Parallel Execution**: Add plugin options to `.run()`

---

## ✅ Summary Workflow Template

```python
from nipype import Node, Workflow
from nipype.interfaces.fsl import BET

# Node
bet = Node(BET(frac=0.4), name="bet")
bet.inputs.in_file = "input.nii.gz"

# Workflow
wf = Workflow(name="wf_name")
wf.base_dir = "/path/to/workdir"

# Connect and run
wf.connect([])  # Add connections here
wf.run()

```

---