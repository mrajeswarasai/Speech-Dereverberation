# Speech-Dereverberation
Dereverberation of Speech Signals Using Weighted Prediction Error
# Problem Description

We aim at a statistical model-based dereverberation approach where we try to estimate the late reverberation in a speech signal captured by distant microphones without prior knowledge of the room impulse response, i.e., the transfer function between the speaker and the microphone.


Late reverberations are dense, unaffected by small variations in the arrival time of the speech signal to the microphone, unlike the early reverb parts which look sparse so that their frequency characteristics are greatly affected. We try to estimate the amount of past signal contained in the present signal using a technique called Delayed Linear Prediction(DLP). 

# Existing Solutions and Background

There have been quite a lot of approaches to this problem, like estimating the room transfer function using a microphone array and estimating the directions  of arrival (DOA) and enhancing the signal component coming from source by controlling the directivity of microphone. The drawback is it requires a large number of microphones to obtain sufficient directivity gain.



The next idea was  finding the inverse characteristics of reverberation(called inverse filtering). However, it does not work so well when the reverberation characteristics change, e.g., due to small positional differences of the speaker or the microphone. 



Multichannel linear prediction: The source signal is assumed to be independent and identically distributed(iid). It can estimate the channels without any prior knowledge of the signals characteristics. The drawback of this approach is that speech signal is not an iid sequence and this method cannot thus be directly applied to speech signals.

# Methodology

The method we have used is known as the  weighted prediction error(WPE) which is an improvisation over the multichannel linear prediction mentioned earlier by dividing the speech signal into small time frames and resolving it in the frequency domain. 


We cannot use Fourier Transformation right away due to the varying nature of frequency of speech signal with time. So we divide the signal into frames and apply FFT to it using STFT. To this we can then apply WPE to each frame which estimates the amount of past signal in the present (a Gaussian function with certain mean and variance is estimated) based on a prediction order. After this, we can subtract the estimation for a time frame and henceforth.



With DLP, the reverberation can be divided into two parts, viz, early and late reverb. It can be shown that DLP can suppress the late reverb effectively without significantly distorting the short time correlations of the speech, with the assumption that speech is stationary. With the use of time-varying speech characteristics with multichannel linear prediction, the reverbs have been reduced to a significant extent.


# Results

We have recorded voice samples on our phones(non-reverberant), added reverb to them using a software known ‘Audacity’, fed this reverberant signal through the algorithm and evaluated the reverb-free reconstructed signal for similarity with the original reverb-free signal. We are finding mean absolute error( (1/m) * ( | original_signal[i] - reconstructed_signal[i] | ) for all i in m) at each discrete point and finding the percentage error.



We see that there is around 65-80 % accuracy in the results.



The signal plotted in the top part of the image is the original signal containing reverb and the signal below that is the one with the 
reverb removed. It is a frequency(kHz) vs time(sec) graph

![alt text](https://firebasestorage.googleapis.com/v0/b/vnpr-ed411.appspot.com/o/graph.png?alt=media&token=cdd928b0-3260-44fb-b70a-c563ffb1045e)



## Requirements
 - Python 3.x
 - Numpy
 - soundfile
 - matplotlib (Optional) 

## Run the Demo
  - Usage:
    ```bash
    python wpe.py [-h] [-o OUTPUT] [-m MIC_NUM] [-n OUT_NUM] [-p ORDER] filename
    ```
  - To use the default configrations and the given audio sample, run:
    ```bash
    python wpe.py ../wav_sample/my_sample.wav
    ```

## Reference

[WPE Speech Dereverberation](http://www.kecl.ntt.co.jp/icl/signal/wpe/)

## Team
 - Sai Rajeswar Maddimsetty
 - Debapriya Tula
 - Hemanth Nani Jella
 - Deepesh Bhageria
