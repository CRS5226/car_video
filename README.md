# 📊 Communication Analysis Tool for Human-AI Interaction Driving Simulator Experiments

This project is part of a screening test to analyze communication in a simulated environment. It consists of two main Python programs:

- **Data Handling & Analysis**: Transcribes and analyzes sentiment from driving simulator video files.
- **Data Understanding & Manipulation**: Visualizes transcription frequency and sentiment results using plots.


## 🧪 1. Data Handling & Analysis

This part handles:

- Importing and preprocessing video/audio files
- Performing speech-to-text transcription (using Whisper)
- Segmenting audio into 5-second chunks
- Mapping each transcription to its start timestamp
- Conducting sentiment analysis using a pre-trained transformer model (e.g., `distilbert-base-uncased-finetuned-sst-2-english`)

### Output

- Results are saved as a CSV with the following columns:
  - `chunk_id`
  - `start_time`
  - `transcription`
  - `sentiment`

➡️ **Output is saved as**: `output/transcription_<video_name>.csv`


## 📈 2. Data Understanding & Visualization

This part:

- Loads a generated transcription CSV
- Generates:
  - 📊 Histogram of transcribed line frequency per 5-second bucket
  - 📈 Sentiment distribution plot (positive / neutral / negative)

Both plots are automatically generated and displayed using **matplotlib** and **seaborn**.


## ▶️ How to Run

### ✅ Option 1: Run Online

You can run this project directly in:

- ✅ **Kaggle Notebook**: All dependencies are pre-installed, just upload and update the dataset path.
- ✅ **Google Colab**: Upload the `.ipynb` file and mount your dataset.

No setup is required on either platform. Just upload the dataset and run the notebook cells.


### 💻 Option 2: Run Locally

1. Clone this repository and download the dataset from https://alabama.app.box.com/s/vnwa6b4qi42ts39exv8jej6vzabdu78k.
2. Install dependencies: pip install -r requirements.txt

## ✅ Testing

- Tested on Kaggle using the sample video: `Experimenter_CREW_999_1_All_1731617801.mp4`
- Transcription and sentiment analysis were verified manually.
- Visual plots confirmed accurate timestamp bucketing and sentiment counts.


## 📌 Notes

- Audio segmentation ensures each chunk is ≤ 5 seconds.
- Sentiment is derived from transcribed text, not tone.
- No external/proprietary API is used, only open-source models.
