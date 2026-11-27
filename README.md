<img width="1919" height="1127" alt="screenshot" src="https://github.com/user-attachments/assets/4008c372-9565-4c9a-9259-d470c7fc1e7a" />
# PedalBoard α1

**Virtual pedalboard for Windows 10/11** — audio interface input → effects → output.
Granular, delay, reverb, pitch + filter, a VST slot and a looper, all locked to the tempo of the music.

By **8OHMEGA** · co-authored with Claude · [ohmega.live](https://www.ohmega.live)

> ⚠️ **Alpha.** Expect bugs. Tempo (BPM) detection is still being tuned.

---

## Download & run

1. Go to [**Releases**](../../releases/latest) and download `PedalBoard-a1-win64.zip`.
2. Unzip it anywhere and run **`PedalBoard.exe`**.
   It is a single file: no installer, no extra libraries (the runtime is built in).

**Windows SmartScreen** may show *"Windows protected your PC"* on first launch, because the app is not code-signed.
Click **More info → Run anyway**.

**Audio interface:** an ASIO driver is recommended (RME, Steinberg, Focusrite, etc.).
Without ASIO the app runs through WASAPI, with higher latency.

## First setup

1. Top bar → **audio settings**: choose the driver (ASIO), inputs and outputs.
2. A buffer of **64–128 samples** is a good balance between latency and stability.
3. Send a signal to the input and switch modules on with their **ON** buttons.

## Signal chain (default)

```
GRANULAR → DELAY → REVERB → PITCH+FILTER → VST → LOOPER → MASTER MIX
```

The order of modules can be changed in **ARRANGE**.

## Modules

### GRANULAR
- **PAD / ARP / ECHO / DRIFT** — mode. **HOLD** — freeze the buffer.
- **OCT / 5TH / OCT+/-** — grain intervals. **BASS MONO** — mono below 150 Hz.
- **Buffer window:** tap to set **POSITION** (where grains are taken from).
- **HEIGHT, GRAINS, SIZE, JITTER, REVERSE, SPREAD, FEEDBACK, MIX** — main controls.
- **SHAPE** — grain envelope, from soft to sharp attack.
- **MAGNET** — pulls grains toward hits in the buffer (tighter rhythm).
- **EVEN** — evens out grain loudness.
- **REACT** — adds grains on every kick.

### TEMPO
- **AUTO** — tempo is detected from the track's kick; beat lamps blink on the beat.
- **TAP** — tap the tempo; the first tap is beat 1. Tapping at a different tempo starts a new track.
- **BPM RANGE** — range for tempo detection.
- Effects with **TEMPO SYNC** (delay, looper, pads) follow the beat.

### LOOPER
- **REC** — record; press again to close the loop. **QUANT** — start on the beat.
- **CAPTURE** — make a loop from the last bars.
- **Pads** — momentary beat-repeat.

### VST
One slot for a VST plugin (its editor opens as a page or in a separate window).

### Presets, MIDI, skins
- Presets are saved from the top bar.
- **MIDI learn** works for any knob.
- Skins: **MODERN / VINTAGE / OHMG** (SKIN page).

## Files

Settings and the tempo log live in `%APPDATA%\MicroPedalBoard\`.

- `bpm_log.txt` — if the BPM was detected wrong, please send this file along with your report.
- Optional: put a `logo_ohmega.png` next to the exe to show your own logo in the header.

## Known limitations (alpha)

- BPM can drift on tracks with broken-beat kicks and may not lock during intros without a kick (use **TAP**).
- One VST slot only.
- The looper's loop is not saved in presets.
- No Ableton Link yet.

## Feedback

Found a bug or have an idea? Open an [issue](../../issues) or write to **info@ohmega.live**.
