`
# Breathing & Cough Detection

This is the repository for the semester project of Biomedical System Processing, 2025, for the group "OLEMFA" with the following members:
- Faizyab Ali Shah
- Muhammed Emre Candir
- Olena Mikhailova

## Directories:
The repository consists of the following directories:
- **raw_data**: This contains the audio recordings of all the participants in the form [participant_name]_[recording_type].wav. Recordings are of types: normal, fatigue, and cough.
- **Cleaned_data**: This directory contains the same recordings, except only the properly recorded parts of the recordings are preserved.
- **code**: This directory contains all the notebooks:
  - machine_learning.ipynb: This notebook contains the machine learning approach for the project.
  - signal_processing_experimental_code.ipynb: This notebook contains the signal processing experiments mentioned in the report.
  - signal_processing_final_code.ipynb: This notebook contains the final methodologies chosen and maintained for the signal processing part. 

## How to Run

1. **Signal processing notebooks**:
   - Open the notebook in google colab.
   - Upload all the files from cleaned_data folder into colab without placing them inside of any directory.
   - Run the cells from top to bottom. The notebook will automatically:
     - load the audio files,
     - extract the breathing envelope,
     - detect breathing peaks,
     - compute BPM & BRV,
     - run cough detection,
     - generate visualizations,
     - and print the final results table.

2. **Machine learning notebook**:
   - Open ``machine_learning.ipynb`` in Google Colab or a local Jupyter environment.
   - Ensure the ``raw_data`` and ``annotations`` directories are uploaded/accessible.
   - Run the cells from top to bottom. The notebook will automatically:
     - Load raw audio and segment files based on CSV annotations.
     - Perform raw data analysis and plot sample spectrograms/waveforms.
     - Extract physics-based, spectral, and temporal features (e.g., Entropy, BPM, MFCCs).
     - Train an **Extra Trees Classifier** using **Leave-One-Group-Out (LOGO)** cross-validation.
     - Generate a **Scientific Hypothesis Testing Report** with T-tests, confusion matrices, and ROC curves to validate classification performance.

## Requirements
- Python 3.8+
- Install dependencies: 
`` pip install numpy scipy librosa matplotlib pandas scikit-learn soundfile seaborn``