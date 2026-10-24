# Robot Voice

A live robot voice changer that runs in the browser. Open it, tap **Start**, and talk: your voice comes back out sounding robotic, in real time. Built for iPhone Safari, and it works in any modern browser.

**Live page:** https://simonborst.github.io/robo_voice_changer/

## Controls

| Fader | What it does |
| --- | --- |
| Robot tone | Frequency of the ring modulator (10–400 Hz). Low values sound like a classic sci-fi robot, high values like a buzzy droid. |
| Metallic | Amount of the short, resonant echo that gives the tinny, metal-box ring. |
| Grit | Soft distortion. |
| Robot mix | Balance between your normal voice and the robot voice. |
| Volume | Output level. |

The **Smooth / Buzzy / Harsh** buttons switch the modulator's waveform. Settings are remembered on your device.

## Using it on iPhone

1. Open the live page in Safari, tap **Start**, and allow the microphone.
2. Use headphones. Without them, the speaker feeds back into the mic.
3. Keep the page on screen. It keeps the display awake while running, but iOS stops the microphone if you lock the phone or switch apps.
4. Optional: Share → **Add to Home Screen** to launch it like an app.

The microphone only works on an `https://` page, which is why it is hosted here rather than opened as a local file.

## Privacy

All audio processing happens on your device with the Web Audio API. Nothing is recorded, stored or uploaded.

## Hosting

This is a single static file (`index.html`) served by GitHub Pages from the `main` branch root. `.nojekyll` tells Pages to serve files as-is.

## License

Code released under the [MIT License](LICENSE).

Third-party resources: the page loads the fonts [Chakra Petch](https://fonts.google.com/specimen/Chakra+Petch) and [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) from Google Fonts at runtime. Both are licensed under the SIL Open Font License 1.1 and are not included in this repository. No other libraries are used.
