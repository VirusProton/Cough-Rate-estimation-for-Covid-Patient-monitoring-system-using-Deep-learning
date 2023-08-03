## `This is a part of the project titled "Real Time Covid Paitent Monitoring".`
**Details of the full project can be found in `Covid Patient Monitoring.pdf` file**

# Cough-Rate-estimation-using-Deep-learning-for-Covid-Paitent

For Covid patient monitoring, measuring cough rate is a cruical and important task. By monitoring cough rate we can decide different conditon of the paitient. In this project we tried to measure cough rate in real time. 

For cough rate measuring we trained a deep learning model which can effectively detect cough from the audio input. Details of the dataset can be found <a href= "https://research.google.com/audioset/dataset/index.html">here </a>. We tried to build a robust model sothat it can differentiate cough from other sounds like sneeze, talking, background noise, intrumental noise etc . <br>
**Detailed explanation of the dataset preparation can be found <a href= "https://github.com/Forsad/FluSense-data">here</a>.**

### Dataset and Training Process
We used `YAMNet` as our base network which is a modified version of `Mobilenet_v1` for audio data classification. As our works is a work for audio classification, whether the incoming audio is cough or not, we used some layer on top of the base YAMNet, as YAMNet is designed for classifying 521 audio event classes.

We used `AudioSet` dataset released by `Google` as our training data. Main Audioset consists of `521 classes` which is firmly annotated. We only used a fraction of that dataset. We used cough data as positive event and sneeze, sniffle, breathe, hiccup, gasp, silence and speech audio data as negative event.


**Dataset Distribution**:<br>
`Train:`- <br>
  Cough= 4926 <br>
	Other= 5530 <br>
`Validation:`- <br>
  Cough= 1231 <br>
	Other= 1777 <br>

### Training results:
We trained our model got around `88.43% accuracy` on our validation dataset. <br>
There are some results of our model. 

| **Metric**                                                                   | **Result** |
|:----------------------------------------------------------:|:--------------------------------
| Accuracy                                                                       | 88.43 %          |
| Precision                                                                      | 93.58%         |
| Recall                                                                         | 77%          |
| F1 score                                                                       |84.4%          |

### Inference
For running inference run <a href= "./final_cough_rate_notebook.ipynb">final_cough_rate_notebook.ipynb</a> notebook.

##
N.B: `pyfirmata` module was used to connect the device with arduino to show the results in a LCD display also blink an LED for extreme case.
