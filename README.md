# TIMIT Database

## Intro
- TIMIT Database is a corpus of continuous speech that is glossed and segmented by phoneticians as a DARPA project created by TI (Texas Instrument) and MIT (Massachusetts Institute of Technology)
	- Lore derived from [Hugging Face link](https://huggingface.co/datasets/timit_asr)
- This folder is uploaded and made possible by [Professor Khalil Iskarous](https://dornsife.usc.edu/profile/khalil-iskarous/) from the [University of Southern California's Linguistics Department](https://sail.usc.edu/span/usc-timit/)

## Motivation
- The official documentation can be found in the sources in [`/TIMIT/DOC`](https://github.com/Ky-Ng/Timit-Database/tree/main/TIMIT/DOC) and in [`/Timit/Covleb.DOC`](https://github.com/Ky-Ng/Timit-Database/blob/main/TIMIT/covleb.DOC)
- The main goal of creating this repository is to make it easier for people to add the original unedited `TIMIT` database as a `submodule` with full transparency of the data they are using
- Also, I'm a Computational Linguistic student interested in `Speech Processing` and want to practice writing documentation and hopefully make it easier for people new in the field like me to understand these databases!
## File Tree Structure
- The file tree separates features of a particular speaker:
```
/<CORPUS>/<USAGE>/<DIALECT>/<SEX><SPEAKER_ID>/<SENTENCE_ID>.<FILE_TYPE>
```
- The example given in [`/Timit/Covleb.DOC`](https://github.com/Ky-Ng/Timit-Database/blob/main/TIMIT/covleb.DOC): 
```
/timit/train/dr1/fcjf0/sa1.wav
```
- Breaking down each part:

| File Tree Component | Example | Meaning                                                                                                                          |
| ------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `<CORPUS>`          | `timit` | From `TIMIT` database                                                                                                            |
| `<USAGE>`           | `train` | Training dataset (either `Test` or `Training)                                                                                    |
| `<DIALECT>`         | `dr1`   | `Dialect Region 1` corresponding                                                                                                 |
| `<SEX>`             | `f`     | `Female`                                                                                                                         |
| `<SPEAKER_ID>`      | `cjf0`  | `cjf` represent the speaker's initials, `0` represents a unique ID if speaker's have same initials (1990s style IDing it seems!) |
| `<SENTENCE_ID>`     | `sa1`   | One of the most famous `TIMIT` sentences: `She had your dark suit in greasy wash water all year.                                 |
| `<FILE_TYPE>`       | `.wav`  | WAV file representing the sound wave                                                                                             |
- Note: A list of the `<DIALECT>`s can be found in [Section 1 of Covleb.DOC](https://github.com/Ky-Ng/Timit-Database/blob/main/TIMIT/covleb.DOC)
## Segmentation Structure 
- The database provides the following segmentation levels:
	- Sentence Level: `.TXT`
	- Word Level: `.WRD`
	- Phoneme Level: .`PHON`
- For the example, we'll choose `PHON` files since `TXT` and `WRD` files are written in standard English orthography whereas `PHON` files extract use `TIMIT`s own phonetic description as detailed in [`DOC/PHONCODE.DOC`](https://github.com/Ky-Ng/Timit-Database/blob/main/TIMIT/DOC/PHONCODE.DOC)
- The example from `PHONECODE.DOC` below is the word `joke`

| IPA  | TIMIT Transcription | Explanation                                                                                               |
| ---- | ------------------- | --------------------------------------------------------------------------------------------------------- |
| /dʒ/ | `DCL`               | `Alveolar` Constriction Location                                                                          |
|      | `JH`                | `Glottal Narrow` and `Alveo-Palatal` Constriction Location (`voiced alveo-palatal`) coming from the `/ʒ/` |
| /ow/ | `ow`                | Diphthong `ow`                                                                                            |
| /k/  | `kcl`               | `Velar` constriction with `Glottal Wide` (`voiceless velar closure`)                                      |
| REL  | `k`                 | Stop Release                                                                                              |
- Note: it's interesting to see how the `TIMIT` transcription gives gestural information about the phonemes in addition to an explicit symbol difference between released and unreleased stops

## Usage
- To copy the Timit Database to your project, either download the repo as a Zip or run the following `git submodule` command in the root of your Git project.
```
git submodule add git@github.com:Ky-Ng/TIMIT-Database.git
```
