# Simple-Stereo-Vision-Demo
<p align="center">
  <a href="https://github.com/mhd-medfa/Simple-Stereo-Vision/commits/master" target="_blank">
    <img src="https://img.shields.io/github/last-commit/mhd-medfa/Simple-Stereo-Vision?style=flat-square" alt="GitHub last commit">
  </a>

  <a href="https://github.com/mhd-medfa/Simple-Stereo-Vision/issues" target="_blank">
    <img src="https://img.shields.io/github/issues/mhd-medfa/Simple-Stereo-Vision?style=flat-square&color=red" alt="GitHub issues">
  </a>

  <a href="https://github.com/mhd-medfa/Simple-Stereo-Vision/pulls" target="_blank">
    <img src="https://img.shields.io/github/issues-pr/mhd-medfa/Simple-Stereo-Vision?style=flat-square&color=blue" alt="GitHub pull requests">
  </a>

  </br>

  <a href="https://github.com/mhd-medfa/Simple-Stereo-Vision#contribute" target="_blank">
    <img alt="Contributors" src="https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square">
  </a>

  <a href="https://github.com/mhd-medfa/Simple-Stereo-Vision/blob/master/LICENSE" target="_blank">
    <img alt="LICENSE" src="https://img.shields.io/github/license/mhd-medfa/Simple-Stereo-Vision?style=flat-square&color=yellow">
  <a/>
</p>

The provided dataset contains left and right images in two different folders with the same name. For this task please select image pair corresponds to your id (`0000[Id].png`). You need to use 8 point algorithm in order to find the fundamental matrix. For the initial key points detection (minimum 8 corresponding points) you can either do it manually or use any key points detection technique. Next step is to estimate the disparity map for the selected image pair. You may assume the baseline of the stereo camera as the 10cm and focal length of both the left and right side cameras as 2.8mm.


Firstly, we needed to find the Fundamental matrix

I used SIFT algorithm to determine key points

Next Step is to match two arrays with points to find corresponding one. for that I used K-Nearest Neighbor from opencv (`cv2.FlannBasedMatcher`)

And after that we create arrays of corresponding points xl, yl, xr, yr. One point has 2 different pairs of image coordinates on the left and right pictures.

Now find the Fundamental matrix F by using the 8-points algorithm. The idea is to solve a system of homogeneous linear equations by using SVD.

Draw epilines on the left and right images

Let's Find epilines corresponding to points in right image (second image) and drawing its lines on left image, and vice versa.

![](https://i.ibb.co/wcSRHkJ/epilines.png)

Now let's estimate the disparity map for the selected image pair with disparity map we can estimate the depth (the distance) to any point.

since:

`depth = (f ∗ b) /(xl − xr)`

where `xl − xr` is also called as disparity.

![](https://i.ibb.co/m8HcRk3/disparity-map.png)

  
### If you like what I do and you want to support me:

Bitcoin address: <a href="bc1q5cjffml32qrvks3xd0hyau8jx3gf5cd04hrn77">
  <img align="left" alt="Bitcoin" width="22px" src="https://raw.githubusercontent.com/mhd-medfa/mhd-medfa/main/assets/bitcoin.svg.png" />
</a>
<mark>`bc1q5cjffml32qrvks3xd0hyau8jx3gf5cd04hrn77`</mark>

Litecoin address: <a href="ltc1q9l4dr8jdtcakhe8qekep9lfwpgscpllxv5zy27">
  <img align="left" alt="Litecoin" width="22px" src="https://raw.githubusercontent.com/mhd-medfa/mhd-medfa/main/assets/litecoin.svg.png" />
</a>
<mark>`ltc1q9l4dr8jdtcakhe8qekep9lfwpgscpllxv5zy27`</mark>

Tether address: <a href="0x0006a16f43D0fdf480bCc88D4398Fe73D6806fc9"> 
  <img align="left" alt="TetherUSD" width="22px" src="https://raw.githubusercontent.com/mhd-medfa/mhd-medfa/main/assets/tether.svg" />
</a>
<mark>`0x0006a16f43D0fdf480bCc88D4398Fe73D6806fc9`</mark>
