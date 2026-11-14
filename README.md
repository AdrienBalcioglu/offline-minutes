# Offline Minutes

Record a meeting, transcribe it on your own computer, and write the minutes next to the transcript.

**[Website](https://adrienbalcioglu.github.io/offline-minutes/about.html)** · **[Open the app](https://adrienbalcioglu.github.io/offline-minutes/)**

## Features

- Record from the microphone, or transcribe an audio file you already have
- Transcription runs on your device: the audio is never uploaded
- Minutes template: decisions, actions with owner and due date, open questions
- Export as Markdown, or print to PDF

## Usage

Use the live demo, or serve the folder locally (the microphone needs `https` or `localhost`):

```bash
python3 -m http.server 8000
```

## How the local transcription works

- Speech is transcribed by [Whisper](https://github.com/openai/whisper), running in your browser through [Transformers.js](https://github.com/huggingface/transformers.js) and WebAssembly.
- **Your audio never leaves the computer.** There is no API key and no server.
- The speech model is downloaded once from Hugging Face, then kept in the browser cache: 41 MB (fast), 77 MB (balanced) or 249 MB (most accurate).
- The recording itself is not stored. Only the text is kept, in the browser's local storage.

The model makes mistakes, mostly on names and figures. Read the text before you rely on it.

The model does not tell speakers apart. Ask the people in the room before you record.

## Stack

A single HTML file. Whisper through Transformers.js, loaded from a CDN at a pinned version.

## License

[MIT](LICENSE) © 2026 Adrien Balcioglu
