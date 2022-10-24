The problems of speech separation and enhancement concern the extraction of the speech emitted by a target speaker when placed in a scenario where multiple interfering speakers or noise are present, respectively. A plethora of practical applications such as home assistants and teleconferencing require some sort of speech separation and enhancement preprocessing before applying Automatic Speech Recognition (ASR) systems. In the recent years, most techniques have focused on the application of deep learning to either time-frequency or time-domain representations of the input audio signals. In this paper we propose a real-time multichannel speech separation and enhancement technique, which is based on the combination of a directional representation of the soundfield, denoted as beamspace, with a lightweight Convolutional Neural Network (CNN). We consider the case where the Direction-of-Arrival (DOA) of the target speaker is approximately known, a scenario where the power of the beamspace-based representation can be fully exploited, while we make no assumption regarding the identity of the talker. We present experiments where the model is trained on simulated data and tested on real recordings and we compare the proposed method with a similar state-of-the-art technique.


### Method
![Image](figures/pipeline.png)

# Listening tests

<audio controls>
<source src="../examples/ex1/ds1/mixture_mic0.wav" type="audio/mpeg">
Your browser does not support the audio element.
</audio>


| Setup                     | Mixture mic 1   | Desired Target      |
| :----:                    |    :----:       |     :----:          |
| <img src="../examples/ex1/ds1/setup.png" title="setup" width="50%"/>     | <img src="../examples/ex1/ds1/Mixture_Mic_0.png" title="mic0" width="100%"/> | <img src="../examples/ex1/ds1/Target_beamspace.png" title="target" width="100%"/> |
| **Mixture beamsapce**     | **NBDF method** | **Proposed method** |

