# shodan-piper-tts

A collection of [Piper](https://github.com/rhasspy/piper) TTS voice models for
characters from the *System Shock* series.

## Voices

| Folder | Voice | Source |
|---|---|---|
| [`shodan_remake_v2/`](./shodan_remake_v2/) | SHODAN | *System Shock Remake* (2023) |
| [`Xerxes_medium/`](./Xerxes_medium/) | Xerxes | *System Shock 2* |

## SHODAN Remake voice model

The SHODAN model files are in [`shodan_remake_v2/`](./shodan_remake_v2/):

```text
en_US-shodan_remake_v2_9689-medium.onnx
en_US-shodan_remake_v2_9689-medium.onnx.json
```

Download both files into a Piper voices directory:

```bash
mkdir -p ~/piper/voices/shodan && cd ~/piper/voices/shodan
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/shodan_remake_v2/en_US-shodan_remake_v2_9689-medium.onnx
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/shodan_remake_v2/en_US-shodan_remake_v2_9689-medium.onnx.json
```

Use it with:

```bash
echo "Look at you, hacker." | piper \
  --model ~/piper/voices/shodan/en_US-shodan_remake_v2_9689-medium.onnx \
  --output_file shodan.wav
```

## Xerxes voice model

The Xerxes model files are in [`Xerxes_medium/`](./Xerxes_medium/):

```text
en_US-xerxes-medium.onnx
en_US-xerxes-medium.onnx.json
```

Download both files with:

```bash
mkdir -p ~/piper/voices/xerxes && cd ~/piper/voices/xerxes
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/Xerxes_medium/en_US-xerxes-medium.onnx
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/Xerxes_medium/en_US-xerxes-medium.onnx.json
```

Use it with:

```bash
echo "The containment protocol remains active." | piper \
  --model ~/piper/voices/xerxes/en_US-xerxes-medium.onnx \
  --output_file xerxes.wav
```

## Training provenance

The SHODAN model was trained with [TextyMcSpeechy](https://github.com/daswer123/textyspeechy)'s
`tts_dojo` pipeline on *System Shock Remake* dialogue clips.

The Xerxes model was trained with the same pipeline on an approved *System
Shock 2* dialogue dataset. It passed a human review of the full 82-line
catalogue and tests with fully original sentences that were not present in the
training dataset.

## Credits and legal

SHODAN, Xerxes, and *System Shock* are properties of their respective rights
holders. These are fan-made voice models. All rights to the source material
belong to those rights holders.
