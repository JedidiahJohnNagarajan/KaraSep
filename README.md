# KaraSep
### We are creating an application in which the music and the sound is separated, similar to a karaoke software.

## Group Members
#### :prince: [Tzu Yu Wang](https://github.com/tw329)             ![](https://komarev.com/ghpvc/?username=tw329&color=red)
#### :princess: [Sahar Qiyash](https://github.com/saharqiyash)            ![](https://komarev.com/ghpvc/?username=saharqiyash&color=green)
#### :prince: [Jedidiah John Nagarajan](https://github.com/JedidiahJohnNagarajan) ![](https://komarev.com/ghpvc/?username=JedidiahJohnNagarajan&color=blue)

## Reach Us:
#### [tw329@njit.edu](https://mail.google.com/mail/?view=cm&fs=1&to=tw329@njit.edu) ✉️, 
#### [sq5@njit.edu](https://mail.google.com/mail/?view=cm&fs=1&to=sq5@njit.edu) ✉️, 
#### [jn34@njit.edu](https://mail.google.com/mail/?view=cm&fs=1&to=jn34@njit.edu) ✉️

### This is class of IS 698 Machine Listening from New Jersey Institute Of Technology, handled by Mark Cartwright ([mark.cartwright@njit.edu](https://mail.google.com/mail/view=cm&fs=1&to=mark.cartwright@njit.edu))

#### It is the study of algorithms for the machine understanding of audio. It's the auditory sibling of computer vision. It has diverse applications such as automatic music transcription, music recommendation, audio search, smart home acoustic sensing, machine condition monitoring, audio captioning, urban noise monitoring, and wildlife monitoring. This course will provide an overview of topics in the field, focusing on the machine understanding of music and environmental sound. Lectures will cover the fundamental problems and classical approaches of the field, as well as the discussion of the field’s recent advances. During the semester, each student will be tasked with presenting one of the field’s recent papers to the class. Assignments in the first half of the course will be Python programming assignments on the fundamentals of the course, and assignments in the second half of the course will consist of milestones and updates on a final group project that students will propose. 


## Motivation
#### One of the main reasons we came up with this idea is because one of the greatest benefits of karaoke is the amount of stress it releases. Since singing usually makes people happy, the level of stress in your body is automatically decreased. At the same time, endorphins are released, and they help reduce both anxiety and stress. Considering the pandemic, everyone is stuck at home and this is a fun way for people to distract themselves.

## Proposed Approach
#### In this project we will train models to separate the vocal and the instrumental part of a song and see how they perform. We will take a .wav file/ YouTube url as input and output the vocal part and instrumental part. Evaluate the output using BSS measure. With the user interface as command line, We will do the project on python. The main package we are using is librosa, numpy, and tensorflow. There are some existing methods used in music separation. We will compare their performance to ours.

## Background
#### Karaoke was invented by a Japanese individual, Daisuke Inoue. The very first karaoke machine was introduced exactly 45 years ago. While the Japanese have customarily enjoyed entertaining dinner guests by singing songs, the notion of using a jukebox that simply played back background recordings, rather than a live band, seemed a bit odd. Inoue, along with his technologically savvy friends, initially assembled eleven 8 Juke machines, as they were originally called, and started renting them out to small drinking establishments in nearby Kobe to see if people would take to them.
+ **https://ieeexplore.ieee.org/abstract/document/6084727?casa_token=kj6sSY_Evx8AAAAA:JUjYQWiVJGPTTNXm9DEHg9NOtlw0pmRQjYZqPAWH-cz8d1uDSr_GRb1ly8lF8U0LdG-lqQ**
+ **https://ieeexplore.ieee.org/abstract/document/6287815**
+ **https://ieeexplore.ieee.org/abstract/document/4694852?casa_token=PMNJCq_Vi08AAAAA:hqpbCMtQS7AfkX2Ph3w3E2l28kbhwSErIDKya91Z1wKRMrjBmxIVa_kkrOp_csuRuDWESQ**

#### There’s many products on the market related to Karaoke such as the JBL Karaoke system.
+ **https://lightyearmusic.com/products/jbl-professional-karaoke-system-bluetooth-mixer-wireless-mics-monitor-and-stand-and-free-karaoke-songs?variant=32241603510366&currency=USD&utm_medium=product_sync&utm_source=google&utm_content=sag_organic&utm_campaign=sag_organic&gclid=Cj0KCQjwjPaCBhDkARIsAISZN7THjb2PzlF3uIw1H1ppihbOK_9MViWI7dWbm_JqLlW8hCEOKT4SR3caApiOEALw_wcB**
+ **https://www.idjnow.com/yamaha-stagepas-600bt-pa-system-with-adapter-and-mics.html?gclid=Cj0KCQjwjPaCBhDkARIsAISZN7TtbvElcVnt6tKscb2_jjhfgnFwkb6mJUVN0s5bQJ62ohZlvarPu6kaAlNMEALw_wcB**

## Training and loss
![trianing loss](https://user-images.githubusercontent.com/13598741/116878917-fc189380-abed-11eb-8821-14163f0106fb.PNG)

## Dataset
#### KaraSep is a service where you can easily separate vocals and music from any song or audio file, allowing you to create a karaoke version of any song. We are using MUSDB18 (https://sigsep.github.io/datasets/musdb.html#musdb18-compressed-stems) for training the system using a dataset which is already labeled. The dataset contains a total 150 full length music tracks encoded in AAC @256kbps, We will separate the MedleyDB into train data, validation data, and test data.

## Evaluation
#### Evaluate the output using BSS measure. There are some existing methods used in music separation. We will compare their performance to ours.

## Challenges
#### Some of our potential challenges include creating a code that will successfully give us the output we are looking for. If we come across any obstacles, we will try to approach the issues in a timely manner that way the final presentation is done by the due date. The dataset MedleyDB contains only 70 tracks with vocals and the number of stereo streams are not always fixed so we decided to go with the dataset professor mentioned, MUSDB18, which contains 150 tracks with vocals.

## Problem we have
#### Setting up the environment is the most difficult part. We tried to run it with tensorflow at first, but kept failing, so we changed it to Pytorch.
#### While building the model, we need to make sure the input dimension and output dimension are correct. Take lots of work to see how other people do it.
#### The original dataset is mp4 files, so we need to convert them into wav files.
#### The most common way to evaluate the result is using SDR, but while using bss_eval_sources in mir_eval, keep seeing value errors that say that the source should be non-silent, but cannot fix it.
#### Training the model uses more power than the charger can charge, so the 75 epochs is the maximum we can achieve. Maybe we can get better results if we solved the mechanical issue.
#### The model could only be applied on the musdb18 dataset. If we tried to use other sources, the results would be very weird. We fix it by double the sample rate while outputting. 

## How to run the code
+ **If just want to try download instrumental versions from Youtube, run**

     ``python test.py .\model.pth``
     
+ **If want to train your own model, run**

     ``python wav.py .\musdb18\ .\musdb18_wav\``
     
+ **To convert the mp4 files to wav files, then run**

     ``python train.py .\musdb18_wav\ .\output\``
     

## Requirements
#### GPU with cuda
#### librosa
#### soundfile
#### pytorch
#### torchaudio
#### youtube-dl

## Reference
+ **https://github.com/f90/Wave-U-Net**
+ **https://github.com/ShichengChen/WaveUNet**
+ **https://github.com/alexeyrodriguez/waveunet**
+ **https://github.com/jnzhng/keras-unet-vocal-separation**
+ **https://github.com/Xiao-Ming/UNet-VocalSeparation-Chainer/blob/master/network.py**







