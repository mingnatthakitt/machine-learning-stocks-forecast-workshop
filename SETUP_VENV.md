# Run the workshop in VS Code

Colab is the recommended route if you do not already use Python. Local setup is
optional; complete it before the workshop. These instructions use Python **3.12**.
Fresh pip installs and Windows execution still need a rehearsal on a participant machine.

## 1. Get the files

Clone the participant repository, or choose GitHub **Code → Download ZIP** and unzip
it. In VS Code choose **File → Open Folder** and open the folder containing
`workshop.ipynb`, `requirements.txt`, and `data/`.
Install the VS Code **Python** and **Jupyter** extensions.

## 2. Create an isolated Python environment

Open **Terminal → New Terminal** in that folder. Run the block for your computer.

macOS / Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

Windows PowerShell:
```powershell
py -3.12 -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```
If PowerShell blocks activation, use `.venv\Scripts\python.exe` instead of `python`
in the installation commands below; activation is not required for that approach.

## 3. Install the packages

**Linux / Windows — all five model families:**
```bash
python -m pip install torch==2.13.0 --index-url https://download.pytorch.org/whl/cpu
python -m pip install -r requirements.txt
```
CPU is enough; no GPU is required. Installing CPU PyTorch first avoids an unnecessary
CUDA package download.

**macOS — four model families:**
```bash
python -m pip install -r requirements-macos.txt
```
The workshop's macOS pip setup encountered a torch/XGBoost OpenMP conflict, so this
recipe deliberately omits XGBoost. The notebook skips it; you can still compete.
Use Colab for all five models.

**Smallest setup on any platform — Ridge and Random Forest:**
```bash
python -m pip install -r requirements-core.txt
```
The notebook skips unavailable optional models and still trains, compares and exports.

## 4. Open and run the notebook

1. Open `workshop.ipynb` in VS Code's notebook editor.
2. Click **Select Kernel** at the top right → **Python Environments** → your `.venv`.
3. Click **Run All** in the notebook toolbar. The setup cell prints `setup OK`.
4. The notebook finds `data/workshop_participant.csv` automatically. No path editing
   is needed when you keep the supplied folder structure.
5. If you moved the CSV, set `DATA_PATH` in the data-loading cell to its full path,
   for example `r"C:\Users\You\Downloads\workshop_participant.csv"` on Windows.
6. Check the scoreboard, change one Ridge setting and rerun that model cell, then
   export a ZIP. Your ZIP appears in the local `exports/` folder.

## Troubleshooting

| Problem | Action |
|---|---|
| `python` / `py` not found | Install Python 3.12, reopen VS Code, and try again; or use Colab. |
| Missing package | Confirm the selected notebook kernel is the `.venv` where you installed the requirements. |
| Kernel does not appear | Confirm installation succeeded, then reload VS Code and select the kernel again. |
| Dataset not found | Open the repository folder, keep `data/` next to the notebook, or set `DATA_PATH`. |
| macOS kernel dies after adding XGBoost | Use a fresh environment with `requirements-macos.txt`, or switch to Colab. |
| Installation takes too long | Use the core-only setup or Colab; ask a facilitator. |

Ready means: setup OK, dataset loaded, a model score printed, and one ZIP exported.
