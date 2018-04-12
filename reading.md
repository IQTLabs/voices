---
title: Reading
feature_text: |
  ## VOiCES
  Voices Obscured in Complex Environmental Scenarios
feature_image: "https://picsum.photos/1300/400?image=989"
excerpt: "A short description of the VOiCES corpus"
aside: True
---

## Dataset Description

### Data format

Audio files will be available in WAV format with 16 kHz sample rate with 16-bit precision. All files begin with the corpus name Lab41-SRI-VOiCES. Source files specify speaker, chapter, and chapter segment identification number. Sample naming format:
Lab41-SRI-VOiCES-scr-sp<speaker_ID>-ch<chapter_ID>-sg<segmetn_ID>.wav

Naming convention for audio at a distance include all the above information, with addition of descriptors on room, distractor noise, microphone type, microphone location, and position of foreground speaker in degrees. Sample file format:
Lab41-SRI-VOiCES-<room>-<distractor_noise>-sp<speaker_ID>-ch<chapter_ID>-seg<segment_ID>-mc<mic_ID>-<mic_type>-<mic_position>-dg<degree>.wav

Possible descriptors are show in the table below:
___
| File Code        | Type               | Definition                                                                 |
|:-----------------|:------------------:|:------------------------------------------------------|
| Lab41-SRI-VOiCES | General info       | Data set name: Lab41-SRI Voices Obscured in Complex Environmental Settings |
| rm1              | Recording location | Room-1: dimensions 146” x 107” (x 107” height)                             |
| rm2              | Recording location | Room-2: dimensions 225” x 158” (x 109” height)                             |
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
| wlo              | Mic location       | Fully obstructed - wall                                                    |
| impulse          | Room response      | Two seconds with transient sound in middle                                 |
| swoop            | Room response      | Rising tone for 20 seconds                                                 |
| tone             | Room response      | Steady tone for 15 seconds                                                 |
___

Microphone identification numbers are listed below:

| Mic ID | Mic Location | Mic Type |
|:-------|:-------------|:---------|
| 01     | clo          | stu      |
| 02     | clo          | lav      |
| 03     | mid          | stu      |
| 04     | mid          | lav      |
| 05     | far          | stu      |
| 06     | far          | lav      |
| 07     | beh          | stu      |
| 08     | beh          | lav      |
| 09     | tbo          | lav      |
| 10     | cec          | lav      |
| 11     | ceo          | lav      |
| 12     | wlo          | lav      |
___

## Blog Posts

- Maria's Blog Post

## Publications

- Interspeech (ArXiv)
- Abstract for ASA
- Poster for ASA ?
- Jeff's Paper (ArXiv)
- Cory's Paper
- Any references from SRI ?

