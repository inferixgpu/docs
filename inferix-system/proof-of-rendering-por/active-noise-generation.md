---
description: >-
  DePIN verification solution: Active Noise Generation and Active Noise
  Verification
---

# Active Noise Generation

Active Noise Generation (ANG) is basically a kind of asymmetric watermarking (e.g. Furon and Duhamel \[1] or Hartung and Girod \[2]) which aims to prevent an attacker knowing the watermarking protocol from bypassing the verification process. Following the main idea of academic research, invisible noise (i.e. below the perceptual capability of human) is added into the carrier signal (audio, video, etc.) so that it cannot be detected without the secret key of the watermarking algorithm. In the traditional context, the watermark maker is always supposed to be the owner of the media. Unfortunately, in the decentralized image/video rendering, noise cannot be added into the rendered media since the rendering processes are decentralized thus public. Inferix’s ANG handles this problem of DePIN verification using a novel technique which adds render-tolerant noise into the scene, before the rendering happens.

## 1. Active Noise Generation

The output of ANG is the coordinates of all N rectangles with dimensions I\*J. The algorithm includes the following steps:

1.1. Insert N noise elements, with a size of I\*J where N, I, and J are parameters tuned via DAO. Typically, I and J must be sufficiently small (e.g., 3\*4).

1.2 Calculate the insertion of these N noise elements into the scene such that:

1.2.1 The noise will always be present in the image (i.e., not obscured by any objects in the scene, and the entire noise element is always in the camera's view).&#x20;

1.2.2 Each noise element in the image will be in the correct rectangular shape (this is achieved by aligning the tilt angle of the noise with the tilt angle of the camera), with the size I\*J.

1.2.3 No two noise elements overlap.

1.3 We currently propose an initial noise pattern that is an image shaped like a bandage.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Proposed initial noise pattern</p></figcaption></figure>

## 2. Active Noise Verification&#x20;

Active Noise Verification (ANV) is an algorithm that ensures the accuracy and completeness of a render task while minimizing computational resource costs. ANV consists of the following steps:

2.1 Input consists of N sets of coordinates calculated by ANG.

2.2 For each set of coordinates, extract a noise window with dimensions 3\*I x 3\*J.

2.2.1 Perform edge enhancement on the noise window, currently using the Laplace filter.

2.2.2 Once the edge enhancement on the noise window is completed, compare the average value of the points in the noise with the average value of the points in the noise window. If this average value exceeds a suitable threshold T, then it is concluded that the noise window contains noise.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Noise window samples</p></figcaption></figure>

## 3. Algorithm Effectiveness Evaluation

3.1. To assess the impact of noise compared to a noise-free image, refer to the following comparison

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

In the image above, the red areas indicate the parts affected by noise. On the left is RGB values of the original image, and on the right is RGB values of the image with noise.

3.2 We can draw following conclusions:

* The impact of noise is very localized. It only causes differences in the specific areas where it is inserted, without affecting the surrounding areas.
* Even within the affected areas, the noise does not cause significant differences. These points ensure that, from the perspective of human perception, there will be no observable differences to the naked eye.
* In the part affected by noise, there will be an effect of creating edges. This is why we chose the initial noise to have a periodic pattern
* The corresponding RGB values of the original image and the noisy image are not too different. However, the RGB values in the column of the noisy image are pushed further apart than in the original image. For example, the first 2 red rows: the original images are \[189 188 175] and \[188 187 174], the noisy images are \[189 188 174] and \[193 191 178]. The difference between \[189 188 175] and \[188 187 174] (in the original image) is not as large as the difference between \[189 188 174] and \[193 191 178] (in the noisy image). This causes a raised edge effect when we apply an edge enhancement filter
* Another way to increase this effect, in addition to the Laplace filter, is to use a filter in the frequency domain (calculate DFT on the noise window).



_\[1] Teddy Furon and Pierre Duhamel. Proceedings of International Workshop on Information Hiding. 1999. An Asymmetric Public Detection Watermarking Technique_

_\[2] Frank Hartung and Bernd Girod. Proceedings of International Conference on Image Processing. 1997. Fast Public-key Watermarking of Compressed Video_
