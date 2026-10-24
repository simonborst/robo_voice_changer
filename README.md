# Robot Voice

A robot voice changer that runs in the browser. Built for iPhone Safari, and it works in any modern browser. It has two modes:

- **Record & replay** (default): tap **Record**, say something, tap **Stop**. It plays back as a robot on a loop, and you can move the faders while it plays. **Save** exports the robot version as a WAV file. Works on the phone speaker with no feedback.
- **Live**: tap **Start** and talk; your voice comes back as a robot in real time. Use headphones.

**Live page:** https://simonborst.github.io/robo_voice_changer/

## Controls

**Voice**

| Control | What it does |
| --- | --- |
| Natural / Monotone / Snap | Natural keeps your own voice. Monotone re-sings your words on one steady note. Snap follows your pitch and snaps it to the nearest note in a key, like hard auto-tune. |
| Note / Key | The note for Monotone, or the key for Snap (with Chromatic, Major or Minor). |
| Tone | Warm to bright. |
| Robot size | Shifts the voice's resonances: bigger robot or smaller robot, without changing the note. |
| Solo / + Octave / + Fifth | Adds a second robot voice an octave or a fifth below. |

**Effects:** Metal box (short metallic resonance), Robot mix (blend with your normal voice), Volume.

**Ring modulator** (off by default): Amount, Speed, Grit, and Smooth / Buzzy / Harsh waveform. This is the classic sci-fi ring-mod sound and adds buzz.

### How Monotone and Snap work

An AudioWorklet measures the shape of your voice's spectrum (the vowel and consonant resonances) 187 times a second using a cepstrum, then rebuilds the voice from smooth pulses at the target pitch. Your words keep their shape but the pitch becomes perfectly steady. Hiss-like consonants pass through so speech stays clear.

Settings are remembered on your device.

## Using it on iPhone

1. Open the live page in Safari, tap **Record** (or **Start** in Live mode), and allow the microphone.
2. In Live mode, use headphones. Without them, the speaker feeds back into the mic.
3. Keep the page on screen. It keeps the display awake while running, but iOS stops the microphone if you lock the phone or switch apps.
4. Optional: Share → **Add to Home Screen** to launch it like an app.

The microphone only works on an `https://` page, which is why it is hosted here rather than opened as a local file.

## Privacy

All audio processing happens on your device with the Web Audio API. Recordings stay in memory on your phone until you leave the page or save them yourself. Nothing is uploaded.

## Hosting

This is a single static file (`index.html`) served by GitHub Pages from the `main` branch root. `.nojekyll` tells Pages to serve files as-is.

## License

Code released under the [MIT License](LICENSE).

Third-party resources: the page loads the fonts [Chakra Petch](https://fonts.google.com/specimen/Chakra+Petch) and [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) from Google Fonts at runtime. Both are licensed under the SIL Open Font License 1.1 and are not included in this repository. No other libraries are used.
