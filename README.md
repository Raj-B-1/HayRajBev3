# HayRajBev3

## AI-Generated Image Detection

**Course:** DS 4002 Section 001  
**Date:** 12/2025  
**Team Members:** Raj Bhowmic (leader), Hayden Cook, Beverley Appiatse 
**Instructor:** Professor Alonzi  

---

## Contents of the Repository

This repository follows the TIER Protocol 4.0 to ensure transparency and reproducibility. Top-level items:

- LICENSE.md  
- README.md (this file)  
- SCRIPTS/ — source code and Jupyter notebooks  
- DATA/ — raw and processed datasets and metadata_README.md  
- OUTPUT/ — figures, tables, and model outputs  

---

## Section 1: Software and Platform

### Software used
- Python 3.10 (Anaconda or standard distribution)  
- Jupyter Notebook (Rivanna Open OnDemand)

### Add-on packages (install before running)
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  
- pillow  
- tqdm  
- imagehash  
- PyWavelets  
- torch  
- torchvision  

(Install with: `pip install -r requirements.txt` — `requirements.txt` is included in the repo.)

### Platform
- Developed and tested on **UVA Rivanna HPC (Linux environment)**  
- Compatible with Windows 10/11 and macOS for smaller-scale tests  

---

## Section 2: Map of Documentation

**Repository structure (top-level):**

- README.md  
- LICENSE.md  

- SCRIPTS/  
  - 11-17(6).ipynb – Exploratory data analysis (class balance, sample grids, basic statistics).   
  - Real_vs_Fake_Detector.ipynb – CNN-based classifier training notebook. 

- DATA/  
  - Link to Dataset.pdf/ – Original downloaded images (AI-generated and real).  

- OUTPUT/  
  - EDA/ – EDA plots and model evaluation figures.  
  - Model Accuracy/ – CSV files with accuracy summaries, loss metrics, and evaluation results.

Each folder contains a local README.md (where relevant) describing contents and usage.

---

## Section 3: Instructions for Reproducing Results

Follow these steps in order to reproduce the project results.

1. **Clone the repository and change directory**  
   - `git clone https://github.com/your-username/HayRajBev3.git`  
   - `cd HayRajBev3`

2. **Set up environment**  
   - (Recommended) Create and activate a virtual environment.  
     - macOS / Linux:  
       - `python -m venv env`  
       - `source env/bin/activate`  
     - Windows (PowerShell):  
       - `python -m venv env`  
       - `.\env\Scripts\Activate.ps1`  
   - Install dependencies:  
     - `pip install -r requirements.txt`

3. **Obtain data**  
   - Launch JupyterLab on Rivanna using Open OnDemand.  
   - Open `SCRIPTS/01_download_data.ipynb`.  
   - Run all cells to download and unzip the selected dataset (e.g., `CNN_synth_testset.zip` from HuggingFace or a GenImage subset).  
   - Confirm that the unzipped folders appear inside `DATA/raw/`.

4. **Preprocess data**  
   - Open `SCRIPTS/03_preprocessing.ipynb`.  
   - Run all cells to:  
     - Resize and/or normalize images (if applicable).  
     - Create train/validation/test splits.  
     - Generate metadata tables (e.g., file paths, labels).  
   - Outputs are saved into `DATA/processed/`.

5. **Run exploratory data analysis (EDA)**  
   - Open `SCRIPTS/02_eda.ipynb`.  
   - Run all cells to produce:  
     - Class distribution plots (real vs AI).  
     - Sample image grids.  
     - Summary tables of counts and basic stats.  
   - Figures and tables are saved to `OUTPUT/figures/` and `OUTPUT/tables/`.

6. **Train baseline and models (if included)**  
   - Open `SCRIPTS/04_model_training.ipynb`.  
   - Adjust hyperparameters (e.g., epochs, batch size, learning rate) if needed.  
   - Run all cells to train the CNN-based classifier on the processed dataset.  
   - Model artifacts and logs are written to `OUTPUT/model_artifacts/` and `OUTPUT/tables/`.

7. **Generate visualizations and results**  
   - Open `SCRIPTS/05_visualizations.ipynb`.  
   - Run all cells to recreate final plots used in the project presentation and report (e.g., confusion matrix, performance bar charts).  
   - Final figures are saved to `OUTPUT/figures/` and summary tables to `OUTPUT/tables/`.

8. **Verify outputs**  
   - Confirm that:  
     - Figures in `OUTPUT/figures/` match those referenced in the MI2/MI3 deliverables.  
     - Metrics in `OUTPUT/tables/` match the values reported in the project documentation.  
   - For more reproducible runs, set random seeds in the training notebook where applicable.

**Notes:**  
- Full image datasets are not stored in the repo due to size constraints and must be downloaded using the provided notebook.  
- Rivanna is recommended for handling large image collections because of memory and storage requirements.  

---

## References

GenImage-Dataset. (2023). *GenImage: A Million-Scale Benchmark for Detecting AI-Generated Images.* GitHub Repository.  
CNNDetection Dataset. *Synthetic and Real Image Benchmark for AI-Generated Image Detection.* HuggingFace.  
OpenAI ChatGPT. (2025). Assistance with exploratory analysis, documentation, and workflow design.

---

## License

This repository is licensed under the MIT License. See `LICENSE.md` for details.






