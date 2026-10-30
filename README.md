# Motion Partials

Play additive synthesis with your body. Each partial (sine wave) gets a zone of the camera picture, and how much you move in that zone sets how loud it is. An adjustable cycle timer records your movement and loops it, and instrument presets reshape the partials' frequencies and amplitudes.

**Live app:** https://viela-la.github.io/motion-partials/

## Features

- **Partials** — type frequencies and max amplitudes, add a harmonic series, or add non-harmonic sets: random frequencies, a stretched (piano-like) series, free-bar / bell ratios, or golden-ratio steps. Up to 24 partials.
- **Motion control** — the camera image is split into one zone per partial. More movement in a zone means a louder partial. Adjustable sensitivity, threshold and release. Without a camera, moving the mouse over the stage works too.
- **Control modes** — each partial in its own zone, all partials following total motion, or one partial at a time (step through with the arrow keys or number keys).
- **Cycle timer** — 0.5 to 30 s. Live mode draws one cycle and starts over; Record & loop captures your movement for one cycle and replays it. In one-at-a-time mode it layers one partial per cycle.
- **Timbre presets** — 16 instruments (pure tone, square, sawtooth, flute, clarinet, oboe, trumpet, violin, piano, organ, church bell, marimba, glockenspiel, gong, voice "ah" and "ee"). Partials glide to the preset; a morph slider, or your movement, blends between before and after. Fundamental, brightness and stretch controls.
- **Plots** — the cycle's waveform envelope with one strip per partial, the waveform right now, and a spectrum comparing your partials with the preset.

## Running it

It is a single HTML file with no build step and no dependencies.

- Open `index.html` in Chrome, or
- Visit the GitHub Pages link above.

The camera needs a secure page (`https://` or a local file) and your permission. Video stays in your browser; nothing is uploaded.

## How it works

Each partial is a Web Audio sine oscillator with its own gain. The camera frame is shrunk to 64×48 pixels and compared with the previous frame; the share of changed pixels in each zone becomes that partial's level, smoothed with a fast attack and adjustable release. Presets define a frequency ratio and amplitude for each partial, and partials are matched to the preset by pitch rank so each keeps its zone.
