The problems of speech separation and enhancement concern the extraction of the speech emitted by a target speaker when placed in a scenario where multiple interfering speakers or noise are present, respectively. A plethora of practical applications such as home assistants and teleconferencing require some sort of speech separation and enhancement preprocessing before applying Automatic Speech Recognition (ASR) systems. In the recent years, most techniques have focused on the application of deep learning to either time-frequency or time-domain representations of the input audio signals. In this paper we propose a real-time multichannel speech separation and enhancement technique, which is based on the combination of a directional representation of the soundfield, denoted as beamspace, with a lightweight Convolutional Neural Network (CNN). We consider the case where the Direction-of-Arrival (DOA) of the target speaker is approximately known, a scenario where the power of the beamspace-based representation can be fully exploited, while we make no assumption regarding the identity of the talker. We present experiments where the model is trained on simulated data and tested on real recordings and we compare the proposed method with a similar state-of-the-art technique.


### Method
![Image](figures/pipeline.png)

# Listening tests
Here below we report some audio examples along with the spectrogram of the signals. <br>

For each example the setup with the numner of interferers R, the mixture at the first microhone and the desired target are depicted. <br>
We compare the results of the proposed method with the NBDF approach and the mixture beamformer steered to 90°.

For each setup we report the comparison between the three array configuration used in the validation. Hence, I=4 with d=26mm,
and I=3, I=4 with d=52mm.

<!-- ***************************************** EXAMPLE 1 *************************************************** -->
<table style="width: 100%; table-layout: fixed; word-wrap: normal;">
  <!-- SETUP -->
  <tr> 
    <th colspan="4" style="text-align:center;">EXAMPLE 1</th>
  </tr>
  <tr>
    <td>
      Setup <br>
      SOI=1 <br>
      R=2
    </td>
    <td>
      <img src="examples/exs1/ds1/setup.png" title="setup" width="100%"/>
    </td>
    <td>
      <img src="examples/exs1/ds1/mixture_mic0.png" title="mic0" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds1/mixture_mic0.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <img src="examples/exs1/ds1/target_beamspace.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds1/target_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
  <!-- TITLE 
  <tr> 
    <td>
      Dataset
    </td>
    <td>
      Mixture Beamspace
    </td>
    <td>
      NBDF method
    </td>
    <td>
      Proposed method
    </td>
  </tr>
  -->
  <!-- DATASET 1 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 26mm
    </td>
    <td>
      <img src="examples/exs1/ds1/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds1/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=-3.24dB
    </td>
    <td>
      <img src="examples/exs1/ds1/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds1/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=-0.86dB
    </td>
    <td>
      <img src="examples/exs1/ds1/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds1/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=-0.23dB
    </td>
  </tr>
  <!-- DATASET 2 -->
  <tr> 
    <td>
      I = 3 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs1/ds2/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds2/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=0.74dB
    </td>
    <td>
      <img src="examples/exs1/ds2/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds2/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=3.64dB
    </td>
    <td>
      <img src="examples/exs1/ds2/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds2/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=4.05dB
    </td>
  </tr>
  <!-- DATASET 3 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs1/ds3/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds3/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=1.08dB
    </td>
    <td>
      <img src="examples/exs1/ds3/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds3/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=0.29dB
    </td>
    <td>
      <img src="examples/exs1/ds3/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs1/ds3/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=1.1dB
    </td>
  </tr>
</table>

<!-- ***************************************** EXAMPLE 2 *************************************************** -->
<hr />
<table style="width: 100%; table-layout: fixed; word-wrap: normal;">
  <!-- SETUP -->
  <tr> 
    <th colspan="4" style="text-align:center;">EXAMPLE 2</th>
  </tr>
  <tr>
    <td>
      Setup <br>
      SOI=1 <br>
      R=3
    </td>
    <td>
      <img src="examples/exs2/ds1/setup.png" title="setup" width="100%"/>
    </td>
    <td>
      <img src="examples/exs2/ds1/mixture_mic0.png" title="mic0" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds1/mixture_mic0.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <img src="examples/exs2/ds1/target_beamspace.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds1/target_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
  <!-- TITLE 
  <tr> 
    <td>
      Dataset
    </td>
    <td>
      Mixture Beamspace
    </td>
    <td>
      NBDF method
    </td>
    <td>
      Proposed method
    </td>
  </tr>
  -->
  <!-- DATASET 1 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 26mm
    </td>
    <td>
      <img src="examples/exs2/ds1/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds1/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=3.64dB
    </td>
    <td>
      <img src="examples/exs2/ds1/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds1/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=0.23dB
    </td>
    <td>
      <img src="examples/exs2/ds1/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds1/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=4.51dB
    </td>
  </tr>
  <!-- DATASET 2 -->
  <tr> 
    <td>
      I = 3 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs2/ds2/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds2/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=3.77dB
    </td>
    <td>
      <img src="examples/exs2/ds2/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds2/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=2.92dB
    </td>
    <td>
      <img src="examples/exs2/ds2/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds2/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=8.08dB
    </td>
  </tr>
  <!-- DATASET 3 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs2/ds3/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds3/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=3.55dB
    </td>
    <td>
      <img src="examples/exs2/ds3/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds3/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=1.09dB
    </td>
    <td>
      <img src="examples/exs2/ds3/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs2/ds3/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=4.42dB
    </td>
  </tr>
