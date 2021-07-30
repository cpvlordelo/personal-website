---
author:
  name: "Carlos Lordelo"
date: 2017-09-10
linktitle: Unsupervised Harmonic Source Separation
title: Unsupervised Harmonic Source Separation
weight: 10
series:
- Source Separation
draft: false
---

I have done this project for my Bachelor's Degree thesis. It consists of my own implementation in MATLAB of the algorithm for unsupervised source separation based on the concept of Average Harmonic Structure (AHS) modelling that has been proposed on the following paper:

* Z. Duan, Y. Zhang, C. Zhang and Z. Shi, "__Unsupervised Single-Channel Music Source Separation by Average Harmonic Structure Modeling__", in _IEEE Transactions on Audio, Speech, and Language Processing_, vol. 16, no. 4, pp. 766-778, May 2008, [doi: 10.1109/TASL.2008.919073](https://doi.org/10.1109/TASL.2008.919073).

The results I obtained using my own implementation were quite similar to the results of the authors. I have written a detailed report (in Portuguese) of this project, which can be found in [my bachelor's thesis](http://monografias.poli.ufrj.br/monografias/monopoli10022740.pdf). The code with my own implementation for this work can be found in [this repository](https://github.com/cpvlordelo/source-separation-AHS).

## Overall Description
The basic functioning of this algorithm starts with the the assumption that when playing in narrow pitch ranges, different monophonic harmonic instrumental sources in a piece of music often have different but stable harmonic structures. So, monophonic sources can be uniquely characterised by a model that is learned by computing their average harmonic structure througout the music signal. 

Given the number of instrumental sources, this unsupervised method learns those models directly from the mixed signal by clustering the harmonic structures extracted from different frames. The corresponding sources are then extracted from the mixed signal using the models by subtraction on the spectrogram domain. It is important to note that this method has been proposed forseparating monophonic instrumental sources.