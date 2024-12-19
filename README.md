
# Whisper Audio Transcription and Summarization

This project demonstrates how to transcribe audio using OpenAI's Whisper model and summarize the transcription using Hugging Face's Longformer Encoder-Decoder (LED) model. It also includes steps to clean repetitive text and save the results in a structured format.

## Features
- **Audio Transcription:** Converts speech in an audio file into text using the Whisper model.
- **Text Summarization:** Summarizes the transcribed text using the LED model.
- **Repetition Removal:** Cleans the transcript by removing repetitive phrases.
- **Output Storage:** Saves the transcript and summary to a CSV file.

## Requirements
- Google Colab (or a Python environment)
- Python 3.8+
- Installed packages:
  - `openai-whisper`
  - `transformers`
  - `gdown`
  - `pandas`

## Installation
Run the following commands to install the necessary libraries:

```bash
pip install openai-whisper
pip install transformers
pip install gdown
pip install pandas
```

## How to Use
1. **Setup Environment:**
   - Use Google Colab for seamless execution or set up a local Python environment with the required libraries.

2. **Mount Google Drive:**
   - (Optional) Mount Google Drive to access or save files.

3. **Download Audio File:**
   - Replace the `file_id` with the ID of the desired Google Drive audio file.
   - The script uses `gdown` to download the audio file.

4. **Transcribe Audio:**
   - Whisper processes the audio file to generate a transcription.

5. **Summarize Text:**
   - The transcription is chunked and summarized using the LED model.

6. **Save Results:**
   - Transcriptions and summaries are saved to a CSV file.

## Example Usage
### Audio File
- The script processes an audio file located on Google Drive.

### Transcription
- The Whisper model converts speech to text.

### Summarization
- The LED model summarizes the text into concise information.

### Output
The transcript and summary are saved to `audio_summary.csv`.

## Code
Here's an overview of the process:

1. **Install Dependencies:**
   ```python
   !pip install openai-whisper transformers gdown pandas
   ```

2. **Import Libraries:**
   ```python
   import whisper
   from transformers import LEDTokenizer, LEDForConditionalGeneration
   import gdown
   import pandas as pd
   ```

3. **Mount Drive and Download Audio:**
   ```python
   drive.mount('/content/drive')
   file_id = 'YOUR_FILE_ID'
   gdown.download(f'https://drive.google.com/uc?id={file_id}', '/content/audio.mp3', quiet=False)
   ```

4. **Process Audio:**
   - Transcribe and summarize using Whisper and LED.

5. **Save Results:**
   ```python
   df.to_csv("/content/audio_summary.csv", index=False)
   ```

## File Structure
```
.
├── README.md
├── audio_summary.csv
└── whisper_audio.mp3
```

## Output
The output CSV contains:
- **Title:** The audio file name.
- **Text:** The cleaned transcript.
- **Summary:** The summarized text.

## Acknowledgements
- [OpenAI Whisper](https://github.com/openai/whisper) for transcription.
- [Hugging Face Transformers](https://huggingface.co/transformers) for summarization.

