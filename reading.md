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

### Source audio references

Source audio references, per LibriSpeech, are provided in three different tables as follows:  

Information on the speaker ID, book ID, and chapter ID
> Lab41-SRI-VOiCES-speaker-book-chapter.tbl

Speaker ID, gender, and LibriSpeech data subset
> Lab41-SRI-VOiCES-speaker-gender-dataset.tbl

Orthographic transcription of all audio files
> Lab41-SRI-VOiCES.refs


### Data format

Audio files are available in WAV format with 16 kHz sample rate with 16-bit precision. All files begin with the corpus name Lab41-SRI-VOiCES. Source files specify speaker, chapter, and chapter segment identification number. The file naming format sample is shown below:
> Lab41-SRI-VOiCES-scr-sp< speaker_ID >-ch< chapter_ID >-sg< segment_ID >.wav

Naming convention for audio at a distance include all the above information, with additional descriptors for room, distractor noise, microphone type, microphone location, and position of foreground speaker in degrees. The file naming format is shown below:
> Lab41-SRI-VOiCES-< room >-< distractor_noise >-sp< speaker_ID >-ch< chapter_ID >-seg< segment_ID >-mc< mic_ID >-< mic_type >-< mic_location >-dg< degree >.wav

---
Possible descriptors for room, distractor noise, microphone type, and microphone location, are show in the table.

<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

| File Code        | Type               | Definition                                                            
|------------------|--------------------|-------------------------------------------------------|
| rm1              | Room | Room-1: dimensions 146” x 107” (x 107” height)                             |
| rm2              | Room | Room-2: dimensions 225” x 158” (x 109” height)                             |
| scr              | Source audio       | Source audio for foreground speaker                                        |
| none             | Distractor noise   | No distractor noise played                                                 |
| musi             | Distractor noise   | Music distractor noise played                                              |
| tele             | Distractor noise   | Television distractor noise played                                         |
| babb             | Distractor noise   | Babble distractor noise played                                             |
| stu              | Mic type           | Cardioid dynamic studio microphone                                         |
| lav              | Mic type           | Omnidirectional condenser lavalier microphone                              |
| clo              | Mic location       | Closest to foreground speaker- on table                                    |
| mid              | Mic location       | Mid-distance to foreground speaker- on table                               |
| far              | Mic location       | Farthest to foreground speaker- on stand                                   |
| beh              | Mic location       | Behind foreground speaker- on stand                                        |
| cec              | Mic location       | Overhead on ceiling, clear                                                 |
| ceo              | Mic location       | Overhead on ceiling, fully obstructed                                      |
| tbo              | Mic location       | Partially obstructed - table                                               |
| wal              | Mic location       | Fully obstructed - wall                                                    |
| impulse          | Signal             | Two seconds with transient sound in middle, for room response              |
| swoop            | Signal             | Rising tone for 20 seconds, for room response                              |
| tone             | signal             | Steady tone for 15 seconds, for room response                              |


---
Microphone identification numbers are unique to a specific microphone location and type, defined below.


<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

| Mic_ID | Location  | Type
|--------|-----------|-------|
| 01     | clo       | stu   |
| 02     | clo       | lav   |
| 03     | mid       | stu   |
| 04     | mid       | lav   |
| 05     | far       | stu   |
| 06     | far       | lav   |
| 07     | beh       | stu   |
| 08     | beh       | lav   |
| 09     | tbo       | lav   |
| 10     | cec       | lav   |
| 11     | ceo       | lav   |
| 12     | wal       | lav   |

---

Audio files to characterize the room response are also available:
> Lab41-SRI-VOiCES-< room >-< signal >-mc< mic_ID >-< mic_type >-< mic_location >.wav

As are recordings of distractor noise only or ambient room background only:
> Lab41-SRI-VOiCES-< distractor_noise >-mc< mic_ID >-< mic_type >-< mic_location >.wav

## Blog Posts

- [Introducing the Voices Obscured in Complex Environmental Settings (VOiCES) corpus](https://gab41.lab41.org/introducing-the-voices-obscured-in-complex-environmental-settings-voices-corpus-b7990d080176)

## Publications

- [Corpus Description and Collection Methodology](https://arxiv.org/abs/1804.05053)
- [175th Meeting of the Acoustical Society of America](https://voices18.github.io/general/2018/05/07/asa-2018/)

