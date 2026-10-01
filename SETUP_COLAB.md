# Run the workshop in Google Colab

You need a browser, internet connection and a Google account. You do not need to
install Python or VS Code on your laptop. Use a **CPU** runtime; no GPU is required.

1. Download the participant repository using **Code → Download ZIP**, then unzip it.
2. Open [Google Colab](https://colab.research.google.com). Choose **File → Upload
   notebook**, and select `workshop.ipynb` from the downloaded folder.
3. Choose **File → Save a copy in Drive** to keep your own editable notebook.
4. Choose **Runtime → Run all**. When the data-loading cell asks, select
   `data/workshop_participant.csv` from your downloaded folder. This prompt appears
   after the setup and the tiny worked example, not in the first cell.
5. Wait for the scoreboard. Optional models are skipped if their packages are
   unavailable; Ridge and Random Forest are sufficient to compete.
6. Change one setting in Model A, run that cell again, and compare its score.
7. Set `TEAM_NAME` and `ROUND`, run the identity and export cells, then open the
   left **Files** panel → `exports/` → right-click your ZIP → **Download**.
8. Upload that ZIP at the submission link supplied in the room.

## If you use the GitHub “Open in Colab” button

The notebook will download the same frozen CSV automatically if the organisers
configured `DATA_URL` for the published repository. Otherwise step 4 prompts for
an upload. Opening a notebook from GitHub does not copy the repository's data files
into Colab.

## If something goes wrong

- Missing core package: run a new code cell containing
  `%pip install pandas numpy scikit-learn matplotlib joblib`, restart the session,
  then run the notebook again. Ask a facilitator if you are unsure.
- A slow or unavailable optional model: continue with Ridge or Random Forest.
- Session reconnects to a new runtime: run the notebook again and upload the CSV
  again if prompted. Saving the notebook in Drive does not save runtime files.
- Keep your exported ZIP on your laptop before leaving. Colab runtime storage is
  temporary. Keep your notebook/change log in Drive for the debrief.

The live Colab route still needs a final rehearsal before the workshop.
