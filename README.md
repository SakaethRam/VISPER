# VISPER - Context-Aware Audio Transcription System

VISPER is an intelligent audio transcription tool that combines OpenAI's Whisper model with signal processing using Librosa to produce detailed and context-enriched transcripts. It transcribes speech from audio files and identifies musical or silent segments based on audio signal analysis.

---

![VISPER AI](https://github.com/user-attachments/assets/3bc52e9c-5291-4358-829d-f19970701e3a)

---

## Features

- Automated speech transcription using Whisper.
- Audio signal analysis with Librosa for tempo and beat tracking.
- Context tagging for [Chorus], [OST], and silent regions.
- Timestamped segment-wise transcription.
- Energy-based background audio detection.

---

## Project Structure

```
├── VISPER - Transcription Model (Whisper).ipynb
├── requirements.txt
├── Dockerfile
└── README.md
```

---

## Installation (Local)

1. **Clone the Repository**
```bash
git clone "https://github.com/SakaethRam/VISPER.git"
cd VISPER
```

2. **Install Dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the Notebook**
Open the notebook using Jupyter:
```bash
jupyter notebook
```

---

## Running with Docker

### Build the Docker image
```bash
docker build -t visper .
```

### Run the container
```bash
docker run -p 8888:8888 visper
```

Then open the link provided in your terminal (e.g., `http://127.0.0.1:8888/?token=...`) to access the Jupyter notebooks in your browser.

---

## Requirements

- Python 3.8+
- OpenAI Whisper
- Librosa
- NumPy
- IPython
- Google Colab (for notebook usage)

Make sure to have a `requirements.txt` with the following:

```
openai-whisper
librosa
numpy
ipython
jupyter
```

### Dockerfile

```dockerfile
# Use an official Python image
FROM python:3.10-slim

# Set working directory
WORKDIR /app

# Copy project files
COPY . /app

# Install system packages
RUN apt-get update && apt-get install -y git ffmpeg && \
    rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose Jupyter port
EXPOSE 8888

# Launch Jupyter
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]
```

---

## Contribution Guidelines

Contributions are welcome. To contribute:
1. Fork the repository.
2. Create a feature branch.
3. Implement your changes.
4. Submit a pull request with a clear explanation of the modifications.

---

## License

MIT License

---

Built by `S A M` – Combining language understanding with audio intelligence.

