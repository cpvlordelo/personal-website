 ---
author:
  name: "Carlos Lordelo"
date: 2018-08-01
linktitle: Remoção Automática de Trilha Musical de Programas de TV
title: Remoção Automática de Trilha Musical de Programas de TV
weight: 10
series:
- Source Separation, Audio Fingerprinting
draft: false
---

[VERSÃO EM PORTUGUÊS EM CONSTRUÇÃO. A SEGUIR SEGUE A VERSÃO EM INGLÊS]

This project is related to the research I performed for my Master's Degree. It consists of a method to automatically detect and remove musical segments from TV programme signals. The main idea behind the method is to use a pre-existant music recording, easily obtainable from officially published CDs related to the audiovisual piece, as a reference for the undesired signal.

However, it is important to note that even though we have access to a reference for the music signal we want to extract from the mixture, we do not know the exact segments that appear in the mixture. Moreover, such segments might appear with distortions and in different positions througout the TV programme signal. So, the algorithm starts by first segmentating, detecting and synchronising the rederence signal with the usually long mixture signal that is the TV programme audio signal before performing the separation per se.

In this post I will just summarise the main structure of the method I proposed. However, a detailed explanation for the key components of the segmentation, detection, synchronisation and separation system can be found in my [Master's Degree Thesis](/docs/MastersThesis_CarlosLordelo_2018.pdf), 

* C. Lordelo, __"Automatic Removal of Music Tracks from TV Programmes"__, in _Master's Degree Thesis_, Federal University of Rio de Janeiro (UFRJ), Brazil, Aug 2018

## Detection and Synchronisation
The first step in the method is to automatically detect and synchronise segments of the reference musictrack that are spread in the long audio signal of the programme, even if they appear with time-variable gain, or after having suffered linear distortions, such as being processed by equalisation filters, or non-linear distortions, such as dynamic range compression. In order to do this, the project uses a quick-search algorithm based on robust audio fingerprinting technique that applies hash-token data types to ensure that the search and synchronisation of segments have low complexity. The basic idea is to use the mixture file as an anchor signal and computes the time-sample where there were the most landmark matches between the long anchor signal (mixture) and the queried signals (segments of reference musictrack).This algorithm is based on the following publication:

* A. Wang, __"An Industrial-Strength Audio Search Algorithm"__ in _International Society for Music Information Retrieval Conference (ISMIR)_, Baltimore, USA, Oct 2003


## Equalisation Filter and Amplitude Estimation
After the detection and syncronisation have been performed, the algorithm uses a Wiener filltering technique to estimate potential equalisation filter coefficients that could have been used during the mixing procedure. This stage is necessary because in some cases the reference musictrack segment might have gone through a filtering stage before being added to the other TV soundtrack signals (dialogue + effects signal, for example).

Then, the method applies a template matching algorithm to estimate time-varing amplitude gains to properly scale the musical segments to the correct amplitude they appear in the mixture. For instance, it is really common to have musictrack signals appearing with fade-ins and fade-outs in a TV programme signal. 

## Separation
This is the last step of the method. The separation is performed by synchonising, filtering and applying the time-varying amplitude gain to segments of the musictrack and subtracting from the TV audio signal in the time domain.


## Results
In summary, even though the full algorithm works really well with synthesised signals, where the mixture is created by segmenting, filtering and mixing a reference music signal with another audio signal (speech + audio effects), when using real-world TV programme signals, the synchronisation stage works really well, but, in my experiments, the separation didn't obtain good results. I believe the reason is because the mixing procedure usually applies non-linear distortions in the signals, such as compression, that are not taken into account by the algorithm. Also, the reference signal that is used might not be the exact same signal that was used in the TV programme signal, so, in this case, the separation stage also fails. 

Anyway, the full code I implemented in MATLAB for this project can be found [here](https://github.com/cpvlordelo/musictrack-removal) and if you want more information about the project you can find in my [Master's Thesis](/docs/MastersThesis_CarlosLordelo_2018.pdf) 
