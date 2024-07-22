# Speech-Enhancement-Tensorflow-UNet-Softmask


### Speech Enhancement Algorithm based on Tensorflow and Keras


**Data**
I mixed clean speech data from RAVDESS dataset with noise data from the UrbanSound8K dataset. As tensorflow was unable to read the raw files, I rewrote the original datasets locally and
used it. I also downsampled the datasets back to 8K - this captures most of the Speech signal. 


This is quite a limited dataset for speech enhancement. My goal for this project was primarily to check how well this algorithm generalize to a completely different unseen dataset.

**ALGORITHM** 
This algorithm takes an Short Time Fourier Transform (STFT) of the audio files to return the transformed signal as a 2D array of dimensions time and frequency.
The transformed signal is complex, but the algorithm only operates on the amplitude. The amplitude is passed through a softmask + UNet algorithm. T



**METRIC**
The PESQ metric is used in the industry as an automatic way to measure speech quality. It is not without it's problems but it still works as a first pass. I would advise you to
listen to the output files (clean, corrupted and corrected) to get a better sense of how the algorithm performs.



**Results**
On the validation data, we saw an average increase of +0.44 in the PESQ score (from 2.08 to 2.52)
In the unseen test data, we saw an average increase of +0.17 in the PESQ score (from 2.13 to 2.30)

