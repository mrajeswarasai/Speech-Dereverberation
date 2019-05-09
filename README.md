# Speech-Dereverberation
Dereverberation of Speech Signals Using Weighted Prediction Error
# Variance-normalized Delayed Linear Prediction Algorithm(Frequency Domain)
This program is an implementation of variance-normalizied delayed linear prediction in time-frequency domain, which is aimed at speech dereverberation, known as weighted prediction error (WPE) method.


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

 Nakatani T, Yoshioka T, Kinoshita K, et al. Speech Dereverberation Based on Variance-Normalized Delayed Linear Prediction[J]. IEEE Transactions on Audio Speech & Language Processing, 2010, 18(7):1717-1731.
