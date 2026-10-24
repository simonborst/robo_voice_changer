# Robot Voice

A robot voice changer that runs in the browser. Built for iPhone Safari, and it works in any modern browser. It has three modes:

- **Record & replay** (default): tap **Record**, say something, tap **Stop**. It plays back as a robot on a loop, and you can move the faders while it plays. **Save** exports the robot version as a WAV file. Works on the phone speaker with no feedback.
- **Repeat**: repeat-after-me. Tap **Start** and it listens. Levels are averaged over the last half second so the bounce of a voice is ignored. When the average goes above the **Start level**, it records from the moment your voice crossed it; once it has stayed under the **Silence level** for the **Silence wait** (1 second by default), it plays the line back once as a robot, then listens again. Playback can't be interrupted by talking, and the mic is off while it plays, so it never repeats itself. A live meter shows your level against both thresholds so you can tune them for your room. Turn on **Loop** to keep repeating a line until you tap **Listen**.
- **Live**: tap **Start** and talk; your voice comes back as a robot in real time. Use headphones.

Every recording becomes a numbered **take** with its own colour. The display stays pinned at the top of the screen and shows the waveform growing while you record, then a playhead moving across it while it plays or loops. Take numbers reset when you reopen the app. A one-shot playback can't be interrupted; turn on Loop if you want to be able to stop it.

**Live page:** https://simonborst.github.io/robo_voice_changer/

## Controls

**Voice**

| Control | What it does |
| --- | --- |
| Natural / Monotone / Snap / Parrot / Mock | Natural keeps your own voice. Monotone re-sings your words on one steady note. Snap follows your pitch and snaps it to a few robot-style notes. Parrot raises your voice about an octave and a half with a raspy warble and a tiny, nasal beak, and gives one parrot squawk before and one after each playback. |
| Mock | Replaces your words with "meh meh meh", one per syllable. It keeps your real voice, pitch and expression and only changes the mouth shape to "m…eh", so nothing is auto-tuned. Short gaps from consonants inside a syllable are filled so each meh stays whole. |
| Note / Key | The note for Monotone, or the key for Snap. |
| Root / Fifth / Major / Minor | Which notes Snap may use: one note in octaves, a two-note "beep-boop", or a three-note chord. |
| Note hold | How long Snap stays on a note before it may jump (default 250 ms). |
| Tone | Warm to bright. |
| Robot size | Shifts the voice's resonances: bigger robot or smaller robot, without changing the note. |
| Solo / + Octave / + Fifth | Adds a second robot voice an octave or a fifth below. |

**Effects:** Metal box (short metallic resonance), Playback speed (40–150%; the robot keeps its pitch and voice size when slowed), Robot mix (blend with your normal voice), Volume.

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
