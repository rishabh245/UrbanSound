# UrbanSound
The automatic classification of sonic events in an urban setting has a variety of applications
including context aware computing, surveillance, or the adaptation of content-based
multimedia retrieval techniques such as highlight extraction and video summarization to
urban applications (e.g. identifying important city-wide events). Importantly, it also has the
potential of improving the quality of life of city dwellers by providing a data-driven
understanding of urban sound and noise patterns, partly enabled by the move towards “smart
cities” equipped with multimedia sensor networks.

The aim of the project is training a machine learning model that can classify different urban
sounds such as dog barking, engine idling etc. While there is a large body of research on sound
classification in related areas such as speech, music and bioacoustics, work on the analysis of
urban acoustic environments is relatively scarce. We selected two different approaches one
represents sound as an image and then uses Neural Networks which are proven technology for
pattern detection in images to classify different sounds and another approach in which we
use unsupervised feature learning using spherical k means clustering algorithm and then using
these features to train an SVM model for classification.

# DEEP LEARNING APPROACH
During the past few years, many attempts to recognize environmental sounds have been made.
Presently, there is an increasing focus on classifying environmental sounds using deep learning
techniques. the improvements in the field of image classification due to
revolution introduced by deep learning in recent years are leading researchers to start using
images when classifying sounds. The main problem with using deep learning for urban sound
classification is that unlike speech/music which are strongly structured and clearly demarcated
urban sounds does not have any common structure. Furthermore, those sources can, and likely
will, be masked by noise, with many sources of interest, such as air conditioners or engine
sounds, fairly noise-like themselves. The most common deep learning-based approach for
classification of sounds is to convert the audio file to an image, and then use a neural network
to process the image.
As summarized in this paper (https://www.researchgate.net/publication/261208284_Environmental_sound_recognition_A_survey)
there are three broad ways of processing environmental sounds for classification purposes: 
1) Framing-based where the audio signals are separated into frames using a Hamming window. 
Then the features are extracted from each frame and classified separately.
2) Sub-framing-based processing where the frames are further subdivided and each frame is 
classified based on the majority voting of the sub-frames.
3) Sequential processing where the audio signals are divided into segments of typically 30 ms with 50%
overlap. The classifier then classifies the features extracted from these segments. In this project
after framing the samples we convert these audio signals to images by first applying Fourier
analysis to get a spectrogram and then applying cepstral analysis to get MFCCs followed by
feature extraction using pooling functions such as min, max, std that are fed into the network.

# FEATURE LEARNING APPROACH
Using MFCCs as features for deep learning models is indeed a powerful tried and tested
method but these have been shown to be sensitive to the type of background noise found in an
urban environment. Recent studies in audio classification have shown that accuracy can be
boosted by using features that are learned from the audio signal in an unsupervised manner,
with examples in the areas of bioacoustics and music information retrieval. We will explore the application of the 
spherical k-means algorithm as an unsupervised feature learning technique for the classification of urban sonic events. In
particular, we investigate learning features that capture the temporal dynamics of different
sound sources.

# Result
Our experiments found that Deep learning performed better than unsupervised feature
learning on UrbanSound8k dataset.
