# MPC — Beat Studio

A browser-based, Akai-MPC-style beat machine. The entire app is a **single self-contained
HTML file** (`index.html`) — all markup, CSS, and JavaScript inline. Every drum/synth sound
is generated live with the **Web Audio API**, so no sample files are needed for the pads.

The only external asset is the optional backing loop, **`intrumental_final.wav`**, which the
app auto-loads next to the HTML and binds to the **Instrument** pad (key `Z`) in the DRUMS kit.

## Run locally

This is a static app — no build step. It must be served over **HTTP** (not opened as a
`file://` path) so the browser can load the `.wav` and decode audio cleanly.

```bash
# from this folder:
python -m http.server 5500
```

Then open: **http://localhost:5500/**

Equivalent npm scripts (same thing):

```bash
npm start          # python -m http.server 5500
npm run serve:node # npx serve -l 5500   (Node alternative)
```

## Files

| File                     | Responsibility                                            |
| ------------------------ | --------------------------------------------------------- |
| `index.html`             | The whole app — UI (CSS), logic (JS), audio engine        |
| `intrumental_final.wav`  | Optional backing loop auto-loaded onto the Instrument pad |
| `package.json`           | Dev-server scripts                                        |

## Controls

- **Kits:** DRUMS · KEYS · BASS · FX · SAMPLE
- **Keyboard:** `Q W E R / A S D F / Z X C V / 1 2 3 4` map to the 16 pads
- **Z (Instrument pad, DRUMS):** toggles the backing loop on/off
- **SAMPLE kit:** drop an audio file to chop it across all 16 pads
