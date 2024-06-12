### Text-to-Speech Script: Guide

The provided Python script converts text from a file into speech using a specified Text-to-Speech (TTS) model. Below are detailed instructions on how to use this script effectively:

#### Prerequisites

Before running the script, ensure you have installed the required libraries.
Run
```
pipenv install
```
or install the libraries with `pip`:
```
pip install coqui-tts
pip install pydub
pip install torch
```

Save the provided Python code in a file named `storyteller.py` or any preferred name.

#### Input Text File

Prepare a text file with your desired content. For example, save it as `input.txt`.

#### Running the Script

Open a terminal or command prompt and navigate to the directory containing `storyteller.py` and your input text file. Run the script using appropriate parameters:

Available parameters include:
- `--in-file`: Path to the input text file (required).
- `--out-file`: Path for the output WAV file (default: "book.wav").
- `--start-line`: Line number to start reading from (default: 1).
- `--to-line` or `--process-lines`: To specify either an end line number or a count of lines to process. If `--to-line` is set, it specifies the last line number; if not, `--process-lines` determines how many lines are processed starting from `--start-line`.
- `--pause-between-lines`: Duration in milliseconds for silence between lines (default: 1000).

Example usage:
```
> ./storyteller --start-line=3 --to-line=5 --process-lines=130 --in-file=~/Temp/alice.txt --out-file=alice.wav --pause-between-lines=750 --model-name=tts_models/en/vctk/vits --speaker-id=p230
```

This command converts lines 3 to 5 (inclusive) from the `alice.txt` file into speech, with a pause of 750 milliseconds between each line. The output is saved as "alice.wav".

#### Model Selection

The script automatically loads a default TTS model but can be customized using:
- `--model-name`: Path or name of the TTS model to use (the default value is set to `"tts_models/en/vctk/vits"`).
- `--speaker-id`: Speaker ID for multi-speaker models.

If the requested **model** cannot be found, the script lists available models and prompts for selection.

In case of multi-speaker model, the script lists available **speaker ID**s and prompts for selection.

#### Device Selection

The script determines a suitable device for processing the TTS output automatically.

### Note on Usage

Ensure that your TTS model is compatible with the input text. The script currently targets the English language using VCTK dataset-based models.

With these steps, you can generate audio files from textual content seamlessly using this Python script and the provided README guide.