</table>

<!-- ***************************************** EXAMPLE 3 *************************************************** -->
<hr />
<table style="width: 100%; table-layout: fixed; word-wrap: normal;">
  <!-- SETUP -->
  <tr> 
    <th colspan="4" style="text-align:center;">EXAMPLE 3</th>
  </tr>
  <tr>
    <td>
      Setup <br>
      SOI=1 <br>
      R=0
    </td>
    <td>
      <img src="examples/exs3/ds1/setup.png" title="setup" width="100%"/>
    </td>
    <td>
      <img src="examples/exs3/ds1/mixture_mic0.png" title="mic0" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds1/mixture_mic0.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <img src="examples/exs3/ds1/target_beamspace.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds1/target_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
  <!-- TITLE 
  <tr> 
    <td>
      Dataset
    </td>
    <td>
      Mixture Beamspace
    </td>
    <td>
      NBDF method
    </td>
    <td>
      Proposed method
    </td>
  </tr>
  -->
  <!-- DATASET 1 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 26mm
    </td>
    <td>
      <img src="examples/exs3/ds1/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds1/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi= -
    </td>
    <td>
      <img src="examples/exs3/ds1/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds1/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi=-1.86db
    </td>
    <td>
      <img src="examples/exs3/ds1/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds1/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi=-5.53db
    </td>
  </tr>
  <!-- DATASET 2 -->
  <tr> 
    <td>
      I = 3 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs3/ds2/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds2/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi= -
    </td>
    <td>
      <img src="examples/exs3/ds2/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds2/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi=-0.5db
    </td>
    <td>
      <img src="examples/exs3/ds2/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds2/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi=-2.48db
    </td>
  </tr>
  <!-- DATASET 3 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs3/ds3/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds3/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi= -
    </td>
    <td>
      <img src="examples/exs3/ds3/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds3/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi=-0.06db
    </td>
    <td>
      <img src="examples/exs3/ds3/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs3/ds3/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_soi=-5.54db
    </td>
  </tr>
</table>

<!-- ***************************************** EXAMPLE 4 *************************************************** -->
<hr />
<table style="width: 100%; table-layout: fixed; word-wrap: normal;">
  <!-- SETUP -->
  <tr> 
    <th colspan="4" style="text-align:center;">EXAMPLE 4</th>
  </tr>
  <tr>
    <td>
      Setup <br>
      SOI=1 <br>
      R=1
    </td>
    <td>
      <img src="examples/exs4/ds1/setup.png" title="setup" width="100%"/>
    </td>
    <td>
      <img src="examples/exs4/ds1/mixture_mic0.png" title="mic0" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds1/mixture_mic0.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <img src="examples/exs4/ds1/target_beamspace.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds1/target_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
  <!-- TITLE 
  <tr> 
    <td>
      Dataset
    </td>
    <td>
      Mixture Beamspace
    </td>
    <td>
      NBDF method
    </td>
    <td>
      Proposed method
    </td>
  </tr>
  -->
  <!-- DATASET 1 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 26mm
    </td>
    <td>
      <img src="examples/exs4/ds1/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds1/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=4.87dB
    </td>
    <td>
      <img src="examples/exs4/ds1/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds1/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=1.84dB
    </td>
    <td>
      <img src="examples/exs4/ds1/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds1/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=2.06dB
    </td>
  </tr>
  <!-- DATASET 2 -->
  <tr> 
    <td>
      I = 3 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs4/ds2/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds2/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=4.58dB
    </td>
    <td>
      <img src="examples/exs4/ds2/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds2/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=5.06dB
    </td>
    <td>
      <img src="examples/exs4/ds2/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds2/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=5.14dB
    </td>
  </tr>
  <!-- DATASET 3 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs4/ds3/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds3/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=5.05dB
    </td>
    <td>
      <img src="examples/exs4/ds3/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds3/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=1.33dB
    </td>
    <td>
      <img src="examples/exs4/ds3/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs4/ds3/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      SDR=3.87dB
    </td>
  </tr>
