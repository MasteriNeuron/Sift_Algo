<img src="https://img.shields.io/badge/status-Active-green" height="20"> <img src="https://img.shields.io/github/issues/adumrewal/SIFTImageSimilarity" height="20"> <img src="https://img.shields.io/github/stars/adumrewal/SIFTImageSimilarity" height="20"> <img src="https://img.shields.io/github/license/adumrewal/SIFTImageSimilarity" height="20"> <img src="https://img.shields.io/badge/language-python-yellow" height="20">

# SIFTImageSimilarity
This repo provides a working interactive code to use SIFT algorithm for image similarity. I have also presented some of the results. Check them out and let me know if you need something more.

#### Requirements:
- Python 3.9.13
- iPython 8.4.0
- jupyter_client 7.3.4
- matplotlib 3.5.2
- opencv_python 4.6.0.66
- numpy 1.23.1

#### Setup
Just run the following command to install all dependencies:
`sh setup.sh`


## Results
|Image 1 vs Image 2|Match (%)|Similar|
|:-:|:-:|:-:|
|<img src="./data/results/book1vsbook2.png" alt="drawing" width="400"/>|9.75|Yes|
|<img src="./data/results/ironman1vsironman2.png" alt="drawing" width="400"/>|60.86|Yes|
|<img src="./data/results/ironman1vsironman3.png" alt="drawing" width="400"/>|48.14|Yes|
|<img src="./data/results/eiffel1vseiffel2.png" alt="drawing" width="400"/>|0.94|No|
|<img src="./data/results/taj1vsironman2.png" alt="drawing" width="400"/>|0.0|No|
|<img src="./data/results/darkknight1vsdarkknight2.png" alt="drawing" width="400"/>|31.26|Yes|
|<img src="./data/images/robert1.jpeg" alt="drawing" width="200"/><img src="./data/images/tom1.jpeg" alt="drawing" width="200"/>|0.18|No|

The codes available in this repo are tuned such that any score greater than 1.0 means they are a possible match. It works well with rotation and for images captured from different angles as well. However, if it is a 3D object (something with holes/gaps in between) and the view changes completely, it might not be possible for the algorithm to detect stuff. Depending on the use case and how strict you want the comparison, you can tune some parameters and also the cut-off.<br>
**I really wished Robert and Tom to match though** (cries in the corner) #3000

If you want the codes for identifying similar objects like Taj1 vs Taj2 or Eiffel1 vs Eiffel2 (3D objects), feel free to reach out to me. I am working on it parallely.<br>

This algorithm works great when you have descriptors pre-generated for thousands of images and all you want to do is find the images similar a new image.<br>
You can also use the opencv's [FlannBasedMatcher](https://docs.opencv.org/3.4/d5/d6f/tutorial_feature_flann_matcher.html) which is faster in terms of keypoint matching time but a little less accurate.<br>

Thanks to [rmislam](https://github.com/rmislam/PythonSIFT/blob/master/pysift.py) for providing an open-source implementation of the SIFT (David G. Lowe's scale-invariant feature transform) done entirely in Python. I have added it as a commented code, you can use it incase you want to avoid using opencv's implementation. The only drawback right now is, it is very slow compared to opencv's efficient implementation.
And Dr.R.C.PANDAY(R.E.C.AMBEDKAR NAGAR(AKTU)),which gave a great guidence to do this project.