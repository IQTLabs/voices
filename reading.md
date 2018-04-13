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

### Data format

Audio files will be available in WAV format with 16 kHz sample rate with 16-bit precision. All files begin with the corpus name Lab41-SRI-VOiCES. Source files specify speaker, chapter, and chapter segment identification number. The file naming format sample is shown below:
> Lab41-SRI-VOiCES-scr-sp< speaker_ID >-ch< chapter_ID >-sg< segmetn_ID >.wav

Naming convention for audio at a distance include all the above information, with additional descriptors for room, distractor noise, microphone type, microphone location, and position of foreground speaker in degrees. The file naming format is shown below:
> Lab41-SRI-VOiCES-< room >-< distractor_noise >-sp< speaker_ID >-ch< chapter_ID >-seg< segment_ID >-mc< mic_ID >-< mic_type >-< mic_location >-dg< degree >.wav

---
Possible descriptors for room, distractor noise, microphone type, and micrphone location, are show in the table.

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
| wlo              | Mic location       | Fully obstructed - wall                                                    |
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
| 12     | wlo       | lav   |

---

Audio files to characterize the room response are also available:
> Lab41-SRI-VOiCES-< room >-< signal >-mc< mic_ID >-< mic_type >-< mic_location >.wav

As are recordings of distactor noise only or ambient room background only:
> Lab41-SRI-VOiCES-< distractor_noise >-mc< mic_ID >-< mic_type >-< mic_location >.wav

## Blog Posts

- Introducing the Voices Obscured in Complex Environmental Settings (VOiCES) corpus

## Publications

- [Corpus Description and Collection Methodology](https://arxiv.org/submit/2227720/view)
- Abstract for ASA -- Coming Soon
- Poster for ASA -- Coming Soon

