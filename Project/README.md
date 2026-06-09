# Audio Source Separation – Independent Research Paper

**Author:** Ralph Cange  
**Course:** Independent Research  
**Semester:** Fall 2023

---

## Description

This paper explores **Audio Source Separation**, the process of isolating individual sound sources from a mixed audio signal. The research is centered around the **Cocktail Party Problem**, first identified by British scientist Colin Cherry in 1953 — the human ability to focus on one sound in a noisy environment. Engineers have since built algorithms that replicate this ability using machine learning and deep neural networks.

---

## Topics Covered

### Why Source Separation?
Voice signals are often degraded by background noise, reverberation, and overlapping speakers. Source separation is used to clean up audio in:
- Cell phone and hands-free calls
- Personal assistants (Siri, Alexa, etc.)
- Automobile navigation systems
- Medical dictation devices
- Automated Speech Recognition (ASR)

### Deep Neural Networks
- Neural networks teach computers to process information like the human brain
- Deep learning uses layered nodes (neurons) to recognize patterns in audio
- MIT student Andrew Simpson applied this to music by training on spectrograms of mixed audio

### Key Concepts
- **Spectrogram** – a visual map of a signal's frequency strength over time; used as input/output for models
- **U-Net** – a Convolutional Neural Network (CNN) architecture using skip connections as an encoder/decoder; used to estimate soft masks per audio stem

---

## Algorithms Compared

| Algorithm | Description |
|---|---|
| **MDX23** (Music Demixing Track 23) | Based on the Ultimate Vocal Remover project; combines Demucs4 and MDX neural net structures |
| **Demucs HT 4** | Uses Wave-U-Net CNN + Cross-Domain Transformer encoder for hybrid spectrogram/waveform separation |
| **Demucs 3** | Splits audio into 3 stems using CNNs and RNNs |
| **Spleeter** | One of the first publicly available source separation tools; built on TensorFlow |

---

## Quality Comparison Results

### MultiSong Dataset (SDR – higher is better)

| Algorithm | SDR Bass | SDR Drums | SDR Other | SDR Vocals | SDR Instrumental |
|---|---|---|---|---|---|
| MVSEP MDX23 | 12.50 | 11.69 | 6.54 | 9.51 | 15.82 |
| Demucs HT 4 | 12.10 | 11.30 | 5.77 | 8.36 | 13.99 |
| Demucs 3 | 10.69 | 10.27 | 5.36 | 8.13 | 14.44 |
| MDX B | — | — | — | 8.51 | 14.82 |

### MusDB Dataset
- **Demucs** performs best for drums and bass
- **MDX** performs best for vocals and accompaniment

---

## Additional Applications

### Cell Phone Noise Suppression
Three engineers developed a blind source separation algorithm that processes random background noise (not pre-recorded samples) to improve call clarity. The method maximizes the entropy of the speech signal using a Probability Density Function (PDF).

### BioCPPNet – Bioacoustics
- Bioacoustics = study of sound produced by living organisms
- **BioCPPNet** is a deep learning pipeline for separating animal sounds (bat cries, dolphin whistles, macaque vocalizations) across species
- Uses permutation-invariant training so it works regardless of source order

---

## Conclusion

Machine learning, deep neural networks, and advanced signal processing are rapidly improving audio source separation. As these techniques evolve, their applications will expand across healthcare, communications, wildlife research, and entertainment.

---

## References

1. Emerging Technology from the arXiv. (2015, April 29). *Deep Learning machine solves the cocktail party problem.* MIT Technology Review. https://www.technologyreview.com/2015/04/29/168316/deep-learning-machine-solves-the-cocktail-party-problem/
2. Vincent, E., Virtanen, T., & Gannot, S. (2018). *Audio Source Separation and Speech Enhancement* (p. 3). John Wiley & Sons, Inc.
3. Hennequin, R., Khlif, A., Voituret, F., & Moussallam, M. (2020). *Spleeter: A fast and efficient music source separation tool with pre-trained models.* https://www.researchgate.net/publication/342429039
4. Rouard, S., Massa, F., & Défossez, A. (2023). *Hybrid Transformers for Music Source Separation.* ICASSP 2023. https://doi.org/10.1109/icassp49357.2023.10096956
5. Bermant, P. C. (2021). *BioCPPNet: Automatic Bioacoustic Source Separation with Deep Neural Networks.* https://doi.org/10.1101/2021.06.18.449016