</table>

<!-- ***************************************** EXAMPLE 5 *************************************************** -->
<hr />
<table style="width: 100%; table-layout: fixed; word-wrap: normal;">
  <!-- SETUP -->
  <tr> 
    <th colspan="4" style="text-align:center;">EXAMPLE 5</th>
  </tr>
  <tr>
    <td>
      Setup <br>
      SOI=0 <br>
      R=4
    </td>
    <td>
      <img src="examples/exs5/ds1/setup.png" title="setup" width="100%"/>
    </td>
    <td>
      <img src="examples/exs5/ds1/mixture_mic0.png" title="mic0" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds1/mixture_mic0.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <img src="examples/exs5/ds1/target_beamspace.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds1/target_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
  <!-- TITLE 
  <tr> 
    <td>
      Dataset
    </td>
    <td>
      Mixture Beamspace
    </td>
    <td>
      NBDF method
    </td>
    <td>
      Proposed method
    </td>
  </tr>
  -->
  <!-- DATASET 1 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 26mm
    </td>
    <td>
      <img src="examples/exs5/ds1/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds1/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf= - 
    </td>
    <td>
      <img src="examples/exs5/ds1/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds1/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-7.88dB
    </td>
    <td>
      <img src="examples/exs5/ds1/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds1/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-13.98dB
    </td>
  </tr>
  <!-- DATASET 2 -->
  <tr> 
    <td>
      I = 3 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs5/ds2/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds2/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf= -
    </td>
    <td>
      <img src="examples/exs5/ds2/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds2/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-12.04dB
    </td>
    <td>
      <img src="examples/exs5/ds2/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds2/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-12.59dB
    </td>
  </tr>
  <!-- DATASET 3 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs5/ds3/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds3/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf= -
    </td>
    <td>
      <img src="examples/exs5/ds3/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds3/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-13.46dB
    </td>
    <td>
      <img src="examples/exs5/ds3/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs5/ds3/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-13.68dB
    </td>
  </tr>
</table>

<!-- ***************************************** EXAMPLE 6 *************************************************** -->
<hr />
<table style="width: 100%; table-layout: fixed; word-wrap: normal;">
  <!-- SETUP -->
  <tr> 
    <th colspan="4" style="text-align:center;">EXAMPLE 6</th>
  </tr>
  <tr>
    <td>
      Setup <br>
      SOI=0 <br>
      R=3
    </td>
    <td>
      <img src="examples/exs6/ds1/setup.png" title="setup" width="100%"/>
    </td>
    <td>
      <img src="examples/exs6/ds1/mixture_mic0.png" title="mic0" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds1/mixture_mic0.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
    <td>
      <img src="examples/exs6/ds1/target_beamspace.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds1/target_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
    </td>
  </tr>
  <!-- TITLE 
  <tr> 
    <td>
      Dataset
    </td>
    <td>
      Mixture Beamspace
    </td>
    <td>
      NBDF method
    </td>
    <td>
      Proposed method
    </td>
  </tr>
  -->
  <!-- DATASET 1 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 26mm
    </td>
    <td>
      <img src="examples/exs6/ds1/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds1/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf= -
    </td>
    <td>
      <img src="examples/exs6/ds1/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds1/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-38.16dB
    </td>
    <td>
      <img src="examples/exs6/ds1/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds1/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-43.03dB
    </td>
  </tr>
  <!-- DATASET 2 -->
  <tr> 
    <td>
      I = 3 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs6/ds2/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds2/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf= -
    </td>
    <td>
      <img src="examples/exs6/ds2/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds2/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-24.94dB
    </td>
    <td>
      <img src="examples/exs6/ds2/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds2/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-17.58dB
    </td>
  </tr>
  <!-- DATASET 3 -->
  <tr> 
    <td>
      I = 4 <br>
      d = 52mm
    </td>
    <td>
      <img src="examples/exs6/ds3/mixture_beamspace.png" title="mix_beamspace" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds3/mixture_beamspace.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf= - 
    </td>
    <td>
      <img src="examples/exs6/ds3/nbdf.png" title="nbdf" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds3/nbdf.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-27.78dB
    </td>
    <td>
      <img src="examples/exs6/ds3/proposed.png" title="target" width="100%"/>
      <audio controls>
        <source src="examples/exs6/ds3/proposed.wav" type="audio/mpeg">
        Your browser does not support the audio element.
      </audio>
      R_interf=-22.11dB
    </td>
  </tr>
</table>

