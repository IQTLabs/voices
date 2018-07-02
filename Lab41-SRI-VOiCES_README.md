## Dataset Description

The Voices Obscured in Complex Environmental settings (VOiCES) corpus is a collaboration between
SRI International and Lab41, In-Q-Tel, presenting audio
recorded in acoustically challenging conditions. Recordings took place in real rooms of
various sizes, capturing different background and reverberation profiles for each
room. Various types of distractor noise (TV, music, or babble) were simultaneously
played with clean speech. Audio was recorded at a distance using various microphones
strategically placed throughout the room. To imitate human behavior during conversation,
the foreground loudspeaker was placed on a motorized platform that rotated over a range of angles during recordings.

Three hundred distinct speakers from LibriSpeech's "clean" data subset were selected as the source audio, ensuring a 50-50 female-male split. In preparation for
upcoming data challenges, the first release of the VOiCES corpus will include 200 speakers only. The remaining 100 speakers will be reserved for model validation; the full corpus
(300 speakers) will be released once the data challenge is closed.  

In addition to the full dataset, the corpus includes a dev set and a mini-dev set. Both maintain the data structure of the VOiCES corpus, but include a small subset of data. The dev set includes audio files for four randomly selected speakers (50-50 female-male split) for data recorded in Room-1. This includes data from all twelve microphones. The mini-dev set includes one speaker, one room (Room-1), and recordings from studio microphones only.

The VOiCES corpus provides audio data that better represent real-use scenarios. The data was designed to promote acoustic research on
event detection, background detection, source separation, speech enhancement, sound localization, as well as research on speaker
recognition, and speech activity detection.    

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


The directory hierarchy is shown below :  


<p align="center">
  <img width="350" src="/images/VOiCES_directory_structure.png">
</p>

---
### Microphone Details

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

<table style="width:95%">
  <tr>
    <th> </th>
    <th colspan="2">Foreground</th>
    <th colspan="2">Distractor 1</th>
    <th colspan="2">Distractor 2</th>
    <th colspan="2">Distractor 3</th>
    <th colspan="2">Floor</th>    
  </tr>
  <tr>
    <td>Mic_ID</td>
    <td>**rm-1**</td>
    <td>**rm-2**</td>
    <td>**rm-1**</td>
    <td>**rm-2**</td>
    <td>**rm-1**</td>
    <td>**rm-2**</td>
    <td>**rm-1**</td>
    <td>**rm-2**</td>
    <td>**rm-1**</td>
    <td>**rm-2**</td>
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
<style>
table, th, td {
    border: 1px solid black;
}
th, td {
    padding: 5px;
}
</style>
|        | Foreground  | Distractor 1 | Distractor 2 | Distractor 3 |     Floor   
| Mic_ID | rm-1 | rm2  | rm-1 | rm2   | rm-1 | rm2   | rm-1 | rm2   | rm-1 | rm2   |
|--------|-------------|--------------|--------------|--------------|--------------|
| 01     | 38   | 80   | 71   | 112   | 71   | 84    |   53 | 64    | 42   | 39    |
| 02     | 38   | 80   | 71   | 112   | 71   | 84    |   53 | 64    | 42   | 39    |
| 03     | 72   | 131  | 35   | 81    | 56   | 58    |   52 | 95    | 42   | 39    |
| 04     | 72   | 131  | 35   | 81    | 56   | 58    |   52 | 95    | 42   | 39    |
| 05     | 119  | 228  | 72   | 101   | 33   | 104   |   83 | 186   | 70   | 70    |
| 06     | 119  | 228  | 72   | 101   | 33   | 104   |   83 | 186   | 70   | 70    |
| 07     | 29   | 29   | 115  | 193   | 133  | 170   |   94 | 94    | 70   | 70    |
| 08     | 29   | 29   | 115  | 193   | 133  | 170   |   94 | 94    | 70   | 70    |
| 09     | 58   | 109  | 64   | 98    | 60   | 65    |   49 | 82    | 28   | 25    |
| 10     | 75   | 128  | 90   | 107   | 108  | 103   |  106 | 104   | 105  | 105   |
| 11     | 75   | 128  | 90   | 107   | 108  | 103   |  106 | 104   | 106  | 106   |
| 12     | 130  | 116  | 861  | 116   | 40   | 115   |   81 | 164   | 12   | 10    |


---

## Licensing

VOiCES is publicly available released under Creative Commos BY 4.0, free for commercial, academic, and
government use. Please do reference [VOiCES](https://arxiv.org/abs/1804.05053) if using the data in
publications.
