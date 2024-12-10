---
title: "Complete: Learning process of classical conditioning"
date: 2022-08-25T00:00:00+09:00
draft: false
tags: [Complete, Database]
images: [スクリーンショット_2022-08-24_1.10.46.png]
description: Classical conditioning experiments were conducted on head-fixed mice. Two different sounds, 6 kHz and 10 kHz, were presented as the conditioned stimulus (CS), and water was rewarded 70% of the time for 6 kHz and 30% of the time for 10 kHz, respectively, as the unconditioned stimulus (US). This experiment was conducted on two individual mice for about 30 minutes for a total of 17 days to record the learning process of classical conditioning. During this recording experiment, brain activity was measured throughout the cortex using a wide-field 1-photon microscope (Wide-field 1p) with a Ca2+ probe. In addition, video data (Face Camera, Body Camera) of the face and upper body of the mice were measured. Behavioral data of the mice were measured in terms of the timing of the clicks and rewards (Behavior data). The sample data is provided under a Creative Commons license for one session per individual on the 10th day after the completion of classical conditioning learning in the measurement system. In Kondo et. al. 2021, we analyzed the neural activity of one-photon and two-photon images only after learning classical conditioning in a similar paradigm, and found that the dorsal medial frontal cortex (dmFrC) is the starting point of reward-expectant behavior. In the Complete dataset, which will be shared with other researchers, we used the same measurement method as Kondo et. al. 2021 and measured the changes in brain activity leading up to the learning process.
---

- Animal: Mouse
- Brain regions: Whole Cortex
- Experiments: Body Camera, Face Camera, Lever-pull, Wide field 1p
- Task: Classical Conditioning, Learning Process
- Publication date: August 25, 2022
- Authors: Masanori Matsuzaki, Masashi Kondo
- Data size (GB): 612
- Indivisuals: 2
- Session: 34

## Abstract

Classical conditioning experiments were conducted on head-fixed mice. Two different sounds, 6 kHz and 10 kHz, were presented as the conditioned stimulus (CS), and water was rewarded 70% of the time for 6 kHz and 30% of the time for 10 kHz, respectively, as the unconditioned stimulus (US). This experiment was conducted on two individual mice for about 30 minutes for a total of 17 days to record the learning process of classical conditioning. During this recording experiment, brain activity was measured throughout the cortex using a wide-field 1-photon microscope (Wide-field 1p) with a Ca2+ probe. In addition, video data (Face Camera, Body Camera) of the face and upper body of the mice were measured. Behavioral data of the mice were measured in terms of the timing of the clicks and rewards (Behavior data). The sample data is provided under a Creative Commons license for one session per individual on the 10th day after the completion of classical conditioning learning in the measurement system.

In Kondo et. al. 2021, we analyzed the neural activity of one-photon and two-photon images only after learning classical conditioning in a similar paradigm, and found that the dorsal medial frontal cortex (dmFrC) is the starting point of reward-expectant behavior. In the Complete dataset, which will be shared with other researchers, we used the same measurement method as Kondo et. al. 2021 and measured the changes in brain activity leading up to the learning process.

![スクリーンショット 2022-08-24 1.10.46.png](スクリーンショット_2022-08-24_1.10.46.png)

## Complete dataset

### Download

Currently, we are distributing the data for internal sharing in collaboration with the Matsuzaki Laboratory of the University of Tokyo or within the Academic Transformation Area A "Behavioral Change Biology". We will send the directory structure of the Data Description and the link to access the file to those who share it, so please download the file by yourself.

We plan to make the files available to the public under a Creative Commons license around the time when the second semester of the "Biology of Behavioral Transformations" project is open for submissions. However, this schedule is subject to change.

### Data License

Since joint research is expected, please consult with the secretariat if necessary.

[braidynbcd@m.u-tokyo.ac.jp](mailto:braidynbcd@m.u-tokyo.ac.jp)

### Term of Use

Please cite: Kondo, M., & Matsuzaki, M. (2021). Neuronal representations of reward-predicting cues and outcome history with movement in the frontal cortex. *Cell Reports* , *34* (5), 108704. doi: https://doi.org/10.1016/j.celrep.2021.108704

## Data Description

### Directory structure of complete dataset

The Complete dataset link provides access to three directories: 1_Raw, 2_Preprocessed, and 3_ROIsegmentation. Of these, 2_Preprocessed is currently not implemented.

- *Under 1_Raw, there are three directories: Behavor for Behavior data, CaData for Wide Field 1p, and Video for Body and Face Camera. The directory is divided into three directories: Behavior, CaData, and Video. Under each of these directories are directories with individual numbers (RCTg_Pv12 and RCTg_Pv13), and under each of these directories are subdirectories divided by date, which contain the datasets described in the Raw data of the Sample dataset.

