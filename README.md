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

The function _"def extract_features(path)"_ was created to perform this process.

## Method and Model Evaluation
In order to understand the essence of the SVM classification, only four basic concepts need to be understood: (i) the separator hyperplane, (ii) the maximum margin hyperplane, (iii) the margin, and (iv) the kernel.

A hyperplane: It is basically a line that separates the characteristics depending on their behavior. However, sometimes there are many lines that can separate our data into different sets. Which of these provides the best classifier? The simplest way to work around this problem is to select the line that is, roughly speaking, "in the middle". That is, the line that is at the maximum distance from any of the features, for example, the energy and the chroma vector, would be selected.

However, we have started from the fact that these characteristics can be separated. But what if for an emotion like anger, the energy is similar to the energy for happiness, for example? Intuitively, we would like vector support machines to be able to deal with data errors by allowing some anomalous expression profiles to fall on the "wrong side" of the separation hyperplane.

To handle cases like these, the algorithm must be modified by adding a "margin" a soft margin. Essentially, this allows some data points to be pushed across the margin of the separation hyperplane without affecting the final result.

Since we don't want this to happen we often introduce control parameters that specify how much feature data they are allowed to violate the separation hyperplane and how far across the line they are allowed to go. The kernel function provides a solution to this problem by adding an additional dimension to the data.

With the function created, data processing was performed for each dataset. These numeric values were stored in a .csv file which can be accessed [here](https://drive.google.com/file/d/1qXaWiRSWDJi6Tw7oE-m14Z1yRM3hJqD6/view?usp=sharing/) ~~Please do not try to open the file as it is too large and could damage your pc~~ 

The sklearn toolkit called [SVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html#sklearn.svm.SVC/) will be used, which is capable of classifying multi-class databases supported by supervised learning methods such as vector support machines.

The accuracy of the classification was evaluated using the _accuracy score_ function subject to different variables such as: Test size, which determines the proportion of the data set to be included in the test division. Kernel that specifies the type of kernel to use in the algorithm. Regularization parameter (C). And Kernel function polynomials degree.

Continuing with the evaluation of the performance of the model according to the results obtained from the _accuracy score_, the hyperparameters Kernel = rbf and C = 100 were taken as standard values, with a _test size_ of 0.3. For this, the sklearn classification report function was used, which provides a summary of the main metrics used in classification;

- Precision = Precision is the ability of the classifier not to label a sample that is negative as positive. The lower the dispersion the greater the accuracy. In our model, the precision is the dispersion of the set of values obtained _yEst_ from repeated measurements of the _ytest_.

- Recall = Also known as sensitivity, it is the proportion that the model obtains by correctly classifying a positive value. This metric indicates the fraction of Labels where we correctly declare x emotion of all cases where the actual emotion is x emotion.

- f1-score = Summarizes accuracy and sensitivity into a single metric and is understood as the mean between the two.

- support = Is the number of occurrences of each class in _ytrain_.



