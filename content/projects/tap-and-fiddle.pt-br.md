---
author:
  name: "Carlos Lordelo"
date: 2020-12-07
linktitle: Base de Dados de Música "Tap & Fiddle"
title: Base de dados de Música "Tap & Fiddle"
weight: 10
series:
- Dataset, Source Separation
draft: false
---

[VERSÃO EM PORTUGUÊS EM CONSTRUÇÃO. A SEGUIR SEGUE A VERSÃO EM INGLÊS]


In this project we have curated **28** stereo recordings of traditional Scandinavian fiddle tunes with accompanying foot-tapping, which is standard performance practice within these musical styles. Its corpora contains not only the mixed signals, but also the two isolated instrumental tracks that can be used to train supervised models for source separation.

* The fiddle (or violin) track (harmonic); 
* The foot-tapping track (percussive).  

Moreover, foot-tapping in performance of fiddle music has not been systematically studied yet, even though it very often appears as an integral part of the musical expression in Scandinavian fiddle music as a percussive accompaniment. Hence, apart from contributing to the music source separation community, it is expected that _Tap & Fiddle_ can also be used by researchers and enthusiasts working with analysis of fiddle music as well as studies of metrical expression in music in general.

The dataset is divided into a training set with 23 files and a test set with 5. In order to facilitate comparison among the research community, it is recommended that supervised approaches be trained on the provided train set and tested on the test set.

## Audio and Repertoire Characteristics
The set contains recordings of different dance types, including Norwegian Halling music, with straight single and double tapping as well as Swedish polska tunes, where tapping is considerably scarcer with tapping on beat 1 and 3 in 3-beat time being the most common way to tap. 

The sound of the foot-tapping ranges from more soft foot-tapping produced by a sock-covered foot, to sharp, distinct and loud foot-tapping produced by shoes with hard heels on parquet. In addition, the loudness of the foot-tapping regardless of sound source in relation to the fiddle is varied between and within recordings.

It is also important to note that some of the recordings in the dataset are variations of the same Scandinavian fiddle tune. Those recordings are versions containing different acoustic conditions and audio characteristics for the foot-tapping and/or for the violin sound within the same tune.

## Recording Methodology
Each isolated signal was recorded by one fiddle player in a natural 30 squared meters room with separate miking for the foot and the fiddle (violin), using close-up Shure SM-58 microphones and a Focusrite sound card recorded in Audacity on a Macbook PRO. The mixture signals were created by adding the two isolated signals together. All the recordings have been made using the same instrument, which was played by the same performer. 

The audio files are uncompressed and saved as stereo files with sampling frequency of 44100 Hz and 32 bits per sample. The average duration for a recording in _Tap & Fiddle_ is __65__ seconds, which totalise around `65 x 28 = 30m 20s` of full play time.

## Download and Licensing
If you want to download the dataset, you can find it [here](https://zenodo.org/record/4308731). You just have to fill a a small form with youra email address and explain why you want to download the dataset for.

The ___Tap & Fiddle Dataset___ has been compiled by Carlos Lordelo, Sven Ahlbäck, Emmanouil Benetos, Simon Dixon and Patrik Ohlsson and is offered for non-commercial research use only. The data is provided for educational purposes only and the material should not be used for any commercial purpose.

More specifically, the data is licensed under the terms of the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License.](http://creativecommons.org/licenses/by-nc-sa/4.0/). To view a copy of this license, visit <http://creativecommons.org/licenses/by-nc/4.0/> or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA. 

The creators of ___Tap & Fiddle___ and their corresponding affiliation institutes are not liable for, and expressly exclude, all liability for loss or damage however and whenever caused to anyone by any use of ___Tap & Fiddle___ or any part of it. 

## How to cite
If you use this dataset, please, provide the following citation in your work:

- C. Lordelo, E. Benetos, S. Dixon, S. Ahlbäck and P. Ohlsson "Adversarial Unsupervised Domain Adaptation for Harmonic-Percussive Source Separation" in *IEEE Signal Processing Letters* 2020 (under review at time of this writing)

## Acknowledgements
This project has received funding from the European Union's Horizon 2020 research and innovation programme under the Marie Sklodowska-Curie grant agreement No. 765068

### Contact Information
For queries and suggestions regarding the __Tap & Fiddle Dataset__, please send me an email. You can find it at my [homepage](/) 