## Frequently Asked Questions

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

**Q10. For the open condition, is it allowed to use LibriSpeech data to train the systems including SAD/VAD?**
LibriSpeech is the source data for VOiCES set and there is a chance of creating an overlap with the eval data. Therefore teams are NOT allowed to use LibriSpeech itself as we would invalidate a lot of conclusions that we might otherwise draw from open condition systems.

**Q11. There are more than 4 million trials, can I use a subset of the trials or do I have to test all the trials?**
The development set of approximately 4 million trials is provided for you to develop your system. You may wish to develop on a subset of these trials, however, we recommend that you report results on the complete development set (if possible) in your Interspeech submission in order to allow for a comparison of results across submissions for the challenge.

**Q12. Can we use publicly available MUSAN speech to create babble noise?**
Unfortunately, we can NOT allow teams to use speech part of MUSAN data to create Babble noise since the speech portion of MUSAN is part of LibriSpeech. LibriSpeech is also the data source for VOiCES data and there is a possibility that there will be an overlap. However, you can use any publicly available audio to generate babble noise for both fixed and open conditions as long as it doesn’t have LibriSpeech audio in it.

**Q13. For the fixed system ASR, what are the specifications for language modeling? Particularly, are we allowed to used any text data (e.g. gigaword) for building the LM?**
As specified in the evaluation plan under section 3.1.1, LM training in the fixed condition is restricted to the 80h subset of LibriSpeech provided:
“While the participants may train their own SAD as well as use external non-speech resources for data augmentation, they may not use additional speech data from any other source for model training (acoustic model, language model, speech enhancement, etc.)"

If you have more questions contact us at voices_poc@sri.com
