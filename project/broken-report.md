# please use proper markdown 

- [ ] this document does not follow clear guidlines posted for this work
- [ ] citations can not be after a period they must be before


The idea of making machines talk has be around for many over 200 years. For example, in as early as 1779, a scientist called Christian Gottlieb Kratzenstein built models of the human vocal tract (the cavity in human beings where voice is produced in) that can produce the sound of long vowels (a, e, i , o, u).[^1] From then till the 1950s, there have been many successful studies and attempts to make physical models that mechanically imitate the human voice. In the late 1960s, the people trying to synthesize human voice started to do it electronically. In 1961, by utilizing the IBM 704 (one of the first mass produced computers), John Larry Kelly Jr and Louis Gerstman, made a voice recorder synthesizer (aka. vocoder). Their system was able to recreate the song “Daisy Bell”. [^2] Before the current deep neural network trend, modern systems for text-to-Speech (TTS) or speech synthesis has been dominated by concatenative methods and then statistical parametric methods.

Concatenative methods work by stringing together segments of prerecorded speech segments. The best of concatenative methods is the Unit Selection. The recorded voice segments in unit selection is categorized into individual phones, diphones, half-phones, morphemes, syllable, words, and phrases. Unit selection divides a sentence into segmented units by a speech recognizer, then these units are filled in with recorded voice segments based on parameters like frequency, duration, syllable position, as well as these parameters of its neighboring units. [^3] The output of this system can be undistinguishable from natural voice, but only in very specific context that it’s being tuned for and provided that the system has a very large database of speeches, usually in the range of dozens of hours of speech. This system suffers from boundary artifacts, which are unnatural connections between the sewed-together speech segments.

What came after concatenative methods are the Statistical Parametric methods, it solved many of the concatenative method’s boundary artifact problems. Statistical Parametric methods are also called Hidden-Markov-Models-based (HHM-based) methods.




## References

[^1]: History and Development of Speech Synthesis [Link](http://research.spa.aalto.fi/publications/theses/lemmetty_mst/chap2.html)

[^2]: Computer Synthesized Speech Technologies: Tools for Aiding Impairment [Link](https://books.google.com/books?id=ZISTvI4vVPsC&pg=PA11&lpg=PA11&dq=bell+labs+Carol+Lockbaum&hl=en#v=onepage&q=bell%20labs%20Carol%20Lockbaum&f=false)

[^3]: Unit Selection in a Concatenative Speech Synthesis System Using a Large Speech Database [Link](https://www.ee.columbia.edu/~dpwe/e6820/papers/HuntB96-speechsynth.pdf)

