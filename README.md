# Pattern Recognition of Emotions in Speech Using SVM

We humans spend more time with our computers than with other human beings. Even the socialization process is done through a machine. With the passage of time and the advancement of technology, human-computer interaction must improve. Your goal then is to create an effective user interface, making your user experience more natural.

Since emotions form an integral part of human interactions, they have become an important aspect of the development of applications based on human-computer interaction.
Automatic emotion recognition is very useful not only in daily life, with virtual assistants (such as Alexa or Google Home), or when searching for the intention of written text on social networks. But they are also very useful in detecting emotions of mobile phone users, call center operators and customers, car drivers, pilots, and many other users of intelligent systems.

From medicine to Advertising. The addition of emotions to machines must be recognized as a critical factor in making machines appear and act in a human-like manner.

## SER and its Challenges
Emotions can be captured and technologically evaluated in a variety of ways, such as facial expressions, physiological cues, or speech. The latter is an area known as SER, Speech Emotion Recognition.

In general, speech recognition systems are based on the Hidden Markov Model -HMM[[1]( https://cs.brown.edu/research/ai/dynamics/tutorial/Documents/References.html#RabinerandJuangASSP-86/)].This approach works on the assumption that as long as a speech signal is studied on a sufficiently small time scale, it can be approximated as a stationary process, that is, a process in which the statistical properties do not change with time and "memoryless", which means that the probability distribution of the future value of a random variable depends only on its present value[[2]( https://cs.brown.edu/research/ai/dynamics/tutorial/Documents/References.html#RabinerandJuangASSP-86/)].

In a typical hidden Markov model the speech signal is divided into fragments. These fragments are processed, from which a sequence of values is obtained. The output of the model, are these values that will be grouped [[3]( https://cs.brown.edu/research/ai/dynamics/tutorial/Documents/References.html#RabinerandJuangASSP-86/)] depending on the characteristic that you want to capture within the signal.

In general, the data collection process in SER works based on the following scheme; First, we have the formulation of the Speech Formulation that is given by a Human Vocal Mechanism. Then we have the message or the Acoustic Wave in Air, which will be received by a dissipative that will convert the digital signal. In the end, the machine, through algorithms, will perform speech understanding.

However, the process of recognizing human emotions is a very complex task in itself in view of the ambiguity in its classification. Due to this, the development of algorithms capable of performing pattern recognition is a priority in the advancement of HCI.

This is where machine learning methods provide us with an incredibly powerful tool capable of performing these pattern recognition processes.
For this project, machine learning processes will be applied through the use of algorithms based on classification models by means of vector support machines. In order to classify emotions from the extraction of a group of speech characteristics.

## Database and Features extraction
In order to classify emotions into speech from the extraction of a group of sound characteristics using vector support machines, the following datasets were used which can be found in kaggle:

- [RAVDESS]( https://zenodo.org/record/1188976#.YZqg8p1BxPY/)
- [CREMA]( https://www.kaggle.com/code/shivamburnwal/speech-emotion-recognition/notebook/) 
- [TESS]( https://www.kaggle.com/code/shivamburnwal/speech-emotion-recognition/notebook/) 
- [SAVEE]( https://www.kaggle.com/code/shivamburnwal/speech-emotion-recognition/notebook/)

Now, as previously mentioned, we want to perform a *sound characteristics* extraction. Since voices are waves, it was proposed to use the following characteristics or features:

1. Energy
2. Vector Chroma
3. Mel Spectrogram 
4. Cepstral Coefficients in Mel Frequencies
5. Root mean square error
6. Zero crossing speed
7. Spectral Centroid
8. Spectral Bandwidth
9. Spectral Contrast
10. Coefficient of Hue or Spectral Flatness
11. Spectral Frequency Rolloff
12. Tonnez


