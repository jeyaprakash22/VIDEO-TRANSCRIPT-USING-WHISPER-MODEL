# VIDEO-TRANSCRIPT-USING-WHISPER-MODEL

# Transcript Model for Match Commentary

## DEMO

https://github.com/Karthick-ng/PROJECT-3-POWERBI-TABLEAU/blob/51fef499803c8afed84150d7742b6ac55dccbae0/1.POWERBI/DEMO_VIRAT.mp4

## Overview
The Transcript Model is designed to convert spoken words (match commentary) into text with precise timestamps. The model integrates the Whisper model, an automatic speech recognition (ASR) system, to transcribe commentary in real-time.

The goal is to capture the spoken commentary of a match, converting it into structured text with timestamps, providing an accurate, searchable, and useful representation of the game as it progresses.

## Technologies Used:
- **Python**: For developing and implementing the transcript model.
- **Whisper Model**: OpenAI's Whisper ASR model, integrated to convert spoken words into text.
- **Timestamping**: For capturing the exact time of each spoken word or sentence in the commentary.

## Features:
- **Real-Time Transcription**: Converts spoken commentary into text as the match progresses.
- **Timestamps**: Each transcribed text segment is tagged with a timestamp, maintaining a precise record of when each part of the commentary occurs.
- **Match Commentary Capture**: Designed specifically for capturing match commentary, making it easy to review and analyze the play-by-play commentary.

## Installation and Setup:
1. Clone the repository: `git clone <repo_url>`
2. Set up the Python environment:
   - `pip install -r requirements.txt`
3. Integrate the Whisper model into your project as described in the documentation.
4. Run the script to start transcribing audio from live commentary.

## Example Use Case:
- During a live match, the model captures spoken commentary, transcribes it into text, and saves the output with timestamps. This data can be analyzed for insights or used to display live text commentary on a website or app.

## Future Enhancements:
- Add language support for multiple languages.
- Implement a UI for users to view the transcription in real-time.


## DEMO:
https://drive.google.com/file/d/1WiGGDxnfNpR0JEvdqrLezi8dNg47K3sm/view
