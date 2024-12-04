# Transcript Model for Hockey Match Commentary

## 1. Overview
### Purpose
  * The Transcript Model is designed to transcribe spoken words from live-streamed hockey matches into text, complete with timestamps for each segment. The model integrates OpenAI’s Whisper model, a state-of-the-art speech-to-text tool, to convert the commentary and other spoken elements of the match into textual form, enabling deeper analysis and keyword extraction.
  * This model is ideal for live sports broadcasting, allowing the transcription of commentary to be stored, reviewed, and analyzed in real time. The system is implemented using Python and leverages various libraries to manage data collection, audio processing, transcription, and keyword extraction.

# DEMO FOR VIDEO TRANSCRIPTION:
https://github.com/user-attachments/assets/e045d12b-1785-48f2-aec4-fbce196a0c0c

### Key Features
  * Real-time Speech-to-Text Conversion: Transcribes live match commentary into text.
  * Timestamped Segments: Each transcribed segment includes a timestamp, enabling accurate synchronization with match events.
  * Keyword Extraction: Detects dynamic hockey-related keywords from the transcription for further analysis.
  * Whisper Model Integration: Utilizes the Whisper model for transcription, ensuring high-quality, multi-language support.
  * Customizable Keyword Detection: Provides a mechanism to add custom keywords for each match, which can be dynamically detected from the transcription.
## 2. System Architecture
The system is built on a Python-based pipeline using the following technologies:

  * Whisper: An automatic speech recognition (ASR) model by OpenAI that transcribes audio into text.
  * Pydub: A Python library for audio file manipulation, used for converting video streams into audio.
  * Fuzzywuzzy: A library used for fuzzy matching of keywords within the transcribed text.
  * MySQL: A relational database to store match data, keywords, and transcriptions.
### Data Flow
  * Audio Data Collection: Live-stream audio is fetched from the video stream of the match.
  * Audio Processing: The audio is converted into a suitable format for transcription using Pydub.
  * Transcription: The Whisper model transcribes the audio data into text, breaking it into segments with timestamps.
  * Keyword Extraction: Hockey-related keywords are identified and extracted using fuzzy matching.
  * Data Storage: Transcriptions, timestamps, and detected keywords are stored in the database for review and analysis.
## 3. Model Components
### (i). Audio Stream Handling
  * The model accepts audio data from live-streamed video. The audio is processed by Pydub, which ensures it is in the correct format (e.g., 16kHz mono) for transcription.
  * This component ensures the system can handle live broadcasts with minimal delay.
### (ii). Whisper Model Integration
  * Whisper is used to transcribe the audio into text. It can handle a variety of languages and is robust enough to deal with noisy environments like live sports commentary.
  * The transcription is returned in segments, each with a start time and corresponding text, ensuring the output can be mapped to specific events in the match.
### (iii). Timestamped Transcription
  * Each transcription segment is paired with a timestamp in the mm:ss format. This allows the text to be synced with the actual video and makes it easier to analyze specific moments in the match.
### (iv). Keyword Detection
  * The transcribed text is analyzed for hockey-specific keywords (such as player names, actions, and match terminology). This is done using fuzzy string matching, which ensures that even if the commentary varies slightly, relevant keywords are still detected.
  * Custom keywords can be added for each match to fine-tune the detection to specific needs (e.g., tracking team names, specific players, or tactics).
### (v). Data Storage and Review
  * The transcriptions and detected keywords are stored in a MySQL database. This allows for easy retrieval and analysis. Each match is linked to its transcription and the keywords detected during commentary.
  * Users can query specific matches and review the transcription for keyword highlights.
## 4. Workflow Overview
  * Fetch Audio Stream: The model starts by accessing the live-stream match's audio data. This could be a video file or a live stream URL.
  * Audio Conversion: The audio is converted into a suitable format using Pydub (if necessary).
  * Run Whisper Transcription: The Whisper model transcribes the audio, segmenting it into chunks and providing text along with timestamps.
  * Dynamic Keyword Extraction: The transcription text is processed to detect predefined keywords (both custom and default).
  * Store Data: Transcribed text, timestamps, and detected keywords are stored in a database for future retrieval and analysis.
  * Review and Analysis: Users can review the transcriptions and search for specific keywords to analyze the match commentary.
## 5. Database Schema
The model uses MySQL to store the following key data:

  * match_details: Contains match metadata (e.g., MATCH_ID, MATCH_NAME, STREAM_URL).
  * transcriptions: Stores transcription segments with timestamps, including the transcribed text (segment_id, match_id, start_time, end_time, text).
  * keywords_detected: Stores detected keywords for each transcription segment (segment_id, keyword, match_id).
## 6. Keyword Management
### Custom Keywords
  * Custom keywords are specific to each match and are added by the user through the application interface.
  * These keywords could relate to specific players, teams, or match events (e.g., "goal", "penalty", "goalkeeper save").
### Dynamic Keyword Extraction
  * The transcribed text is checked against a list of predefined and custom keywords. Fuzzy matching is used to account for variations in how keywords might be mentioned in commentary.
## 7. Use Cases
  * Match Commentary Analysis: Enables sports analysts to track specific moments or players in the commentary in real time.
  * Keyword-based Filtering: Helps in identifying key events during a match based on keywords (e.g., tracking all mentions of a player or goal).
  * Fan Engagement: Provides fans with a textual summary of important match moments that can be used for social media posts or live commentary updates.
## 8. Future Enhancements
  * Multi-Language Support: Expand the model's capabilities to transcribe and analyze commentary in multiple languages.
  * Real-Time Feedback: Implement real-time streaming analysis for live broadcasts, allowing immediate keyword detection and transcription updates.
  * Sentiment Analysis: Integrate sentiment analysis to gauge the tone of commentary, such as excitement or disappointment.
## 9. Conclusion
The Transcript Model for hockey match commentary provides a sophisticated, real-time transcription solution with timestamped accuracy. By leveraging Whisper's advanced transcription capabilities and combining it with dynamic keyword detection, the model enables deeper insights into live broadcasts. It is a powerful tool for analysts, broadcasters, and fans alike, enabling efficient review and engagement with the game.







