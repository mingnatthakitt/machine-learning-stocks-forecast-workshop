# Machine Learning Stocks Forecast Workshop

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mingnatthakitt/machine-learning-stocks-forecast-workshop/blob/main/workshop.ipynb)

**Start in Colab:** click the button, save a copy in Drive, then choose **Runtime → Run all**. The data loads automatically.

**This folder is everything you need as a workshop attendee.** This participant repository contains the notebook, setup guides and public training
data. Your private competition evaluation is handled by the organisers.

## New to coding? Start here

You will use ready-made code. Your first experiment is changing one number.

1. Run the supplied notebook in Colab and upload the CSV when prompted. A cell is
   one box of code; its ▶ button runs it and the result appears underneath.
2. Find **Model A — Ridge**. Note its validation MAE: smaller is better.
3. Change `"alpha": 1.0` to `"alpha": 10.0`, keeping the punctuation. Run that
   cell again and compare the new MAE with the old value. Either outcome is useful.
4. Record what you changed. Rerun the scoreboard cell to update its table; avoid
   rerunning shared training setup, which resets stored experiments.
5. Set your team name and round, run the export cell, download the ZIP from Colab's
   Files panel, and upload it at the organisers' link using the room PIN.

You can contribute by suggesting changes, comparing scores, or taking notes. Ask a
facilitator if a cell fails or you cannot find the ZIP. The team exports its best
stored candidate by validation score unless it explicitly picks a model.


## What's in here

| File | What it is | When to open it |
|---|---|---|
| `workshop.ipynb` | The starter notebook — your workspace for the whole workshop. All training plumbing is done; you compete by editing clearly-marked 🟩 sections. | From 0:42 (briefing) onward |
| `GUIDE.md` | Section-by-section walkthrough of the notebook, with the *why* behind every part + a troubleshooting table | Skim before Round 1; keep open while you work |
| `CHEATSHEET.md` | One-page quick reference: feature menu, hyperparameter dials, rules, export checklist | **During Round 1 & 2** (it's competition-legal) |
| `SETUP_VENV.md` | Local install guide for VS Code + venv users (macOS caveats included) | Only if not using Colab |
| `requirements.txt` | Full Linux/Windows local setup | Used by SETUP_VENV.md |
| `requirements-core.txt` | Small setup for Ridge and Random Forest | Fast local fallback |
| `SETUP_COLAB.md` | Browser setup, CSV upload and ZIP download | Recommended starting point |
| `DATA_SOURCE.md` | Data origin, dates and snapshot checksum | Dataset reference |
| `requirements-macos.txt` | Pinned local packages for macOS venv; omits XGBoost to avoid the torch/OpenMP conflict | Used by SETUP_VENV.md on macOS |
| `data/workshop_participant.csv` | The dataset: OHLCV for **SPY, NVDA, AAPL, MSFT, TSLA**, 2014–2024, split-adjusted | Loaded by the notebook automatically |
| `exports/` | Created when you export your trained model | Download your ZIP for hand-in |

**Not in this folder (and never will be):** the private 2025 labels your model will be
scored against, and the 2026 holdout. That's the whole point.

## Quick start

### Google Colab (recommended — no laptop installation)
Follow **[SETUP_COLAB.md](SETUP_COLAB.md)**. Download this repository as a ZIP,
upload `workshop.ipynb` to Colab, save a copy in Drive, and choose **Runtime → Run all**.
Upload the supplied CSV when the data-loading cell asks. Once the organisers publish
a configured Colab button, that route downloads the same CSV automatically.

### Local VS Code
Clone this repository or download/unzip it, then follow **[SETUP_VENV.md](SETUP_VENV.md)**.
The notebook finds `data/workshop_participant.csv` automatically; you do not need
to paste a path unless you move the file. `DATA_PATH` accepts a custom local path;
`DATA_URL` accepts a direct CSV download link.

All routes use the **same frozen 2014–2024 CSV**. Do not fetch new Yahoo data during
the competition. Core-only installs can compete using Ridge and Random Forest;
macOS pip installs omit XGBoost because of the observed packaging conflict.

## The competition in 60 seconds

- **Competition block: 0:42–1:42 (60 minutes total):** 6 minutes for briefing,
  36 minutes to work across both rounds (20 + 16), and 18 minutes for evaluation
  and results.
- **Task:** predict each ticker's **next-day return**. Primary metric: **MAE**, pooled
  over all five tickers (lower = better).
- **The bar:** "always predict 0" scores ≈ **0.0162** on the private 2025 set. Beating
  that is the whole game.
- **Round 1 (0:48–1:08) — human only.** No ChatGPT/Claude/Gemini/Copilot. Slides,
  cheatsheet, docs, teammates and facilitators are allowed.
- **Round 2 (1:18–1:34) — AI unlocked.** Use AI, then record suggestions and changes
  in the notebook's change log. The log is not in the model ZIP; keep the notebook
  available for the debrief. Re-export with `ROUND = 2`.
- **Hand-in:** run the 📦 export cell → upload the zip it produces at the **submission
  link and PIN on the whiteboard** (a page on the facilitator's laptop; you can use
  your phone). Type your team name exactly as agreed, pick your round, press upload.
  You get a ✓ with a receipt hash — that's your proof of hand-in. You can re-upload
  until the deadline; the last one counts. If the link doesn't load, the Wi-Fi is
  probably blocking device-to-device traffic: ask a facilitator for the hotspot
  password, or hand the zip over on a USB stick. **No zip = no leaderboard row.**

## When you're stuck

1. Check the troubleshooting table at the end of [`GUIDE.md`](GUIDE.md).
2. Re-read the 🟩 banner comments above the cell you're editing.
3. Ask a facilitator — that's what they're floating around for.
