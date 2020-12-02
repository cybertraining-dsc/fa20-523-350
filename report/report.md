# Review of Text-to-Voice Synthesis Technologies

[![Check Report](https://github.com/cybertraining-dsc/fa20-523-350/workflows/Check%20Report/badge.svg)](https://github.com/cybertraining-dsc/fa20-523-350/actions)
[![Status](https://github.com/cybertraining-dsc/fa20-523-350/workflows/Status/badge.svg)](https://github.com/cybertraining-dsc/fa20-523-350/actions)
Status: in progress

- [ ] does not follow template, watch video
- [ ] please use proper markdown 
- [ ] this document does not follow clear guidlines posted for this work
- [ ] citations can not be after a period they must be before
- [ ] Please remote the bulletins from the refereneces. Follow the template when adding references.
- [ ] do not use html
- [ ] do not use contractions

Eugene Wang, [fa20-523-350](https://github.com/cybertraining-dsc/fa20-523-350/), [Edit](https://github.com/cybertraining-dsc/fa20-523-350/blob/main/project/project.md)


{{% pageinfo %}}

## Abstract

<p>The paper is about the most popular and most successful voice synthesis methods in the recent 5 years. Area of examples that would be explored in order to produce such a review paper would consist of both academic research papers and examples real world successful applications. For each specific example examined, its dataset, theory/model, training algorithms, and the purpose and use for that specific method/technology would be examined and reviewed. Overall, I will compare the similarities and differences between these methods and explore how big data enabled these new voice-synthesis technologies. And last, the changes these technologies will bring to our world in the future is discussed and both positive and negatives implications are explored in depth. This paper is meant to be informative to the both general audience and professionals about the how voice-synthesizing techniques has been transformed by big data, most important developments in the academic research of this field, and how these technologies are adopted to create innovation and value. But also to explain the logic and other technicalities behind these algorithms created by academia and applied to real world purposes. Codes and datasets of voices will be supplemented as for the purpose of demonstrations of these technologies in working. </p>

Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** Text-to-Speech Synthesis, Speech Synthesis, Artificial Voice

## 1. Introduction (History and Real-World Motivations)

<p>The idea of making machines talk has be around for many over 200 years. For example, in as early as 1779, a scientist called Christian Gottlieb Kratzenstein built models of the human vocal tract (the cavity in human beings where voice is produced in) that can produce the sound of long vowels (a, e, i , o, u)[^1]. From then till the 1950s, there have been many successful studies and attempts to make physical models that mechanically imitate the human voice. In the late 1960s, the people trying to synthesize human voice started to do it electronically. In 1961, by utilizing the IBM 704 (one of the first mass produced computers), John Larry Kelly Jr and Louis Gerstman, made a voice recorder synthesizer (aka. vocoder). Their system was able to recreate the song “Daisy Bell”[^2]. Before the current deep neural network trend, modern systems for text-to-Speech (TTS) or speech synthesis has been dominated by concatenative methods and then statistical parametric methods. Creating the ability for humans to converse with computers or any machines is a one of those age-old dreams of humans. A human-computer interaction technology that provides the computers to comprehend raw human speech has been revolutionized in last couple of years by the amount of big data we have now and the implementation, mainly deep neural networks, that feeds on big data. </p>

## 2. Overview of the Technology

<p>Concatenative methods work by stringing together segments of prerecorded speech segments. The best of concatenative methods is the Unit Selection. The recorded voice segments in unit selection is categorized into individual phones, diphones, half-phones, morphemes, syllable, words, and phrases. Unit selection divides a sentence into segmented units by a speech recognizer, then these units are filled in with recorded voice segments based on parameters like frequency, duration, syllable position, as well as these parameters of its neighboring units [^3]. The output of this system can be undistinguishable from natural voice, but only in very specific context that it’s being tuned for and provided that the system has a very large database of speeches, usually in the range of dozens of hours of speech. This system suffers from boundary artifacts, which are unnatural connections between the sewed-together speech segments. </p>
<p>What came after concatenative methods are the statistical parametric methods, it solved many of the concatenative method’s boundary artifact problems. Statistical Parametric methods are also called Hidden-Markov-Models-based (HHM-based) methods, because HMM are often the choice to model the probability distribution of speech parameters. The HH model selects the most likely speech parameters like frequency spectrum, fundamental frequency, and duration (prosody), given the word sequence and trained model parameters. Last, these speech parameters are combined to construct a final speech wave form. Statistical parametric synthesis can be described as “generating the average of some sets of similarly sounding speech segment” [^4]. The advantage that statistical parametric methods have over concatenative methods is the ability to modify aspects of the speech such as the gender of speaker, or the emotion and emphasis of the speech. The use of statistical parametric methods marks the beginning of the transition from a knowledge-based system to a data-based system for speech synthesis.  </p>
<p>From a high-level point of view, a text-to-speech system is composed of two components. The first component starts with text normalization, also called preprocessing or tokenization. Text normalization converts symbols, numbers, and abbreviations into normal dictionary words. After text normalization, the first components end with text-to-phenome. Text-to-phenome is the process of dividing the text into units like words, phrases, and sentences; then converting these units into target phonetic representations, or target prosody (frequency contour, durations…etc.) <pic example of prosody> The second component, often called the synthesizer or vocoder, takes the symbolic phonetic representations and converts them into the final sound. </p>
  
## 3. Example A: Tacotron I & II and WaveNet for Voice Synthesis

<p> The Tacotron a TTS system that begin by using a sequence to sequence architecture implemented with neural network to produce magnitude spectrograms with a given string of text. The first component of Tacotron is one single neural network that was trained from 24.6 hours of speech audio recorded by a professional female speaker. The effectiveness of a neural network in speech synthesis shows how big data approaches are improving and changing up the speech synthesis methodologies. Tacotron uses the Giffin-Lim algorithm for its second component, the vocoder. The authors note that their choice of approach for the second component is only used as a placeholder at that time, and they anticipated that the Tacotron is be more advanced with alternative approaches for the second component, the vocoder, in the future. [^6] And Tacotron 2 is what the authors of the original Tacotron might have envisioned. </p>
<p> Tacotron 2 is a TTS system built entirely using neural network architectures for both its first and second component. Tacotron 2 combines the original tacotron’s first component and combine it with Google’s WaveNet that serves as the second component. The tacotron-style first component responsible for preprocessing and text-to-phenome, produces mel spectrograms given the original text input. Mel spectrograms are representations of frequencies in mel scale as it varies over different time. The mel spectrograms are then fed into WaveNet, a vocoder that serves as the second component, which outputs the final sound. [^7] </p> 
<p> WaveNet is a deep neural network model that can generate raw audio.  What is different about WaveNet is that it can model and generate the raw audio form. Typically, audio is digitized by sampling a single data point for every very small-time interval. A raw audio wave form typically contains 16,000 sample point in every second of audio. With that many sample points per second, an audio clip of a simple speech would contain millions and billions of data points. To make a generative model for these sample audio points, the model needs to be autoregressive, meaning every sample point generated by the model is influenced by its earlier sample points that is also generated by the model itself. [^8] A very difficult challenge that DeepMind solved. Before DeepMind came up with WaveNet, they made pixelRNN and pixel CNN. Which proved that it is possible to generate a complicated image one pixel at a time given a large amount of quality training data. This time instead of an image generated a pixel at a time, an audio clip is generated one sample point at a time. <p>
<p> WaveNet is trained with audio recordings, or wave forms, from real human speech. After training the model, WaveNet can generate synthetic utterances of human speech that doesn’t actually mean anything. WaveNet would be fed a random audio sample point, and it will predict the next audio sample point and feed it back to itself and generating the next one, so on and so forth, producing complex realistic speech wave form. To apply WaveNet to TTS systems, it would have to be trained not only the human speech but also each training sample’s corresponding linguistic and phonetic features. This way, WaveNet would be conditioned on both the previous audio sample points and the words we want WaveNet to say. In a real working TTS system, these linguistic and phonetic features are the product of the first component, which is responsible for text-to-phenome. [^8] </p>


![Figure 1](https://raw.githubusercontent.com/cybertraining-dsc/fa20-523-350/main/report/images/wavenet.gif)
**Figure 1:** Illustration of WaveNet's autoregression [^9]


## 4. Application and Discussion of Example A

Utilizing WaveNet to clone anyone’s voice

* Transfer Learning from Speaker Verification to Multispeaker Text-To-Speech Synthesis [Link](https://arxiv.org/abs/1806.04558) 
* "Artificial Intelligence Can Now Copy Your Voice: What Does That Mean For Humans?" [Link](https://www.forbes.com/sites/bernardmarr/2019/05/06/artificial-intelligence-can-now-copy-your-voice-what-does-that-mean-for-humans/#6cbb296e72a2)


## 5. Example B: “Neural Text to Speech” TTS by Neural Network: Mixture Density Network

* Deep Voice: Real-time Neural Text-to-Speech [Link](https://arxiv.org/abs/1702.07825)


## 6. Application and Discussion of Example 2: How Apple made Siri Sound more natural in iOS 13

* Deep Learning for Siri’s Voice: On-device Deep Mixture Density Networks for Hybrid Unit Selection Synthesis (Link: https://machinelearning.apple.com/research/siri-voices )


## 7. Conclusion


## 8. References

[^1]: J. Ohala, “Christian Gottlieb Kratzenstein: Pioneer in Speech Synthesis”, ICPhS. (2011) Link: https://www.internationalphoneticassociation.org/icphs-proceedings/ICPhS2011/OnlineProceedings/SpecialSession/Session7/Ohala/Ohala.pdf>

[^2]: J. Mullennix and S. Stern, "Synthesized Speech Technologies: Tools for Aiding Impairment", University of Pittsburh at Johnsonstown (2010) Link: <https://books.google.com/books?id=ZISTvI4vVPsC&pg=PA11&lpg=PA11&dq=bell+labs+Carol+Lockbaum&hl=en#v=onepage&q=bell%20labs%20Carol%20Lockbaum&f=false>

[^3]: A. Hunt and A. W. Black, "Unit Selection in a Concatenative Speech Synthesis System Using a Large Speech Database", ATR Interpreting Telecommunications Research Labs. (1996) Link: <https://www.ee.columbia.edu/~dpwe/e6820/papers/HuntB96-speechsynth.pdf>

[^4]: A. W. Black, H. Zen and K. Tokuda, "Statistical Parametric Speech Synthesis", Language Technologies Institute, Carnegie Mellon University (2009) Link: <https://doi.org/10.1016/j.specom.2009.04.004>

[^5]: Van Santen, Jan P. H, “Progress in Speech Synthesis”, New York: Springer, (1997) Link: <https://archive.org/details/progressinspeech0000unse>

[^6]: Wang, Yuxuan, et al. “Tacotron: Towards End-to-End Speech Synthesis”, Google Inc, (2017) Link: <https://arxiv.org/pdf/1703.10135.pdf>

[^7]: Shen, Jonathan, et al. “Natural TTS Synthesis by Conditioning WaveNet on Mel Spectrogram Predictions.”, Google Inc, (2018) Link: <arxiv.org/abs/1712.05884.pdf>

[^8]: Oord, Aaron van den, et al. “WaveNet: a Generative Model for Raw Audio”, Deepmind (2016) Link: <https://arxiv.org/pdf/1609.03499.pdf>

[^9]: Oord, Aaron van den and Dieleman, Sander, "WaveNet: A generative model for raw audio", Blogpost: Deepmind (2016) Link <https://deepmind.com/blog/article/wavenet-generative-model-raw-audio>

[^10]: 


[Online]. Available: <
## Initial Report Proposal

<p>Change of project format from report w/ code to report w/o code. Reason: I've decided to do a report instead of a project for the same topic, because I don't have the computing power to recreate let alone change the training process of the large neural networks technologies I've chosed to write about.</p>




