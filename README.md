# Speech-Dereverberation
Dereverberation of Speech Signals Using Weighted Prediction Error
# Problem Description

We aim at a statistical model-based dereverberation approach where we try to estimate the late reverberation in a speech signal captured by distant microphones without prior knowledge of the room impulse response, i.e., the transfer function between the speaker and the microphone.


Late reverberations are dense, unaffected by small variations in the arrival time of the speech signal to the microphone, unlike the early reverb parts which look sparse so that their frequency characteristics are greatly affected. We try to estimate the amount of past signal contained in the present signal using a technique called Delayed Linear Prediction(DLP). 

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
    python wpe.py ../wav_sample/sample_4ch.wav
    ```

## Reference

[WPE Speech Dereverberation](http://www.kecl.ntt.co.jp/icl/signal/wpe/)

## Team
 - Sai Rajeswar Maddimsetty
 - Debapriya Tula
 - Hemanth Nani Jella
 - 
