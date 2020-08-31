---
title: Readme
feature_text: |
  ## Detailed VOiCES Readme
  Voices Obscured in Complex Environmental Settings
feature_image: "/voices/images/readme.jpg"
excerpt: "A detailed description of the VOiCES corpus"
aside: False
---
## Dataset Description

The VOiCES corpus is a collaboration between
SRI International and Lab41, In-Q-Tel, presenting audio
recorded in acoustically challenging conditions. Recordings took place in real rooms of
various sizes, capturing different background and reverberation profiles for each
room. Various types of distractor noise were simultaneously
played with clean speech. Audio was recorded at a distance using various microphones
placed throughout the room. To imitate human behavior during conversation,
the foreground loudspeaker was placed on a motorized platform that rotated over a range of angles during recordings.

Three hundred distinct speakers from LibriSpeech's "clean" data subset were selected as the source audio, ensuring a 50-50 female-male split. In preparation for
upcoming data challenges, the first release of the VOiCES corpus will include 200 speakers only. The remaining 100 speakers will be reserved for model validation; the full corpus
(300 speakers) will be released once the data challenge is closed.     

## Description of Files

`VOiCES_competition` was a release designed for a special competition workshop at InterSpeech 2019.  See the `README` inside the archive for more information on the structure and arrangement of the dataset.

`VOiCES_release` is the full VOiCES dataset with a general purpose directory structure.  `VOiCES_devkit` is a subset of the data (detailed below) designed for easier experimentation and development.  Both `VOiCES_release` and `VOiCES_devkit` have the same directory structure.

`recording_data` contains two files, `distances.csv` and `quality_metrics.csv` with useful information about the recordings.  Both files have a row for every recording.

#### VOiCES_release

`VOiCES_release` contains all recordings from each room, mic, and under all distractor types.  Rooms 1 and 2 have 12 mics, and rooms 3 and 4 have 20 mics.  As there are four types of distractor noises, there are 256 VOiCES recordings per source recording.  All source recordings have unique transcripts.

<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

|Subset    |# Examples    |
|----------|--------|
|Train|661,248|
|Test| 337,920|
|Total|999,168|

<br>

#### VOiCES_devkit

`VOiCES_devkit` is a subsample of the full `VOiCES_release` dataset.  All of the speakers of the full dataset are retained.  For each speaker we randomly selected two librispeech source recordings.  For each source recording we retained all of the VOiCES recordings from microphones 1 and 5, the nearest and furthest mics, respectively, from the speaker.  Otherwise all rooms and background distractor types are included for a total of 32 VOiCES recordings per source recording.

<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

|Subset    |# Examples    |
|----------|--------|
|Train|12,800|
|Test| 6,400|
|Total|19,200|

## recording_data.tar.gz

`recording_data.tar.gz` contains two files, `distances.csv` and `quality_metrics.csv`, with auxiliary information for each recording in the VOiCES dataset, with a row for each recording.

### distances.csv

Each row in this file contains the distance (in inches) from the foreground speaker, each of the distractor speakers, and the floor to the microphone for a given recording.  Specifically, it has the following columns:

|Column   |Datatype   |Description|   
|---------|-----------|-----------|
|distractor 1| integer| Inches from mic to 1st distractor speaker
|distractor 2| integer| Inches from mic to 2nd distractor speaker
|distractor 3| integer| Inches from mic to 3rd distractor speaker
|floor| integer| Inches from mic to floor
|foreground| integer| Inches from mic to source/foreground speaker
|query_name| string| The recording filename without directory path or extension, useful as a key to join with other tables (e.g. index files)


### quality_metrics.csv

This file contains a number of precomputed measures of speech quality or intelligibility for each recording.  Intrusive methods use the original Librispeech source audio as the ground truth.  For recordings where the VOiCES audio does not fully contain the source audio (detectable from comparing source_length and noisy_length in index files), all quality_metrics are set to -1.

