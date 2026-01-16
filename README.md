# NTIRE-2026-3D-Content-Super-Resolution-Challenge
---

**The 3D Content Super-Resolution (SR) challenge is held as a part of the NTIRE workshop in conjunction with CVPR 2026. The goal of this challenge is to develop methods to recover high-resolution (HR) 3D contents from low-resolution (LR) counterparts.**

## Introduction
---

Beyond traditional images and videos, 3D content has gained immense popularity to provide both appearance and geometry information of the scene. Recent years have witnessed an exponential surge of 3D contents due to advances in 3D generation and reconstruction. Nevertheless, current 3D generation models still suffer relatively low quality. For 3D reconstruction, due to diverse constraints in the real world, the observed multi-view images are usually of low resolution, which ultimately degrades the quality of reconstructed 3D content. In applications like AR/VR, increasing the resolution of these 3D contents is highly demanded to provide immersive experience and help to parse the real world.

Recently, remarkable progress has been achieved in image super-resolution (SR) to improve the visual quality of images. To enhance the quality of a 3D content, a straightforward approach is to employ an off-the-shelf image SR model to super-resolve the rendered images. However, this approach ignores the tightly coupled relationship between geometry and appearance information, resulting in multi-view inconsistency and flicker artifacts.

In this challenge, we aim at establishing a benchmark for 3D content SR. We aspire to highlight the specific challenges and research problems faced by 3D content SR. We hope that this challenge could inspire the community to explore the cross area of low-level vision and 3D vision, and ultimately drive technological advancement in emerging applications such as AR/VR.

## Challenge Description
---

The 8th edition of NTIRE: New Trends in Image Restoration and Enhancement workshop will be held in June 2026 in conjunction with CVPR 2026.

The objective of this challenge is to reconstruct high-resolution (HR) 3D contents from their low-resolution (LR) counterparts. During the development phase, the validation set will be released. The participants can evaluate their models on the validation set by submitting their results to the validation server. Specifically, super-resolved images are rendered using given camera intrinsics and extrinsics and then submitted to the server for online evaluation. During the test phase, the test set will be released, which includes LR 3D content only. Challenge participants should apply their trained models to the LR 3D content to generate super-resolved results. Then, these results are submitted to the server and evaluated by the organizers.

This challenge has two tracks:

**- Track 1: Bicubic Degradation**   
  The aim of this track is to obtain super-resolved 3D content under bicubic degradation (Matlab `imresize` function in bicubic mode).

**- Track 2: Realistic Degradation**    
  The aim of this track is to obtain super-resolved 3D content under realistic degradation.

## Datasets
---

### Track 1: Bicubic Degradation

**(1) Training Set** 
This challenge does not provide a training set and encourages the participants to employ diverse external datasets, including but not limited to image SR datasets, depth map SR datasets, multi-view datasets, and 3D reconstruction datasets, to improve the quality of a 3D content.

**(2) Validation Set** 
The validation set consists of LR 3D contents and HR images/depth maps with their corresponding camera poses. The participants can download the validation set to evaluate the performance of their developed models by comparing their super-resolved images/depth maps with the HR images/depth maps. The participants are encouraged to write papers to describe their methods and use the released validation set for performance evaluation.

**(3) Test Set**  
To rank the submitted models, a test set consisting of two 3D scenes is provided. Unlike the validation sets, only LR 3D contents and a set of camera poses will be released for the test set. The participants must apply their models to the released LR 3D contents and submit their super-resolved images/depth maps at given camera poses to the server.

### Track 2: Realistic Degradation

**(1) Training Set**  
This challenge does not provide a training set and encourages the participants to employ diverse external datasets, including but not limited to image SR datasets, depth map SR datasets, multi-view datasets, and 3D reconstruction datasets, to improve the quality of a 3D content.

**(2) Validation Set**  
The validation set consists of LR 3D contents and HR images/depth maps with their corresponding camera poses. The participants can download the validation set to evaluate the performance of their developed models by comparing their super-resolved images/depth maps with the HR images/depth maps. The participants are encouraged to write papers to describe their methods and use the released validation set for performance evaluation.

**(3) Test Set**  
To rank the submitted models, a test set consisting of two 3D scenes is provided. Unlike the validation sets, only LR 3D contents and a set of camera poses will be released for the test set. The participants must apply their models to the released LR 3D contents and submit their super-resolved images/depth maps at given camera poses to the server.

## Evaluation
---

