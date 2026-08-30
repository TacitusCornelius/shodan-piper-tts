# shodan-piper-tts

A [Piper](https://github.com/rhasspy/piper) TTS voice model of **SHODAN**, the
malevolent AI of *System Shock*. Trained on clips from the **System Shock
Remake** (Nightdive Studios, 2023).

## Files

| File | Purpose |
|------|---------|
| `en_US-shodan_remake_v2_9689-medium.onnx` | Model weights |
| `en_US-shodan_remake_v2_9689-medium.onnx.json` | Voice config (phoneme map, sample rate, inference params) |

- Sample rate: 22050 Hz (medium quality)
- Language: `en_US`

## Install

Download both files into a Piper voices directory:

```bash
mkdir -p ~/piper/voices && cd ~/piper/voices
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/en_US-shodan_remake_v2_9689-medium.onnx
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/en_US-shodan_remake_v2_9689-medium.onnx.json
```

## Usage

```bash
echo "Look at you, hacker." | piper \
  --model ~/piper/voices/en_US-shodan_remake_v2_9689-medium.onnx \
  --output_file shodan.wav
```

Or with the Python API:

```python
from piper import PiperVoice

voice = PiperVoice.load(
    "~/piper/voices/en_US-shodan_remake_v2_9689-medium.onnx",
    config_path="~/piper/voices/en_US-shodan_remake_v2_9689-medium.onnx.json",
)
with wave.open("shodan.wav", "wb") as f:
    voice.synthesize("The machine is awake.", f)
```

## Xerxes voice model

The repository also contains a Xerxes voice model from *System Shock 2*:

| Folder | Contents |
|---|---|
| [`xerxes_v14_200k/`](./xerxes_v14_200k/) | `en_US-xerxes-medium.onnx` and its `.onnx.json` configuration |

Download both files with:

```bash
mkdir -p ~/piper/voices/xerxes && cd ~/piper/voices/xerxes
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/xerxes_v14_200k/en_US-xerxes-medium.onnx
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/xerxes_v14_200k/en_US-xerxes-medium.onnx.json
```

Use it with:

```bash
echo "The containment protocol remains active." | piper \
  --model ~/piper/voices/xerxes/en_US-xerxes-medium.onnx \
  --output_file xerxes.wav
```

## Training provenance

Trained with [TextyMcSpeechy](https://github.com/daswer123/textyspeechy)'s
`tts_dojo` pipeline on a dataset of System Shock (2023 Remake) dialogue clips
(9,689 training steps).

## Credits & legal

SHODAN and System Shock are properties of Nightdive Studios. This is a
fan-made voice model for personal / non-commercial use. All rights to the
source material belong to their respective owners.
