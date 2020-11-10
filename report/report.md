# please use proper markdown 

- [ ] this document does not follow clear guidlines posted for this work
- [ ] citations can not be after a period they must be before

# Review of Text-to-Voice Synthesis Technologies

Eugene Wang, [fa20-523-350](https://github.com/cybertraining-dsc/fa20-523-350/), [Edit](https://github.com/cybertraining-dsc/fa20-523-350/blob/master/project/project.md)


{{% pageinfo %}}

## Abstract

Contents

1. Introduction to the topic
2. History and Real-World Motivations
3. Overview of the technology
   * Main Principles of Text-to-Speech Synthesis System [Link](https://publications.waset.org/8303/pdf )
4. Example 1: Google’s WaveNet for Voice Synthesis
   * WaveNet: A Generative Model for Raw Audio [Link](https://arxiv.org/abs/1609.03499 )
5. Application of Example 1: Utilizing WaveNet to clone anyone’s voice
   * Transfer Learning from Speaker Verification to Multispeaker Text-To-Speech Synthesis [Link](https://arxiv.org/abs/1806.04558) 
6. Discussion of Example 1: Implications of ability to clone anyone’s voice
   * "Artificial Intelligence Can Now Copy Your Voice: What Does That Mean For Humans?" [Link](https://www.forbes.com/sites/bernardmarr/2019/05/06/artificial-intelligence-can-now-copy-your-voice-what-does-that-mean-for-humans/#6cbb296e72a2)
7. Example 2: “Neural Text to Speech” TTS by Neural Network: Mixture Density Network
   * Deep Voice: Real-time Neural Text-to-Speech [Link](https://arxiv.org/abs/1702.07825 )
8. Application and Discussion of Example 2: How Apple made Siri Sound more natural in iOS 13
   * Deep Learning for Siri’s Voice: On-device Deep Mixture Density Networks for Hybrid Unit Selection Synthesis [Link](https://machinelearning.apple.com/research/siri-voices )

{{% /pageinfo %}}

**Keywords:** missing

<p>The idea of making machines talk has be around for many over 200 years. For example, in as early as 1779, a scientist called Christian Gottlieb Kratzenstein built models of the human vocal tract (the cavity in human beings where voice is produced in) that can produce the sound of long vowels (a, e, i , o, u).[^1] From then till the 1950s, there have been many successful studies and attempts to make physical models that mechanically imitate the human voice. In the late 1960s, the people trying to synthesize human voice started to do it electronically. In 1961, by utilizing the IBM 704 (one of the first mass produced computers), John Larry Kelly Jr and Louis Gerstman, made a voice recorder synthesizer (aka. vocoder). Their system was able to recreate the song “Daisy Bell”. [^2] Before the current deep neural network trend, modern systems for text-to-Speech (TTS) or speech synthesis has been dominated by concatenative methods and then statistical parametric methods. </p>
<p>Concatenative methods work by stringing together segments of prerecorded speech segments. The best of concatenative methods is the Unit Selection. The recorded voice segments in unit selection is categorized into individual phones, diphones, half-phones, morphemes, syllable, words, and phrases. Unit selection divides a sentence into segmented units by a speech recognizer, then these units are filled in with recorded voice segments based on parameters like frequency, duration, syllable position, as well as these parameters of its neighboring units. [^3] The output of this system can be undistinguishable from natural voice, but only in very specific context that it’s being tuned for and provided that the system has a very large database of speeches, usually in the range of dozens of hours of speech. This system suffers from boundary artifacts, which are unnatural connections between the sewed-together speech segments. </p>
<p>What came after concatenative methods are the statistical parametric methods, it solved many of the concatenative method’s boundary artifact problems. Statistical Parametric methods are also called Hidden-Markov-Models-based (HHM-based) methods, because HMM are often the choice to model the probability distribution of speech parameters. The HH model selects the most likely speech parameters like frequency spectrum, fundamental frequency, and duration (prosody), given the word sequence and trained model parameters. Last, these speech parameters are combined to construct a final speech wave form. Statistical parametric synthesis can be described as “generating the average of some sets of similarly sounding speech segment.” [^4] The advantage that statistical parametric methods have over concatenative methods is the ability to modify aspects of the speech such as the gender of speaker, or the emotion and emphasis of the speech. The use of statistical parametric methods marks the beginning of the transition from a knowledge-based system to a data-based system for speech synthesis.  </p>
<p>From a high-level point of view, a text-to-speech system is composed of two components. The first component starts with text normalization, also called preprocessing or tokenization. Text normalization converts symbols, numbers, and abbreviations into normal dictionary words. After text normalization, the first components end with text-to-phenome. Text-to-phenome is the process of dividing the text into units like words, phrases, and sentences; then converting these units into target phonetic representations, or target prosody (frequency contour, durations…etc.) <pic example of prosody> The second component, often called the synthesizer or vocoder, takes the symbolic phonetic representations and converts them into the final sound. </p>
<p>In this paper, we’ll explore the TTS system known as Tacotron 2. Tacotron 2 is a TTS system built using neural network architecture for both its first and second component. Tacotron 2 combines the original tacotron’s first component and combine it with Google’s WaveNet that serves as the second component. The tacotron-style first component responsible for preprocessing and text-to-phenome, produces mel spectrograms given the original text input. Mel spectrograms are representations of frequencies in mel scale as it varies over different time. The mel spectrograms are then fed into WaveNet, a vocoder that serves as the second component, which outputs the final sound. </p>
<p>The </p>





## References

[^1]: History and Development of Speech Synthesis [Link](http://research.spa.aalto.fi/publications/theses/lemmetty_mst/chap2.html)

[^2]: Computer Synthesized Speech Technologies: Tools for Aiding Impairment [Link](https://books.google.com/books?id=ZISTvI4vVPsC&pg=PA11&lpg=PA11&dq=bell+labs+Carol+Lockbaum&hl=en#v=onepage&q=bell%20labs%20Carol%20Lockbaum&f=false)

[^3]: Unit Selection in a Concatenative Speech Synthesis System Using a Large Speech Database [Link](https://www.ee.columbia.edu/~dpwe/e6820/papers/HuntB96-speechsynth.pdf)




## Initial Project Proposal

-	I plan to study about the most popular and most successful voice synthesis methods in the recent 5-10 years. Area of examples that would be explored in order to produce such a review paper would consist of both academic research papers and real world successful applications. For each specific example examined, I will focus my main points on the dataset, theory/model, training algorithms, and the purpose and use for that specific technique/technology. Overall, I will compare the similarities and differences between these examples and explore how voice-synthesis technology has evolved in the big data revolution. And last, the changes these technologies will bring to our world in the future will be discussed by presenting both the positive and negatives implications. The first and main goal (80%) of this paper is to be informative to the both general audience and professionals about the how voice-synthesizing techniques has been transformed by big data, most important developments in the academic research of this field, and how these technologies are adopted to create innovation and value. The second and smaller goal (20%) of this paper is to explain the logic and other technicalities behind these algorithms created by academia and applied to real world purposes. Codes and datasets of voices will be supplemented as for the purpose of demonstrations of these technologies in working. To get a good grade I need to be achieve the stated main goal and second goal. The main goal requires me to find, read, and understand relevant papers and articles pertaining to topic and the second goal requires be to acquire enough technical knowledge to be able to produce a working example code to showcase the technology discussed.