In the **3_ROISegmentation directory** you can access the data after processing. All frame rates were aligned to 30 Hz and the following processing was performed: 1. shaking correction, 2. alignment to Allen CCF, 3. left hemisphere only clipping, 4. SVD → reconstruction and denoising with top 24 singular values, 5. per pixel, per time point -15 to +15 F for the 10th percentile of the time window of -15 to +15 s, and dF/F for the 10th percentile of the time window of -15 to +15 s. Also (pre-training: 3 sessions, here both sounds, 100% reward probability). under 3_ROISegmentation there is a date directory under the individual number directory, in which the Processed data is stored as mat files.

### File description of sample data

Two mouse populations, RCtg_Pv12 and RCtg_Pv13, were each measured for a total of 17 days. 4 sessions were measured per day.

#### **Raw data**

**Body Camera Movie: Cam1-180623_RCtg_Pv12.avi**

Video data of the ventral side of the mouse during the experiment during 1Session, measured at 30 Hz by camera.

**Face Camera Movie: Cam2-180623_RCtg_Pv12.avi**

Video data of the left side face of the mouse during the experiment during one session, measured by camera at 30 Hz.

**Wide Field 1p: 180623_RCtg_Pv12*.tif**

TIFF image data of Ca2+ probe excitation light in the bilateral cerebral cortex from the upper side of the mouse during the experiment in 1Session, measured at 30 Hz with a one-photon microscope. The data is divided into four TIF files of up to 2 GB in size, and those marked X2, X3, and X4 at the rear of the file name are each a temporally contiguous image file.

**Behavior data: 180623_RCtg_Pv12_kondo_5000Hz.lvm**

Behavioral data (analog voltage recorded via AD converter) measured at 5000 Hz for timing of licks and rewards, to be read in MATLAB, using https://jp.mathworks.com/matlabcentral/fileexchange/19913-lvm-file-import

*Segment1.data is a matrix where **rows are the number of frames and columns are the recording channels, and the following values are stored (meaning HIGH=5V, LOW=0V).

**ch.1**: lick sensor (raw), HIGH when the mouse tongue is in contact with the spout, LOW when not.

**ch.2**: Reward, the moment it goes HIGH, the pump is driven.

**ch.3**: Sound, the sound of ch.7 is sounding while the pump is HIGH.

**ch.4**: Imaging frame, acquired when HIGH. HIGH = approx. 3V only for this channel.

**ch.5**: lick sensor (binary), 1 when the mouse tongue is in contact with the spout, 0 when not.

**ch.6**: sound presentation + delay period flag, 2 indicates sound presentation + delay period, 1 indicates other period (actually this ch is not used for analysis).

**ch.7**: Sound frequency (When ch.3 is HIGH, this channel is sounding. Unit kHz)

#### Analyzed data

**stdData_(day)_(id).mat**

**stdData**（structure）

**fct3** (cell array): Neural activity for each ROI (pixel-averaged dF/F within ROI, Z-scored for the whole time series), aligned with the beginning of the sound for each trial. The elements of the cell array correspond to the "extracted trial type" and are [A+, A-, B+, B-, actual trial series] (+/- corresponds to the presence or absence of reward, respectively). Each cell is a 3-dimensional array. Frame x ROI x Trial structure. Aligned with sound onset, -6 to 8 s. Therefore, the number of frames is 301.

**flt3**（cell array）：Similar to fct3, but instead of neural activity, licking (continuous value as lick-rate, then Z-scored) is included.

**SVDresult** (structure): Result of SVD on the original image stack (process 3). Up to 1000 singular value tops are stored for each component to reduce data volume. The singular value matrix S contains only diagonal elements.

**videoSVD** (Structure) SVD of the video Motion Energy, generated by FaceMap. Top 10 singular values.

**Smode** (Cell array): Spatial mode, by upper body, nose, mustache, and mouth.

**Tmode** (Cell array): Time mode by trial type. (cell array): spatial mode, by upper body, nose, whiskers, and mouth (cell array): temporal mode, by trial type.

※Using the data in this field, it is possible to reconstruct the non-ROI areas (except for the right hemisphere) using up to arbitrary singular values.．

**ROIs** (Array): ROI mask Number of ROIs xY (vertical dimension of acquired image) xX (horizontal dimension of acquired image)

**Bhv** (Structure): Each event occurrence state extracted from the action data, Licking, etc.

**Ds** (structure): The actual behavioral data (analog voltage from sensors, etc.) is sampled at 5 kHz, which is different from the sampling rate of the imaging data. Therefore, the behavior data is downsampled to 30 Hz by referring to the timing of each frame acquisition of the imaging. The contents include: Licking (raw data, analog voltage from sensors), Licking frequency (calculated from Licking), reward, sound A, sound B.

**Idx** (Structure): Presentation state of reward, sound A, and sound B in all trials.

