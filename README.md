# Custom CNNs vs. Transfer Learning — Food-101 Subset

> **Assignment:** Compare a CNN built from scratch against a MobileNetV2 Transfer Learning model on a 10-class subset of the Food-101 dataset.

---

## 📁 Project Files

| File | Description |
|---|---|
| `cnn_vs_transfer_learning.ipynb` | Main experiment notebook |
| `CNN_vs_TransferLearning_Report.pdf` | Report |
| `requirements.txt` | Python package dependencies |
| `README.md` | This file |

---

## ⚙️ Environment Setup

Choose the setup that matches where you are running the notebook.

---

### ▶️ Option A — Google Colab or Kaggle (Recommended)

No local setup needed. TensorFlow and GPU drivers are pre-installed.

1. Upload `cnn_vs_transfer_learning.ipynb` to [Google Colab](https://colab.research.google.com) or [Kaggle](https://www.kaggle.com/code).
2. Enable the GPU runtime:
   - **Colab:** `Runtime → Change runtime type → T4 GPU`
   - **Kaggle:** `Session options → Accelerator → GPU P100`
3. Run the first cell — it installs `tensorflow-datasets` automatically:
   ```python
   !pip install tensorflow-datasets -q
   ```
4. Run all cells in order (`Runtime → Run all`).

> **Note:** Food-101 is ~5 GB. Colab/Kaggle download it automatically on first run and cache it for the session.

---

### 🐍 Option B — Local Machine (CPU or GPU)

#### Prerequisites

- **Python 3.9, 3.10, or 3.11** — [Download](https://www.python.org/downloads/)
- *(Optional for GPU)* NVIDIA GPU + CUDA 11.8 or 12.x + cuDNN 8.x

#### Step 1 — Clone or download the project

```bash
# If using git
git clone <your-repo-url>
cd <project-folder>

# Or simply place all files in a folder and cd into it
cd path/to/project
```

#### Step 2 — Create a virtual environment

```bash
# Create the environment (only once)
python -m venv venv
```

#### Step 3 — Activate the environment

```bash
# macOS / Linux
source venv/bin/activate

# Windows (Command Prompt)
venv\Scripts\activate.bat

# Windows (PowerShell)
venv\Scripts\Activate.ps1
```

You should see `(venv)` at the start of your terminal prompt.

#### Step 4 — Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

This installs:

| Package | Purpose |
|---|---|
| `tensorflow` | Deep learning framework (includes Keras) |
| `tensorflow-datasets` | Downloads and loads Food-101 automatically |
| `numpy` | Array operations |
| `matplotlib` | Plotting training curves |

#### Step 5 — Launch Jupyter

```bash
pip install jupyter          # only if not already installed
jupyter notebook
```

Then open `cnn_vs_transfer_learning.ipynb` in the browser tab that opens.

---

### 🐳 Option C — Conda Environment

If you prefer Conda (Anaconda/Miniconda):

```bash
# Create environment with Python 3.10
conda create -n cnn_project python=3.10 -y
conda activate cnn_project

# Install pip packages
pip install -r requirements.txt

# Launch notebook
pip install jupyter
jupyter notebook
```

---

## 🚀 Running the Experiment

Once the environment is ready and the notebook is open, run cells **in order** from top to bottom:

| Section | Cell | Action |
|---|---|---|
| 0 | Install & Imports | Installs `tensorflow-datasets`, imports libraries |
| 1 | Configuration | Sets hyperparameters — edit here to experiment |
| 2 | Data Loading | Downloads Food-101 (~5 GB), filters 10 classes |
| 3 | Phase 1 — Scratch CNN | Builds and trains custom CNN with RMSprop |
| 4 | Phase 2 — Transfer Learning | Loads MobileNetV2, trains classification head with Adam |
| 5 | Visualisations | Saves `plot_scratch.png`, `plot_tl.png`, `plot_comparison.png` |
| 6 | Results Summary | Prints comparison table of both models |
| 7 | Conclusion | Guided discussion template |

---

## 📚 References

- Bossard et al. (2014). *Food-101 — Mining discriminative components with random forests.* ECCV.
- Sandler et al. (2018). *MobileNetV2: Inverted residuals and linear bottlenecks.* CVPR.
- [TensorFlow Transfer Learning Guide](https://www.tensorflow.org/tutorials/images/transfer_learning)
- [TensorFlow Datasets — Food101](https://www.tensorflow.org/datasets/catalog/food101)