|Column   |Datatype   |Description|   
|---------|-----------|-----------|
|query_name| string| The recording filename without directory path or extension, useful as a key to join with other tables (e.g. index files)
|pesq nb| float| [Perceptual Evaluation of Speech Quality](https://en.wikipedia.org/wiki/Perceptual_Evaluation_of_Speech_Quality), computed using [python-pesq](https://github.com/ludlows/python-pesq) with narrow band setting
|pesq wb| float| [Perceptual Evaluation of Speech Quality](https://en.wikipedia.org/wiki/Perceptual_Evaluation_of_Speech_Quality), computed using [python-pesq](https://github.com/ludlows/python-pesq) with wide band setting
|STOI| float| [Short Time Objective Intelligibility Measure](https://ieeexplore.ieee.org/document/5495701), computed using [pystoi](https://github.com/mpariente/pystoi)
|SIIB| float| [Speech Intelligibility in Bits](https://arxiv.org/abs/1708.05132) computed using [pySIIB](https://github.com/kamo-naoyuki/pysiib) with all default settings.
|SRMR| float| [Normalized speech-to-reverberation modulation energy ratio](https://ieeexplore.ieee.org/abstract/document/6953337), computed using [SRMRpy](https://github.com/jfsantos/SRMRpy) with norm=True.

---
### Source audio references

Source audio references, per LibriSpeech, are provided in three different tables as follows:  

Information on the speaker ID, book ID, and chapter ID
> Lab41-SRI-VOiCES-speaker-book-chapter.tbl

Speaker ID, gender, and LibriSpeech data subset
> Lab41-SRI-VOiCES-speaker-gender-dataset.tbl

Orthographic transcription of all audio files
> Lab41-SRI-VOiCES.refs


### Data format

Audio files are available in WAV format with 16 kHz sample rate with 16-bit precision. All files begin with the corpus name Lab41-SRI-VOiCES. Source audio files specify speaker, chapter, and chapter segment identification number. The file naming format sample is shown below:
> Lab41-SRI-VOiCES-src-sp< speaker_ID >-ch< chapter_ID >-sg< segment_ID >.wav

The naming convention for audio recorded at a distance includes all the above information, with additional descriptors for room, distractor noise, microphone type, microphone location, and position of foreground loudspeaker in degrees. The file naming format is shown below:
> Lab41-SRI-VOiCES-< room >-< distractor_noise >-sp< speaker_ID >-ch< chapter_ID >-seg< segment_ID >-mc< mic_ID >-< mic_type >-< mic_location >-dg< degree >.wav

Audio files to characterize the room response are also available:
> Lab41-SRI-VOiCES-< room >-< signal >-mc< mic_ID >-< mic_type >-< mic_location >.wav

As are recordings of distractor noise only or ambient room background only:
> Lab41-SRI-VOiCES-< distractor_noise >-mc< mic_ID >-< mic_type >-< mic_location >.wav

---
Possible descriptors for room, distractor noise, microphone type, and microphone location, are show in the table below.

<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

| **File Code**    | **Type**           | **Definition**                                                            
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
| ds1              | Mic location       | Near distractor 1                                                          |
| ds2              | Mic location       | Near distractor 2                                                          |
| ds3              | Mic location       | Near distractor 3                                                          |
| tbc              | Mic location       | Mid-distance, on table                                                     |
| sho              | Mic location       | In cupboard, fully obstructed                                              |
| ref              | Mic location       | Across the room, near refrigerator                                         |
| obs              | Mic location       | Fully.partially obstructed in wall/ceiling                                 |
| impulse          | Signal             | Two seconds with transient sound in middle, for room response              |
| swoop            | Signal             | Rising tone for 20 seconds, for room response                              |
| tone             | signal             | Steady tone for 15 seconds, for room response                              |  

<br>

All the data is contained in two main folders: **distant-16k**, containing all the audio recordings, and **source-16k**, containing
the audio files used from LibriSpeech, corrected for DC offset and normalized to each file’s peak amplitude. The WAV files for the source audio are organized in subdirectories by speaker ID. The **distant-16k** has three main subdirectories:
- distractors : distractor noise recordings with no foreground audio for all rooms
- room-response : recorded sound to determine room-response for all rooms
- speech : for each room, recordings of foreground audio with babble, music, television or no distractor noise, arranged by
speaker ID in each subfolder.  

---
#### Directory Structure

There are three top-level directories in root folder of `VOiCES_release` and `VOiCES_devkit`: `references`, `source-16k`, and `distant-16k`.  The contents of these directories are detailed below.


`references` contains a number of files with information about the dataset.  All necessary information is gathered in `test_index.csv` and `train_index.csv`, and other files are redundant.
```
- references/
  - filename_transcripts
  - Lab41-SRI-VOiCES-speaker-book-chapter.tbl
  - Lab41-SRI-VOiCES-speaker-gender-dataset.tbl
  - test_index.csv
  - Test_Set_Speakers.csv
  - time_values.csv
  - train_index.csv
```

`source-16k` contains the original librispeech source audio.  The train-test split is the same as the VOiCES data.  The audio files are separated by speaker ID.  For example, all audio from speaker 115 is stored in `sp0115/`.
```
- source-16k/
  - test/
    - sp0115/
      - Lab41-SRI-VOiCES-src-sp0115-ch121720-sg0008.wav
      - ...
    - ...
  - train/
```


`distant-16k` contains the VOiCES data.  There are subdirectories for the audio files used to create the distractor sounds, as well as for room responses when test sounds (impulse, swoop, and tone) are played.
```
- distant-16k
  - distractors/
    - rm1/
      - babb/
        - Lab41-SRI-VOiCES-rm1-babb-mc01-stu-clo.wav
        - ...
      - ...
    - ...
  - room_response/
    - rm1/
      - impulse/
        - Lab41-SRI-VOiCES-rm1-impulse-mc01-stu-clo.wav
        - ...
      - swoop/
      - tone/
    - ...
  - speech/
    - test/
    - train/
      - rm1/
        - babb/
          - sp0032/
            - Lab41-SRI-VOiCES-rm1-babb-sp0032-ch004137-sg0007-mc01-stu-clo-dg150
          - ...
        - ...
      - ...
```

### Index Files

In the `references` directory there are two csv files, `train_index.csv` and `test_index.csv`, that serve as index files for the training and test sets, respectively.  Each file contains a single row for each recording in the given subset of the data.  Both files have the following columns.

|Column   |Datatype   |Description|   
|---------|-----------|-----------|
|index| integer| Unique index for recording
|chapter| integer | Librispeech chapter ID
|degrees| integer | Angle (in degrees) between source speaker and mic
|distractor| string | Distractor type, options are 'none', 'babb', 'tele, 'musi'
|filename| string| Path to recording .wav, relative to root directory
|gender| string| Speaker gender, options are 'M' and 'F'
|mic| integer| The mic used for this recording
|query_name| string| The filename without directory path or extension
|room| string| The room recorded in, options are 'rm1', 'rm2', 'rm3', 'rm4'
|segment| integer| Librispeech segment ID
|source| string| Path to .wav file for Librispeech source audio for this recording
|speaker| integer| Librispeech speaker ID
|transcript| string| Orthographic transcript of the Librispeech source audio
|noisy_length| integer| Sample length of recording
|noisy_sr| integer| Sample rate (hz) of recording
|noisy_time| float| Duration of recording in seconds
|source_length| integer| Sample length of Librispeech source audio
|source_sr| integer| Sample rate (hz) of Librispeech source audio
|source_time| float| Duration of Librispeech source audio in seconds


---
## Rooms 1 and 2
#### Microphone Details

Microphone identification numbers are unique to a specific microphone location and type, defined below.

<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

| **Mic_ID** | **Location**  | **Model**      | **Type**
|--------|-----------|------------|-------|
| 01     | clo       | SHURE SM58 | stu   |
| 02     | clo       | AKG 417L   | lav   |
| 03     | mid       | SHURE SM58 | stu   |
| 04     | mid       | AKG 417L   | lav   |
| 05     | far       | SHURE SM58 | stu   |
| 06     | far       | AKG 417L   | lav   |
| 07     | beh       | SHURE SM58 | stu   |
| 08     | beh       | AKG 417L   | lav   |
| 09     | tbo       | AKG 417L   | lav   |
| 10     | cec       | AKG 417L   | lav   |
| 11     | ceo       | AKG 417L   | lav   |
| 12     | wal       | SHURE SM11 | lav   |  


<br>
Distance (inches) between microphones and loudspeakers or floor, for Room-1 and Room-2 recordings.

<html>
<head>
<style>
table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
}
th, td {
    padding: 5px;
    text-align: left;
}
</style>
</head>
<body>

<table style="width:110%">
  <tr>
    <th> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Foreground</b> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Distractor 1</b> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Distractor 2</b> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Distractor 3</b></th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Floor</b> </th>    
  </tr>
  <tr>
    <td><b>Mic_ID</b></td>
    <td><b>rm-1</b></td>
    <td><b>rm-2</b></td>
    <td><b>rm-1</b></td>
    <td><b>rm-2</b></td>
    <td><b>rm-1</b></td>
    <td><b>rm-2</b></td>
    <td><b>rm-1</b></td>
    <td><b>rm-2</b></td>
    <td><b>rm-1</b></td>
    <td><b>rm-2</b></td>
  </tr>
  <tr>
    <td> 01 </td>
    <td> 38 </td>
    <td> 80 </td>
    <td> 71 </td>
    <td> 112 </td>
    <td> 71 </td>
    <td> 84 </td>
    <td> 53 </td>
    <td> 64 </td>
    <td> 42 </td>
    <td> 39 </td>  
  </tr>
  <tr>
    <td> 02  </td>
    <td> 38 </td>
    <td> 80  </td>
    <td> 71 </td>
    <td> 112 </td>
    <td> 71 </td>
    <td> 84 </td>
    <td> 53  </td>
    <td> 64  </td>
    <td> 42 </td>
    <td> 39 </td>  
  </tr>
  <tr>
    <td> 03 </td>
    <td> 72 </td>
    <td> 131 </td>
    <td> 35 </td>
    <td> 81  </td>
    <td> 56 </td>
    <td> 58  </td>
    <td> 52 </td>
    <td> 95  </td>
    <td> 42  </td>
    <td> 39  </td>  
  </tr>
  <tr>
    <td> 04 </td>
    <td> 72  </td>
    <td> 131 </td>
    <td> 35 </td>
    <td> 81  </td>
    <td> 56 </td>
    <td> 58  </td>
    <td> 52 </td>
    <td> 95  </td>
    <td> 42  </td>
    <td> 39  </td>  
  </tr>
  <tr>
    <td> 05  </td>
    <td> 119 </td>
    <td> 228 </td>
    <td> 72 </td>
    <td> 101 </td>
    <td> 33 </td>
    <td> 104 </td>
    <td> 83 </td>
    <td> 186 </td>
    <td> 70 </td>
    <td> 70 </td>  
  </tr>
  <tr>
    <td> 06 </td>
    <td> 119 </td>
    <td> 228 </td>
    <td> 72 </td>
    <td> 101 </td>
    <td> 33 </td>
    <td> 104 </td>
    <td> 83 </td>
    <td> 186 </td>
    <td> 70 </td>
    <td> 70 </td>  
  </tr>
  <tr>
    <td> 07 </td>
    <td> 29 </td>
    <td> 29 </td>
    <td> 115 </td>
    <td> 193 </td>
    <td> 133 </td>
    <td> 170 </td>
    <td> 94 </td>
    <td> 94  </td>
    <td> 70  </td>
    <td> 70 </td>  
  </tr>
  <tr>
    <td> 08 </td>
    <td> 29 </td>
    <td> 29 </td>
    <td> 115 </td>
    <td> 193 </td>
    <td> 133 </td>
    <td> 170 </td>
    <td> 94 </td>
    <td> 94 </td>
    <td> 70 </td>
    <td> 70 </td>  
  </tr>
  <tr>
    <td> 09 </td>
    <td> 58 </td>
    <td> 109 </td>
    <td> 64 </td>
    <td> 98 </td>
    <td> 60 </td>
    <td> 65 </td>
    <td> 49 </td>
    <td> 82 </td>
    <td> 28 </td>
    <td> 25 </td>  
  </tr>
  <tr>
    <td> 10 </td>
    <td> 75 </td>
    <td> 128 </td>
    <td> 90 </td>
    <td> 107 </td>
    <td> 108 </td>
    <td> 103 </td>
    <td> 106 </td>
    <td> 104 </td>
    <td> 105 </td>
    <td> 105 </td>  
  </tr>
  <tr>
    <td> 11 </td>
    <td> 75 </td>
    <td> 128 </td>
    <td> 90 </td>
    <td> 107 </td>
    <td> 108 </td>
    <td> 103 </td>
    <td> 106 </td>
    <td> 104 </td>
    <td> 106 </td>
    <td> 106 </td>  
  </tr>
  <tr>
    <td> 12 </td>
    <td> 130 </td>
    <td> 116 </td>
    <td> 861 </td>
    <td> 116 </td>
    <td> 40 </td>
    <td> 115 </td>
    <td> 81 </td>
    <td> 164 </td>
    <td> 12 </td>
    <td> 10 </td>  
  </tr>
</table>

</body>
</html>

---
## Rooms 3 and 4
#### Microphone Details

Microphone identification numbers are unique to a specific microphone location and type, defined below.

<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>

| **Mic_ID** | **Location**  | **Model**      | **Type**
|--------|-----------|------------|-------|
| 01     | clo       | SHURE SM58 | stu   |
| 02     | clo       | AKG 417L   | lav   |
| 03     | mid       | SHURE SM58 | stu   |
| 04     | mid       | AKG 417L   | lav   |
| 05     | far       | SHURE SM58 | stu   |
| 06     | far       | AKG 417L   | lav   |
| 07     | beh       | SHURE SM58 | stu   |
| 08     | beh       | AKG 417L   | lav   |
| 09     | tbo       | AKG 417L   | lav   |
| 10     | cec       | AKG 417L   | lav   |
| 11     | ceo       | AKG 417L   | lav   |
| 12     | wal       | SHURE SM58 | lav   |
| 13     | ds1       | ATR1500    | stu   |
| 14     | ds2       | ATR1500    | stu   |
| 15     | ds3       | ATR1500    | stu   |
| 16     | tbc       | ATR4697    | bar   |
| 17     | sho       | L41        | mem   |
| 18     | clo       | ADA I2S    | mem   |
| 19     | ref       | ADA I2S    | mem   |
| 20     | obs       | ADA I2S    | mem   |

<br>

Distance (inches) between microphones and loudspeakers or floor, for Room-1 and Room-2 recordings.
For microphones 13, 14 and 15 the distances are reported first for non-babble sessions, and then for babble sessions.

<html>
<head>
<style>
table, th, td {
    border: 1px solid black;
    border-collapse: collapse;
}
th, td {
    padding: 5px;
    text-align: left;
}
</style>
</head>
<body>

<table style="width:110%">
  <tr>
    <th> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Foreground</b> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Distractor 1</b> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Distractor 2</b> </th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Distractor 3</b></th>
    <th colspan="2" style="font-size:115%;text-align:center;"> <b>Floor</b> </th>    
  </tr>
  <tr>
    <td><b>Mic_ID</b></td>
    <td><b>rm-3</b></td>
    <td><b>rm-4</b></td>
    <td><b>rm-3</b></td>
    <td><b>rm-4</b></td>
    <td><b>rm-3</b></td>
    <td><b>rm-4</b></td>
    <td><b>rm-3</b></td>
    <td><b>rm-4</b></td>
    <td><b>rm-3</b></td>
    <td><b>rm-4</b></td>
  </tr>
  <tr>
    <td> 01 </td>
    <td> 67 </td>
    <td> 72 </td>
    <td> 179 </td>
    <td> 291 </td>
    <td> 170 </td>
    <td> 222 </td>
    <td> 141 </td>
    <td> 79 </td>
    <td> 41 </td>
    <td> 41 </td>  
  </tr>
  <tr>
    <td> 02  </td>
    <td> 67 </td>
    <td> 72  </td>
    <td> 179 </td>
    <td> 291 </td>
    <td> 170 </td>
    <td> 222 </td>
    <td> 141  </td>
    <td> 79  </td>
    <td> 41 </td>
    <td> 41 </td>  
  </tr>
  <tr>
    <td> 03 </td>
    <td> 146 </td>
    <td> 167 </td>
    <td> 117 </td>
    <td> 200  </td>
    <td> 157 </td>
    <td> 150  </td>
    <td> 106 </td>
    <td> 126  </td>
    <td> 41  </td>
    <td> 41  </td>  
  </tr>
  <tr>
    <td> 04 </td>
    <td> 146  </td>
    <td> 167 </td>
    <td> 117 </td>
    <td> 200  </td>
    <td> 157 </td>
    <td> 150  </td>
    <td> 106 </td>
    <td> 126  </td>
    <td> 41  </td>
    <td> 41  </td>  
  </tr>
  <tr>
    <td> 05  </td>
    <td> 281 </td>
    <td> 387 </td>
    <td> 103 </td>
    <td> 76 </td>
    <td> 207 </td>
    <td> 106 </td>
    <td> 165 </td>
    <td> 306 </td>
    <td> 67 </td>
    <td> 71 </td>  
  </tr>
  <tr>
    <td> 06 </td>
    <td> 281 </td>
    <td> 387 </td>
    <td> 103 </td>
    <td> 76 </td>
    <td> 207 </td>
    <td> 106 </td>
    <td> 165 </td>
    <td> 306 </td>
    <td> 67 </td>
    <td> 71 </td>  
  </tr>
  <tr>
    <td> 07 </td>
    <td> 58 </td>
    <td> 71 </td>
    <td> 292 </td>
    <td> 367 </td>
    <td> 252 </td>
    <td> 420 </td>
    <td> 232 </td>
    <td> 167  </td>
    <td> 67  </td>
    <td> 70 </td>  
  </tr>
  <tr>
    <td> 08 </td>
    <td> 58 </td>
    <td> 71 </td>
    <td> 292 </td>
    <td> 367 </td>
    <td> 252 </td>
    <td> 420 </td>
    <td> 232 </td>
    <td> 167 </td>
    <td> 67 </td>
    <td> 67 </td>  
  </tr>
  <tr>
    <td> 09 </td>
    <td> 88 </td>
    <td> 128 </td>
    <td> 163 </td>
    <td> 241 </td>
    <td> 165 </td>
    <td> 183 </td>
    <td> 129 </td>
    <td> 101 </td>
    <td> 27 </td>
    <td> 27 </td>  
  </tr>
  <tr>
    <td> 10 </td>
    <td> 176 </td>
    <td> 173 </td>
    <td> 135 </td>
    <td> 208 </td>
    <td> 174 </td>
    <td> 159 </td>
    <td> 135 </td>
    <td> 128 </td>
    <td> 126 </td>
    <td> 95 </td>  
  </tr>
  <tr>
    <td> 11 </td>
    <td> 176 </td>
    <td> 175 </td>
    <td> 135 </td>
    <td> 210 </td>
    <td> 174 </td>
    <td> 155 </td>
    <td> 135 </td>
    <td> 130 </td>
    <td> 125 </td>
    <td> 97 </td>  
  </tr>
  <tr>
    <td> 12 </td>
    <td> 262 </td>
    <td> 380 </td>
    <td> 54 </td>
    <td> 39 </td>
    <td> 157 </td>
    <td> 131 </td>
    <td> 188 </td>
    <td> 128 </td>
    <td> 10 </td>
    <td> 12 </td>  
  </tr>
  <tr>
    <td> 13 </td>
    <td> 230/224 </td>
    <td> 259/337 </td>
    <td> 10/30 </td>
    <td> 10/30 </td>
    <td> 107/121 </td>
    <td> 42/92 </td>
    <td> 196/175 </td>
    <td> 277/259 </td>
    <td> 42 </td>
    <td> 42 </td>  
  </tr>
  <tr>
    <td> 14 </td>
    <td> 219/178 </td>
    <td> 344/305 </td>
    <td> 23/61 </td>
    <td> 23/61 </td>
    <td> 108/95 </td>
    <td> 42/62 </td>
    <td> 185/176 </td>
    <td> 263/224 </td>
    <td> 42 </td>
    <td> 42 </td>  
  </tr>
  <tr>
    <td> 15 </td>
    <td> 201/195 </td>
    <td> 334/331 </td>
    <td> 40/60 </td>
    <td> 40/61 </td>
    <td> 102/55 </td>
    <td> 42/51 </td>
    <td> 176/213 </td>
    <td> 151/242 </td>
    <td> 42 </td>
    <td> 42 </td>  
  </tr>
  <tr>
    <td> 16 </td>
    <td> 108 </td>
    <td> 128 </td>
    <td> 144 </td>
    <td> 241 </td>
    <td> 156 </td>
    <td> 179 </td>
    <td> 120 </td>
    <td> 128</td>
    <td> 28 </td>
    <td> 28 </td>  
  </tr>
  <tr>
    <td> 17 </td>
    <td> 151 </td>
    <td> 353 </td>
    <td> 145 </td>
    <td> 40 </td>
    <td> 72 </td>
    <td> 115 </td>
    <td> 238 </td>
    <td> 281</td>
    <td> 22 </td>
    <td> 14 </td>  
  </tr>
  <tr>
    <td> 18 </td>
    <td> 75 </td>
    <td> 78 </td>
    <td> 176 </td>
    <td> 287 </td>
    <td> 175 </td>
    <td> 216 </td>
    <td> 132 </td>
    <td> 74</td>
    <td> 30 </td>
    <td> 30 </td>  
  </tr>
  <tr>
    <td> 19 </td>
    <td> 236 </td>
    <td> 286 </td>
    <td> 87 </td>
    <td> 208 </td>
    <td> 36 </td>
    <td> 232 </td>
    <td> 267 </td>
    <td> 273</td>
    <td> 38 </td>
    <td> 1 </td>  
  </tr>
  <tr>
    <td> 20 </td>
    <td> 250 </td>
    <td> 407 </td>
    <td> 173 </td>
    <td> 68 </td>
    <td> 261 </td>
    <td> 130 </td>
    <td> 80 </td>
    <td> 320</td>
    <td> 45 </td>
    <td> 97 </td>  
  </tr>
</table>

</body>
</html>

 ---
## Licensing

VOiCES is publicly available released under Creative Commos BY 4.0, free for commercial, academic, and
government use. Please do reference [VOiCES](https://arxiv.org/abs/1804.05053) if using the data in
publications.