**TrigF**(structure): Event onset for field name (corresponds to position in imaging frame); CS onset for each US condition (A+, B-, etc.) is also available. For example, CueA_nR is the onset of sound A when sound A is presented and then there is no reward. _R" corresponds to rewarded and "_nR" corresponds to unrewarded.

**t_type**(Array): Trial type. The values from 1 to 4 correspond to [A+, A-, B+, B-] (+- corresponds to the presence or absence of reward). The order in the array corresponds to the order in which they occurred in the actual task.

**params (Structure): Parameters related to imaging**．

**d1/d2**：Number of pixels in the imaging image (only the left hemisphere is extracted by preprocessing).

**T**：Number of image frames

**Frate**：Sampling rate

## Results

![スクリーンショット 2022-08-14 13.42.43.png](スクリーンショット_2022-08-14_13.42.43.png)

Schematic of classical conditioning task with different reward probabilities, with higher probability of reward after 6kH of sound presentation.

![スクリーンショット 2022-08-14 13.39.34.png](スクリーンショット_2022-08-14_13.39.34.png)

Lick changes between 6kHz (red) and 10kHz (blue) as the number of sessions (days) elapses, showing that the number of Licks is the same for each sound in the early stages of Lick learning, but that the 6kHz sound learns significantly more Licks as the days elapse. The data presented here is from one individual in Session 7.

## Method

### Processing of Wide-field 1 photon image

Each image stack was aligned to the Allen Common Coordinate Framework version 3 (Allen CCF) top view using 10 feature points. Feature points were set at the bilateral anterior ganglia of the (FrC) olfactory bulb, the central and lateral ends of the frontal vessels, the lambda suture, the bilateral posterior ends of the dorsal cortex, and the bilateral lateral ends of the dorsal cortex. Masks for the cortex were created from the Allen CCF to exclude fluorescence changes in the outer cortical pixels. Only the activity of pixels in the left hemisphere was used. Singular value decomposition (SVD) of the image stack was computed for noise reduction and the image was reconstructed from the top 24 singular values; the SVD results yielded a spatial component U (size pixel x component), a singular value S (size spatial component x temporal component), and an inverted temporal component VT (size component x frame ) are obtained.

Using the reconstructed data, the change in fluorescence intensity (Δ F / F) was calculated for each pixel using the 10th percentile values at ± 15 second intervals before and after each frame.For the analysis using ROIs, 12 ROIs (10 x 10 pixels, rectangular) were set up in the brain regions described below, with localization coordinates were defined according to the top view of the Allen CCF and previously reported areas, which were identified anatomically and functionally: dmFrC (AP +2.8 mm, ML 0.8 mm); dlFrC (AP +2.5 mm, ML 2.0 mm); M1 (AP +1.2 mm, ML 1.0 mm); primary somatosensory forelimb region (S1FL, AP +0.4 mm, ML 2.2 mm). Primary somatosensory hindlimb area (S1HL, AP -0.5 mm, ML 1.5 mm). Primary somatosensory cortex mouth area (S1m, AP +1.4 mm, ML 3.0 mm). Primary somatosensory cortex nasal area (S1n, AP 0 mm, ML 3.4 mm); primary somatosensory cortex barrel area (S1b, AP -1.2 mm, ML 3.0 mm). Primary auditory cortex (Aud, AP -2.5 mm, ML 4.0 mm). Primary visual cortex (Vis, AP -4.0 mm, ML 2.2 mm). Posterior parietal cortex (PPC, AP -2.0 mm, ML 2.0 mm). Posterior cerebral cortex (RSC, AP -2.4 mm, ML 0.5 mm). The stereotactic coordinates here refer to the center position of the ROI.

For each session and mouse, the position of the ROI was fine-tuned manually. The fluorescence intensity of each ROI was determined by averaging the included pixels; the neural activity extracted from the ROI was converted to a Z-score and adjusted for the onset of each cue tone. For each pixel, the 10th percentile of the time window from -15 to +15 s for each time point was converted to dF/F as F

### Processing of Face and Body camera image

Video obtained from the high-speed camera was processed with the FaceMap package ( Stringer et al., 2019 ; https://github.com/MouseLand/FaceMap ) to identify mouth, nose, beard, and upper body parts.ROIs were set for the forelimbs and chest, nose, mouth and beard pads, and the SVD of the kinetic energy (absolute difference between frames) of each ROI was computed. The software generated a "motion mask" calculated from the spatial component U and the singular value S. The time series of separable motions in singular value space, found by the SVD, were calculated by multiplying the motion mask by the original time series data.

## Reference

Kondo, M., & Matsuzaki, M. (2021). Neuronal representations of reward-predicting cues and outcome history with movement in the frontal cortex. *Cell Reports* , *34* (5), 108704.