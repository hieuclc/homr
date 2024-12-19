# homr
homr is an Optical Music Recognition (OMR) software that allows transcription of camera pictures or scanned images into machine-readable format of MusicXML, based on works of [oemer](https://github.com/BreezeWhite/oemer) and [Polyphonic-TrOMR](https://github.com/NetEase/Polyphonic-TrOMR).

The workflow of the program is as follows:
- Image processing and dewarping
- Predictions for staff and symbols
- Stafflines and noteheads detection
- Notegroups, symbols and rhythm detection
- Use Transformer to create semantic sequences from segmented outputs
- Convert to MusicXML file

## Datasets
CVC-Muscima: Handwritten music score images of 1,000 music sheets written by 50 different musicians.

DeepScores-extended: 255,385 Images of digitally rendered images of written sheet music.

## Requirements
Python 3.10 with Poetry installed

Optional: NVIDIA GPU compatible with CUDA 12.1 by deactivate `os.environ["CUDA_VISIBLE_DEVICES"] = "-1"` in main.py.

## Installation
Make sure your system meet the previous requirements

Clone the directory

Install dependencies by `poetry install`

Prepare the image and run the program by `poetry run homr <path to your image>`

The result MusicXML file will be saved in the same directory as the input, then use any program that supports the format to play the file