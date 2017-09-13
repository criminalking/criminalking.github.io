---
layout: page
title: Projects
permalink: /project/
---
## Egocentric Face Reconstruction with side cameras on VR glasses

`8/2017 - Present` <br>
`Research assistant, advised by Henry Fuchs, Department of Computer Science, University of North Carolina at Chapel Hill`

This project is the beginning of my PhD career. I'm going to use two side-face images captured by two RGB cameras fixed on Hololens to construct user's face. Face reconstruction with side faces is still a challenging problem and nobody can reconstruct a photorealistic face with just side-face images now. But this work is very amazing!!! It could be used on AR telepresence system, just like [Microsoft Research Holoportation project](https://www.microsoft.com/en-us/research/project/holoportation-3/), VR game and so on. Imaging you are in the virtual world, stand in front of the virtual mirror and smile, what do you want to see? Also a smiling man, right? But wait, stay with me. I am working now! <br>
To be continued...

## Motion Capture and Character Animation

`2/2017 - 7/2017` <br>
`Lab work, advised by Yebin Liu, Department of Automation, Tsinghua Univeristy`

System: Mac OS X 10.12 <br>
Programming Language: c++/Python/Matlab

In this project, I captured human motion from a RGB video and then embed it into a static 3D scan human body(We scan human body using our lab's approach) to make this body move. As far as I know, this is the first work to address this task with only one RGB video. I proposed two methods to

Method1:<br> complete it. 


Method2:<<br>
<img src="{{ site.baseurl }}/images/project1_9.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 600px;"/> <br>

* Proposed a new method to address character animation with only one RGB camera(video)
* Integrated shape parameter from human model and pose parameter from video and optimized results with inter-frame information
* Be able to handle apparent occlusion and big range variation of poses

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

<img src="{{ site.baseurl }}/images/project1_9.png" alt="Constructocat by https://github.com/jasoncostello" style="width: 600px;"/>

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
