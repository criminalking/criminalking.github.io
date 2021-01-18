---
layout: page
title: Projects
permalink: /project/
---
## High-precision gaze tracking

`9/2018 - 1/2019` <br>
`Research intern, advised by Derek Bradley and Thabo Beeler, Disney Research Zurich`


System: Ubuntu 16.04 <br>
Programming Language: c++/Python/Lua

After coming to Disney Research Zurich, I began to work on a very interesting new topic - Eye tracking. Eye tracking could be used in a wide range of applications, such as human-computer interaction, psycholinguistics, marketing and so on. We are working on tracking eye gaze based on high-fidelity eye model and eye rig. In order to track eye gaze in real-time, we decided to use deep learning method for infering high-accuracy gaze direction.

Images coming soon.

## Egocentric Face Reconstruction with side cameras on Hololens

`8/2017 - 7/2018` <br>
`Research assistant, advised by Henry Fuchs, Department of Computer Science, University of North Carolina at Chapel Hill`

System: Ubuntu 16.04 <br>
Programming Language: c++/Python

This project is the beginning of my PhD career. With the rise of VR/AR, 3D telepresence attracted more and more attention. [Microsoft Research Holoportation project](https://www.microsoft.com/en-us/research/project/holoportation-3/) is one of the good examples. They reconstructed high-quality 3D models of people, compressed and transmitted them to anywhere in the world in real time. This technology allows users to see, hear, and interact with remote participants in 3D as if they are actually present in the same physical space. However, they used multiple RGBD cameras fixed in a room to reconstruct which is limited to professional user and also not convenient to move. What we want to achieve is to reconstruct whole user face, body and environment around the user with only a modified Hololens.

I'm mainly responsible for human face reconstruction. Face reconstruction with side faces is still a challenging problem and as far as I know, nobody has reconstructed a photorealistic face with only side-face images until now. Our video-based face reconstruction pipeline takes as input two synchronized images from the downward-facing cameras, as well as a pre-scan model of the user's face. For each captured time instant, we first detect 2D landmarks in the two images with a finetuned CNN based on side face images, and then compute a deformation of the pre-scan that minimizes the reprojection error between the face model's fiducial 3D landmarks and their corresponding 2D detections. However, full-face reconstruction relying solely on ego-centric views is challenging due to the oblique viewing angles. Moreover, video-based reconstruction is hindered if the face is partially occluded. We address these problems by augmenting the face reconstruction with geometry derived from the captured audio. We trained a CNN to infer expression parameters and combine them with video expression parameters as final result.

<img src="{{ site.baseurl }}/images/project1_11.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 400px;"/> <br>
This is camera installation result of our project. <br>

<img src="{{ site.baseurl }}/images/project1_12.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 400px;"/> <br>
2D facial landmark detection and 3D model fitting results. White points in the first (indoor) and third (outdoor) columns show the 66 2D landmarks. The second and fourth columns show the mesh fitting visualization with all mesh vertices (green) projected into the images.

<img src="{{ site.baseurl }}/images/project1_13.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 400px;"/> <br>
Two video/audio-based fitting results. The first column shows the original image captured by the right side camera, and the second and third columns respectively show reconstruction results using only video or audio. The last column shows the final result of combining video and audio. The top row shows a result where the face is unoccluded; in this case, the combined result closely matches the video-only result. The second row demonstrates the contribution of audio-based capture when the face is partially occluded.

<span style="color:red">News</span> Our paper ***Towards fully mobile 3d face, body, and environment capture using only head-worn cameras*** is accepted by 2018 IEEE Transactions on Visualization and Computer Graphics (TVCG).

## Motion Capture and Character Animation

`2/2017 - 7/2017` <br>
`Lab work, advised by Yebin Liu, Department of Automation, Tsinghua Univeristy`

System: Mac OS X 10.12 <br>
Programming Language: c++/Python/Matlab

In this project, I captured human motion from a RGB video and then embedded it into a static 3D scan human body(We scan human body using our lab's approach) to make this body move. As far as I know, this is the first work to address this task with only one RGB video. I proposed two methods to complete it. The first one extracted 3D skeleton from a RGB video by estimating 2D heatmap. In the meantime, body weights and 3D skeleton was also extracted from 3D static human scan. After this, we computed a transformation matrix between these two 3D skeletons. In the end, we got the result by LBS skinning. Below is the overview of method one. <br>

<img src="{{ site.baseurl }}/images/project1_8.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 900px;"/> <br> <br>

The second method used popular and useful body model SMPL to improve the result of method one. Above all, we infered 2D body joints from RGB video with CNN and then fitted a SMPL body model which contributed its pose parameters. And then we directly fitted a SMPL model to 3D static scan and extracted its shape parameters. The next step was SMPL fusing and added smoothness between consecutive frames which can also discarded odd frames. In the end we used deformation transfer to convert SMPL model to human scan.  Below is the overview of method two. <br>

<img src="{{ site.baseurl }}/images/project1_9.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 900px;"/> <br>

* Proposed a new method to address character animation with only one RGB camera(video)
* Integrated shape parameter from human model and pose parameter from video and optimized results with inter-frame information
* Handled apparent occlusion and big range variation of poses

## Pose Imitation of Robot in ROS System

`7/2016 - 9/2016` <br>
`Research intern, advised by Yuhao Lu, Turing Robot`

System: Ubuntu 16.04 <br>
Programming Language: c++/Python

In this project, I teach robot to imitate human movement(dance) in real-time and then let them teach children dance, which is inspired by my interest in street dance "popping"(i.e. "robot dance"). So we developed a pose estimation system with binocular camera in ROS platform.

* Proposed an algorithm to locate people, match ICP, extract skeleton and compute similarity <br>
* Implemented a 3D body model composed of 10 main body parts to improve results <br>
* Ran at ~5-10 frames per second—the rate of a standard PC—and achieved an accuracy over 90%, thus satisfied the requirements of the industry

(Robots are being produced now. Unfortunately no images are allowed.)

## Offline Ray tracing(Course Work)

`11/2016 - 1/2017` <br>
`Advanced Computer Graphics's Course Work`

System: Mac OS X 10.12 <br>
Programming Language: c++

In this project, I built a system to complete Monto Carlo Ray Tracing.

* Implemented circle, rectangle, and triangle mesh, support texture mapping
* Completed diffuse reflection, specular reflection and refraction
* Used KD-tree to accelerate

<img src="{{ site.baseurl }}/images/project1_6.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 300px;"/> <img src="{{ site.baseurl }}/images/project1_7.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 300px;"/>

## Neural Color Transfer

`9/2016 - 12/2016` <br>
`Lab work, advised by Songhai Zhang, Department of CS, Tsinghua Univeristy`

System: Ubuntu 14.04 <br>
Programming Language: c++/lua

In this project, I transfered style of one photographer to another image. Inputs are many images from one photographer and one test image. We use crawler to get images from flickr and train a neural network to extract style of the photographer.

* Implemented advanced colorization algorithm <br>
* Used CRF method to solve the problem of color bleeding during the transfer <br>
* Trained a new neural network to smooth the result

<img src="{{ site.baseurl }}/images/project1_10.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 600px;"/>

## Image and Video Matting in Real-Time

`3/2016 - 6/2016` <br>
`Lab work, advised by Songhai Zhang, Department of CS, Tsinghua Univeristy`

System: Mac OS X 10.12 <br>
Programming Language: c++

In this project, I used an input image including a person and its trimap to extract the person to a very fine degree.

* Constructed a pipeline to automatically generate trimap, to think over both local and nonlocal methods and the latter consists of sampling-based and affinity-based matting(my work), and to speed up with GPU.
* Improved the algorithm by using the expanded regions to accelerate computing speed

<img src="{{ site.baseurl }}/images/project1_3.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 230px;"/> <img src="{{ site.baseurl }}/images/project1_4.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 230px;"/> <img src="{{ site.baseurl }}/images/project1_5.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 230px;"/>


## An Augmented Reality Technology based on Hand Recognition

`3/2015 - 6/2015` <br>
`33rd Challenge Cup`

System: Windows 8 <br>
Programming Language: c++/qt

In this project, we developed an AR system(also a headset product) integrating camera, computer and projector allowed users to control electronic appliances and play games on the papers, walls or some other normal places.

**Camera**: Detect user inputs, mainly are hand posture information <br>
**Computer**: Handle user inputs(image preprocessing and hand recognition) and generate feedback user wants(e.g. open a video) <br>
**Projector**: Project the virtual information generated by computer to the real world(e.g. Wall/Paper/Curtain) <br>
**Human**: Use hands to click or drag something

This's a diagram showing the structure of our system.

<img src="{{ site.baseurl }}/images/project1_1.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 400px;"/>

This is our poor equipment(lack of beauty, but not heavy).

<img src="{{ site.baseurl }}/images/project1_2.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 400px;"/>

Our product, due to its excellent innovation and practicability, won prizes in the 33rd Challenge Cup of Tsinghua, the Huawei Special Award (5/400), and the EMC Special Award (3/400).


<br>
All the codes above could be found in my Github.