The objective of this challenge is to reconstruct high-resolution (HR) 3D contents from their low-resolution (LR) counterparts. During the development and testing phase, challenge participants will submit the super-resolved results. Example codes to calculate evaluation metrics can be found [here](https://drive.google.com/file/d/1cYcP898xBpNWR-bGKKyFECymZkieN11a/view?usp=drive_link).

- Track 1: Bicubic Degradation  
  Given multi-view images of a scene, bicubic degradation (Matlab `imresize` function in bicubic mode) is used to generate LR images.

- Track 2: Realistic Degradation  
  Given multi-view images of a scene, a realistic degradation model consisting of random blur, downsampling, noise, and compression is adopted to synthesize LR images.

For quantitative evaluation, we select M camera poses for each test 3D content to render M images and corresponding depth maps. Then, PSNR is used to evaluate the visual quality, while EPE is employed to assess geometry accuracy. The final score for ranking is calculated as:
<div align="center">
  <img src="https://github.com/user-attachments/assets/8ae7da97-a497-44af-b98b-40dc9f6c1e79" width="350" />
</div>

## Submission
---

During the development phase, participants can submit their results on the validation set to get feedback from the Codabench server. During the test phase, participants will submit the whole results of the test set. This should match the last submission to Codabench.

The submitted results should contain images and depth maps rendered from the super-resolved 3D content under given camera intrinsics and extrinsics. The terminology of the rendered images and depth maps should be identical to that of the camera intrinsics and extrinsics in the validation and test sets.

When submitting the results, create a ZIP archive containing all the resulting images and depth maps. A valid example dummy submission file can be found [here](https://www.jianguoyun.com/p/Dfe7flkQleb6DRjY1ZkGIAA).

After the test phase, the participants will 1) fill in an [online form](https://www.jianguoyun.com/p/Dfe7flkQleb6DRjY1ZkGIAA) and 2) submit a zip file (containing fact sheet, source code, and final results, an example of fact sheet can be found [here](https://www.jianguoyun.com/p/DbxH8hgQleb6DRi_6pgGIAA) to the official submission account (ntire.3dsr@outlook.com) by email. The final submission should be made by the following rules:

  (1) The submitted results must be from the same method that generated the last submission to Codabench. Consistency will be checked; otherwise, the submission is invalid.  
  
  (2) Both testing source code (or executable) and training code must be submitted. Reproducibility is required.  
  
  (3) Fact sheet describing the method details should be submitted together. The factsheet format is provided with data. Participants must submit a compiled PDF file and the TeX source. Figures and image sources should be enclosed.  

Each participating team in the final testing phase should use the provided factsheet template to describe their solution(s).

**Email submission format:**  
Please use the following format to submit your final results, fact sheet, code, and model (with trained parameters). We will run the test code to reproduce the results. The code and the model will be posted on the NTIRE 2026 website.

To: ntire.3dsr@outlook.com
CC: your_team_members
Title: [NTIRE 2026 3D Content Super-Resolution Challenge (Track *)] - [Team_name]
body should include:

  1. The challenge name (including track id)
  2. Team name
  3. Team leader's name, affiliation, and email address
  4. Team members' names, affiliations, and email addresses
  5. User name on the NTIRE 2026 Codabench leaderboard (if any)
  6. Executable/source code attached or download links
  7. Fact sheet attached
  8. Download link to the results

It should be noted that the top ranking participants should publicly release their code (or executables) under a license of their choice, taken among popular OSI-approved licenses ([http://opensource.org/licenses](http://opensource.org/licenses)), and make their code (or executables) online accessible for not less than one year following the end of the challenge. (Applies only for the top three ranked participants of the competition.)

## Important Dates
---

- 2026-01-15: Release of training and validation data;
- 2026-01-30: Validation server online;
- 2026-03-10: Final test data release, validation server closed;
- 2026-03-17: Test result submission deadline;
- 2026-03-18: Fact sheet / code / model submission deadline;
- 2026-03-19: Test preliminary score release to participants;
- 2026-03-24: Challenge paper submission deadline;
- 2026-03-31: Paper decision notification;
- 2026-04-10: Camera-ready;
- 2026-06-18: Workshop day (TBU);
  
## Group number policy
---

Each group cannot have more than six group members (i.e., 1 to 6 group members is OK), and each participant can only join one group. Each group can only submit one algorithm for final ranking.

## Organizers
---

- Longguang Wang (wanglongguang15@nudt.edu.cn)  
- Yulan Guo (yulan.guo@nudt.edu.cn)  
- Yingqian Wang (wangyingqian16@nudt.edu.cn)  
- Juncheng Li (cvjunchengli@gmail.com)  
- Sida Peng (pengsida@zju.edu.cn)  
- Ye Zhang (zhangy2658@mail.sysu.edu.cn)  
- Radu Timofte (Radu.Timofte@vision.ee.ethz.ch)  

## NTIRE 2026 Terms and Conditions
---

The terms and conditions of this challenge can be viewed [here](https://www.codabench.org/competitions/12695/?secret_key=84291672-bbd8-4b1b-8c23-0964a92f96ae).

## Official Repository
---

NTIRE 2026: 3D Content Super-Resolution Challenge

