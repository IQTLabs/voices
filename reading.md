---
title: Reading
feature_text: |
  ## Dataset Specifics and Reading Material
  Implementation details, file formats, and paper links
feature_image: "https://picsum.photos/1300/400?image=989"
excerpt: "A short description of the VOiCES corpus"
aside: True
---

## Dataset Description

The Voices Obscured in Complex Environmental settings (VOiCES) corpus presents audio
recorded in acoustically challenging conditions. Recordings took place in real rooms of
various sizes, capturing different background and reverberation profiles for each
room. Various types of distractor noise (TV, music, or babble) were simultaneously
played with clean speech. Audio was recorded at a distance using twelve microphones
strategically placed throughout the room. To imitate human behavior during conversation,
the foreground speaker used a motorized platform, rotating over a range of angles during recordings.

Three hundred distinct speakers from LibriSpeech's "clean" data subset were selected as the source audio, ensuring a 50-50 female-male split. In preparation for
upcoming data challenges, the first release of the VOiCES corpus will include 200 speakers only. The remaining 100 speakers will be reserved for model validation; the full corpus
(300 speakers) will be released once the data challenge is closed.  

In addition to the full dataset, we also provide a dev set and a mini-dev set. Both maintain the data structure of the VOiCES corpus, but include a small subset of data. The dev set includes audio files for four randomly selected speakers (50-50 female-male split) for data recorded in Room-1. This includes data from all twelve microphones. The mini-dev set includes one speaker, one room (Room-1), and studio microphones only.

## Readme

For more details about how to use the dataset, please see our [README](Lab41-SRI-VOiCES_README.md).

## Blog Posts

- [Introducing the Voices Obscured in Complex Environmental Settings (VOiCES) corpus](https://gab41.lab41.org/introducing-the-voices-obscured-in-complex-environmental-settings-voices-corpus-b7990d080176)
- [Realistic speech data applications in Machine Learning](https://gab41.lab41.org/using-realistic-audio-data-in-machine-learning-49ef034b93a3)
- [VOiCES: closing one chapter and starting a second](https://gab41.lab41.org/voices-closing-one-chapter-and-starting-a-second-1c67d32ac888)

## Publications

- [Robust Speaker Recognition from Distant Speech Under Real Reverberant Environments](https://www.isca-speech.org/archive/Interspeech_2018/pdfs/2221.pdf)
- [Corpus Description and Collection Methodology](https://arxiv.org/abs/1804.05053)
- [175th Meeting of the Acoustical Society of America](https://voices18.github.io/general/2018/05/07/asa-2018/)
#### Interspeech 2019: VOiCES froma  Distance Challenge
- [The VOiCES from a Distance Challenge 2019 Evaluation Plan](https://arxiv.org/abs/1902.10828)
- [The VOiCES from a Distance Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/1837.pdf)
- [STC Speaker Recognition Systems for the VOiCES From a Distance Challenge](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/2783.pdf)
- [Analysis of BUT Submission in Far-Field Scenarios of VOiCES 2019 Challenge](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/2471.pdf)
- [The STC ASR System for the VOiCES from a Distance Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/1574.pdf)
- [The I2R’s ASR System for the VOiCES from a Distance Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/2130.pdf)
- [Multi-Task Discriminative Training of Hybrid DNN-TVM Model for Speaker Verification with Noisy and Far-Field Speech](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/3010.pdf)
- [The JHU Speaker Recognition System for the VOiCES 2019 Challenge](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/2979.pdf)
- [Intel Far-Field Speaker Recognition System for VOiCES Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/2894.pdf)
- [The I2R’s Submission to VOiCES Distance Speaker Recognition Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/1997.pdf)
- [The LeVoice Far-Field Speech Recognition System for VOiCES from a Distance Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/1944.pdf)
- [The JHU ASR System for VOiCES from a Distance Challenge 2019](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/1948.pdf)
- [The DKU System for the Speaker Recognition Task of the 2019 VOiCES from a Distance Challenge](https://www.isca-speech.org/archive/Interspeech_2019/pdfs/1435.pdf)
