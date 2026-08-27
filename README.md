# Audio Treatment Pipeline

A brief automated Google Colab workflow designed to clean audio streams and separate speakers[cite: 1].

## Pipeline Workflow

* **Download audio:** Fetches audio from a YouTube source and converts it into a high-quality WAV file using `yt-dlp`[cite: 1].
* **Map silence:** Scans the audio file for inactive intervals and records their timestamps using `inaSpeechSegmenter`[cite: 1].
* **Remove silence:** Strips out all detected silent blocks using `ffmpeg` filters[cite: 1].
* **Speaker recognition:** Uses Pyannote's AI diarization pipeline with GPU acceleration to identify and track different speakers[cite: 1].
* **Slice audio:** Parses speaker timestamps to isolate and export separate clean audio files for each unique voice to Google Drive[cite: 1].
