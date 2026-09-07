# demon_haunted

A Carl Sagan voice for on-device text-to-speech.

`vits-piper-sagan-medium.tar.bz2` is a Piper-format VITS voice (22 kHz,
single speaker) fine-tuned from the `en_US-lessac-medium` base on 41 minutes
of curated, speaker-verified Sagan recordings. It runs fully offline on
Android via [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) and is the
voice engine shipped in [TextVoice](https://github.com/pnutnam) (`piper-sagan`).

## Install (sherpa-onnx layout)

The tarball unpacks to `vits-piper-sagan-medium/`:

- `model.onnx` — VITS generator (63 MB)
- `tokens.txt` — phoneme → id map
- `espeak-ng-data/` — phonemizer data

Point sherpa-onnx's `OfflineTtsVitsModelConfig` at the three files and go.

## Notes

- Fine-tune base: rhasspy/piper `lessac-medium` (MIT). Audio: public
  lectures/recordings of Carl Sagan, curated by speaker verification.
  Personal/educational use; the voice likeness belongs to his estate's legacy.
- 4 flow... no training steps hidden: trained 2026-09-05/06, ~11k fine-tune
  steps, checkpoint picked by ear from 31 machine-scored candidates.
