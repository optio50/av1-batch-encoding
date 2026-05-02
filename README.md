# AV1 Batch Encoding

This repository contains a Python wrapper script for batch encoding video files to AV1 using SVT-AV1 via `ffmpeg`.

## Files

- `AV1-SVT-New-argparse.py` - batch encoding script with scaling, CRF, SVT preset, film grain, and subtitle preservation.

## Requirements

- `python3`
- `ffmpeg` with `libsvtav1` enabled
- `ffprobe`
- `mkvpropedit`
- `tput`

## Usage

Basic usage:

```bash
python3 AV1-SVT-New-argparse.py /path/to/input.mp4 /path/to/output_dir
```

Example:

```bash
python3 AV1-SVT-New-argparse.py --scale 720 --crf 32 --preset-svt 8 --film-grain 10 /path/to/input.mkv /path/to/output_dir
```

## Options

- `--pin-cores` / `--no-pin-cores` - Enable or disable CPU core pinning for the encoding process.
- `--cpu-cores` - CPU core range to pin ffmpeg to.
- `--scale` - Output height in pixels. Use `0` for no scaling.
- `--crf` - CRF value for SVT-AV1 (`1-70`).
- `--preset-svt` - SVT-AV1 preset (`0-13`).
- `--film-grain` - Film grain synthesis strength (`0-50`).
- `--depth` - Directory traversal depth for batch mode.

## Notes

- SVT-AV1 supports film grain encoding and can preserve subtitles and chapters.
