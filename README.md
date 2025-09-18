# Hindi Matra Tuner

Hindi Matra Tuner is an interactive single-page tool that helps learners move between
Hinglish (Latin script) and Hindi (Devanagari) while exploring how matras change the
sound of a base consonant. It bundles a matra "piano", transliteration helpers, and a
word deconstructor with speech synthesis so learners can hear and practice individual
syllables.

## Features

- **Matra piano** – Pick any Hindi consonant, then click or hover across matra keys to
  hear the resulting syllable via the browser's speech synthesis engine.
- **Google Transliteration support** – Type Latin characters in the textarea and press
  <kbd>Ctrl</kbd>+<kbd>G</kbd> (or hit the space bar) to toggle Google Transliteration
  between Hinglish and Hindi scripts.
- **Speech input** – Record Hinglish or Hindi using the built-in microphone controls.
  Recognized Hinglish is auto-converted to Devanagari with Sanscript so it feeds
  directly into the analyser.
- **Word deconstructor** – Break any word or sentence into syllables, highlight the
  matras that appear, and replay individual syllables or the full sequence at
  different speeds.

## Quick start

1. Clone the repository.
2. Open `index.html` in a modern browser (Chrome works best for speech recognition).
3. Allow microphone access if you plan to use the speech input controls.

Because every dependency is loaded from a CDN, no build step is required. If you prefer
running a lightweight development server, you can use Python:

```bash
python -m http.server 8000
```

Then open <http://localhost:8000/index.html>.

## Usage tips

- Click **Start Speaking** to begin recording. Use the dropdown to switch between
  `hi-IN` (Hindi) and `en-IN` (Hinglish) recognition. Hinglish transcripts are passed
  through Sanscript before being analysed.
- The "Latin Input" display shows the raw transcript that arrived from speech
  recognition. The "Hindi" display mirrors the transliterated text that will be sent to
  the deconstructor.
- In the Word Deconstructor, press **Analyze** or hit **Enter** to refresh syllables.
  Use the **Play All** button to hear each syllable sequentially; adjust playback speed
  with the radio controls.
- Hover previews for matras can be toggled with the checkbox next to the consonant
  selector in the matra piano.

## Browser support notes

- Speech recognition relies on the Web Speech API, which is currently supported in
  Chromium-based browsers. When unsupported (or when microphone permission is denied),
  the app will display an inline warning.
- Speech synthesis (`speechSynthesis`) is used for matra and syllable playback. Ensure
  your browser has the Hindi voice pack installed for best pronunciation quality.

## Contributing

If you spot a bug or have an enhancement idea, feel free to open an issue or submit a
pull request. When contributing code, please keep the interface self-contained so it
remains easy to open via `index.html` without a build pipeline.
