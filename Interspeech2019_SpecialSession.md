---
title: Description
feature_text: |
  ## The VOiCES from a Distance Challenge -- Interspeech 2019 Special Session

feature_image: "https://picsum.photos/1300/400?image=1051"
excerpt: "Interspeech 2019 Special Session"
aside: True
#redirect_from:
#  - /Interspeech2019-Special-Session/
#  - https://voices18.github.io/Interspeech2019-Special-Session/
#permalink: /Interspeech2019_SpecialSession/
---

## The Challenge

The VOiCES from a distance challenge 2019 will be focused on benchmarking and further improving state-of-the-art technologies
in the area of speaker recognition and automatic speech recognition (ASR) for far-field speech. The challenge will use the VOiCES data for development and evaluation. The challenge will have two tracks for speaker recognition and ASR:

(i) _Fixed System_ - Training data is limited to a subset of VOiCES, a subset of LibriSpeech, [SITW](http://www.speech.sri.com/projects/sitw/), and [VoxCeleb](http://www.robots.ox.ac.uk/~vgg/data/voxceleb/index.html#portfolio)

(ii) _Open System_ - Participants can use any external datasets they have access to (private or public)

<center>{% include button.html text="REGISTER HERE" color="#733f94" link="https://goo.gl/forms/OehGNC7E7HRtxjCb2" %} </center> <br/>


 > Participants who complete the challenge (**submit their system outputs and system description**) will get early access to the VOiCES phase 2 data.   
The phase 2 data is an extension of VOiCES, with over 310k audio files recorded in new reverberant environments.

### Updates and News
###### Jan. 24, 2019
-  The official [scorer for speaker recognition](https://app.box.com/s/9tpuuycgxk9hykr6romsv05vvmdpie11/folder/63883249918) is now released
- Updated ASR development set is released.
- Updated evaluation plan is released.

### Data and Evaluation
Data subsets for challenge tracks are available for download [HERE](https://app.box.com/s/9tpuuycgxk9hykr6romsv05vvmdpie11). Make sure to check-out the README.VOICES_2019.txt for more details on what is included in each subset and tips on how to to unzip the data.<br/>

The [evaluation plan](/images/VOiCES_eval_plan.v5.pdf) outlines training conditions for fixed and open tracks, details on the development and evaluation data, model performance metrics, and how to submit scores, for both ASR and SID tasks. This document also provides information on how the training and evaluation datasets provided for download are organized, and evaluation rules for the challenge.  


### Timeline
**Jan. 15, 2019 :** Release of the evaluation plan and development sets  
**Feb. 25, 2019 :** Evaluation data available  
**March 4, 2019 :**  System output submission deadline (11:59 PM PST)  
**March 11, 2019 :** Release of evaluation results  
**March 15, 2019 :** System description submission and release of VOiCES phase II key for the participating teams  
**March 29, 2019 :** Regular paper submission deadline for Interspeech 2019  

### FAQ’s

**Q1. Am I allowed to use additional “non-speech” data for data augmentation by mixing them with clean training
data you provided for the fixed condition?**
As specified in the evaluation plan, you are allowed to use any “non-speech” data for data augmentation
in the fixed condition for ASR and speaker recognition.

**Q2. I cannot download the data, the website is blocked by my institution or country. How can I get the
data?**
Please send an email to voices_poc@sri.com
and we will create an ftp link for you to download the data.

**Q3. Is there a registration deadline?**
Participants may register at any time before March 4th.

**Q4. Will the accepted paper submitted for the challenge be published in the conference proceedings?**
Yes, the submitted paper will go through a peer review process and will be part of the official Interspeech
conference proceedings.

**Q5. Will there be metadata available in the evaluation set (speaker, room, microphone, etc) for each utterance (as in the dev set)?**
We only provide metadata in the dev set as a way for the participants to look at the performance of
their system under different microphones, rooms or distractors. The metadata will not be provided for the evaluation set, in fact, we anticipate the file names will be fully anonymized.

**Q6. We are allowed to use VoxCeleb1, VoxCeleb2 and SITW data for training. Are we limited to using the official annotations only? For example, the VoxCeleb corpora contain segments from YouTube videos. Are we limited to using only the annotated segments or may we use other parts of the videos also, if we find it useful?**
The audio data from the Voxceleb1 and Voxceleb2 is restricted to the official annotations for the fixed condition submissions. In this way, the fixed condition can serve its purpose of measuring the performance of different systems trained with the same data (or a subset thereof). However, you can certainly use all the audio from the Voxceleb-provided URLs for
the open condition system development.

**Q7. How are we supposed to submit our system description and score files?**
We will provide you instructions along with the release of the evaluation data on how to upload the
system description and score files.

**Q8. For the ASR task, may we use an external pronunciation lexicon (e.g., CMUdict) for deriving the pronunciation of words in the training data?**
Yes, you may use any dictionary you have for the purpose of this evaluation, in either fixed or open
condition.

**Q9. How will the team submission be ranked?**
The official score for a team will be selected as the best primary metric from systems submitted by
the team for that condition (up to 3 systems can be submitted per condition per task per team). These official scores will be used for ranking teams.

Additional questions about the challenge? contact us at voices_poc@sri.com
