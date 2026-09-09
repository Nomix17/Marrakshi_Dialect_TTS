# Audio Treatment Pipeline

Google Colab workflow designed to clean audio streams and separate speakers[cite: 1].

## Pipeline Workflow

* **Download audio:** Fetches audio from a YouTube source and converts it into a high-quality WAV file using `yt-dlp`[cite: 1].
* **Map silence:** Scans the audio file for inactive intervals and records their timestamps using `inaSpeechSegmenter`[cite: 1].
* **Remove silence:** Strips out all detected silent blocks using `ffmpeg` filters[cite: 1].
* **Speaker recognition:** Uses Pyannote's AI diarization pipeline with GPU acceleration to identify and track different speakers[cite: 1].
* **Slice audio:** Parses speaker timestamps to isolate and export separate clean audio files for each unique voice to Google Drive[cite: 1].

## Chatterbox Tuning

Google Colab workflow designed to standrize audio and fine-tune [Chatterbox TTS](https://github.com/gokhaneraslan/chatterbox-finetuning) to produce a Moroccan Darija voice.

* **Prepare dataset:** Loads the processed audio and transcripts from Drive, converts clips to 16kHz mono, and builds the training metadata.
* **Configure & train:** Sets up the fine-tuning config (LoRA, turbo mode) and runs `train.py` on the prepared dataset.
* **Test:** Generates a short sample sentence in Darija with the fine-tuned model to check voice quality.
