# SHODAN Remake Piper voice model

This folder contains a Piper TTS voice model for SHODAN from the *System Shock
Remake* (Nightdive Studios, 2023).

## Files

| File | Purpose |
|---|---|
| `en_US-shodan_remake-medium.onnx` | Model weights |
| `en_US-shodan_remake-medium.onnx.json` | Piper voice configuration |

Model settings:

- Sample rate: 22,050 Hz
- Quality: medium
- Language: `en_US`
- eSpeak voice: `en-us`
- Speakers: 1

## Install

```bash
mkdir -p ~/piper/voices/shodan
cd ~/piper/voices/shodan
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/shodan_remake/en_US-shodan_remake-medium.onnx
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/shodan_remake/en_US-shodan_remake-medium.onnx.json
```

## Usage

```bash
echo "Look at you, hacker." | piper \
  --model ~/piper/voices/shodan/en_US-shodan_remake-medium.onnx \
  --output_file shodan.wav
```

## Credits and legal

SHODAN and *System Shock* are properties of Nightdive Studios. This is a
fan-made voice model. All rights to the source material belong to the relevant
rights holders.
