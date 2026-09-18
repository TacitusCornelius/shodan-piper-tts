# Xerxes Piper voice model

This folder contains a Piper TTS voice model for Xerxes from *System Shock 2*.

## Files

| File | Purpose |
|---|---|
| `en_US-xerxes-medium.onnx` | Model weights |
| `en_US-xerxes-medium.onnx.json` | Piper voice configuration |

Model settings:

- Sample rate: 22,050 Hz
- Quality: medium
- Language: `en_US`
- eSpeak voice: `en-us`
- Speakers: 1

## Install

Download both files into a Piper voices directory:

```bash
mkdir -p ~/piper/voices/xerxes
cd ~/piper/voices/xerxes
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/Xerxes_medium/en_US-xerxes-medium.onnx
curl -LO https://github.com/TacitusCornelius/shodan-piper-tts/raw/main/Xerxes_medium/en_US-xerxes-medium.onnx.json
```

## Usage

```bash
echo "The containment protocol remains active." | piper \
  --model ~/piper/voices/xerxes/en_US-xerxes-medium.onnx \
  --output_file xerxes.wav
```

## Provenance

The model was fine-tuned with the TextyMcSpeechy `tts_dojo` pipeline.

The model passed a human review of the full 82-line catalogue and tests with
fully original sentences that were not present in the training dataset.

## Checksums

```text
SHA-256  en_US-xerxes-medium.onnx
7626e290d4549335d1031c3dc19baff36a4303a9798ba21d63a2fb3c49b96351

SHA-256  en_US-xerxes-medium.onnx.json
ed8eb49ee3296bc3777d665ec281b9abd159ef3da8b8f4228e5e639124c50b2b
```

## Credits and legal

Xerxes and *System Shock 2* are properties of their respective rights holders.
This is a fan-made voice model. All rights to the source material belong to
those rights holders.
