<p align="center">
  <img src="chabud_logo.png">
</p>

# ChaBuD Challenge - ECML/PKDD 2023
This repository contains the description of the ChaBuD Challenge, held in conjuction with ECML/PKDD 2023. The content hosted on the HuggingFace competition are reported here.
Consider that a more complete dataset is available [here](https://huggingface.co/datasets/DarthReca/california_burned_areas) and its official TorchGeo implementation. The dataset used for this challenge is contained in the previously linked dataset.


# Announcements
- May 8, 2023: **Public leaderboard is online!** You can now submit your predictions and check the (public) leaderboard! You can find instructions [here](DATASET_DESCRIPTION.md).
- April 11, 2023: **Competition starts!** Data is made publicly available to participants! **Submission page will be enabled in the following days.**


# Motivation
Satellite missions enable large-scale data acquisitions at high resolution in a short amount of time, paving the way for exciting scenarios and applications in the computer vision domain. The capacity to collect continental-scale information represents an extremely valuable resource to researchers and authorities in different contexts.
In Earth Observation, crisis response and disaster management represent relevant topics. Data availability plays a vital role in timely responses and continuous monitoring of areas affected by catastrophic events, such as earthquakes, floodings and forest fires.

In this context, ChaBuD challenge proposes a computer vision task, leveraging raster bi-temporal geospatial data collected from Sentinel-2 L2A satellite imagery. The goal is to identify areas previously affected by forest wildfires over the state of California to support local authorities in monitoring the affected areas and planning the restoration process.

# Task Description
The challenge proposes a binary image segmentation task on forest fires monitored over California.
The goal is to predict whether or not a region was affected by a forest fire, given a pre-fire and post-fire satellite acquisition.
Participants are encouraged to leverage on temporal information to develop change detection models.

# Evaluation
IoU is used for final evaluation. Evaluation score is computed the validation set (public leaderboard) and hidden test set (private leaderboard).

The final evaluation (private leaderboard) admits **only two** submissions for the entire challenge.

# Baseline
Baseline (public) is submitted by user `DarthReca`, with a public score (IoU) of 0.6765. The baseline model used is DeepLabV3+ with ResNet backbone. 

# Participation rules
- Participants are allowed to create teams. Each participant is allowed to be part of a single team only. Teams must be composed of 5 people at most.
- Each team must be registered using the following form: [link](https://forms.gle/oFXcJHnNaVKnvKak8)
- All submissions for each team must be performed by the Team Leader from the HuggingFace user account specified in the Google Form
- Models and code should be able to run on a single GPU
- Use of external data is admitted for training, with the constraint that such data must be either publicly available or released before the end of the competition (June 25, 2023). Additional data must not contain any information related to California (due to possible overfitting)
- **A final report is required for the final submission for evaluation purposes. Solutions must have a written report to be considered for prizes.**
- Participants are asked to publicly release the code associated with the developed models and training procedures before July 15, 2023. Solutions without a code repository will not be considered in the final evaluation.

# Prizes
The challenge is held in conjunction with ECML/PKDD 2023 (Discovery Challenge) in Turin, Italy from September 18, 2023 to September 23, 2023.
To be eligible for prizes, participants' submissions must perform better than the baseline proposed by the organizers **and be registered using the form specified in Participation rules**.

Prizes:
- 1st place: **650€** (gross, ~500€ net) and one full registration to ECML/PKDD 2023 Conference
- 2nd place: **350€** (gross, ~250€ net) and one full registration to ECML/PKDD 2023 Conference
- most innovative and original solution: one full registration to ECML/PKDD 2023 Conference

Monetary prizes are kindly offered by LINKS Foundation and SAFERS project.
Conference registrations are gently provided by the ECML-PKDD organizing committee.

# Report

The reports will be peer-reviewed and each report must complain the following requirements to be accepted: 

- It must be in LCNS format
- It must be at least 6 pages long, references included
- It must include Include clear research objectives, methodology, results, and analysis

# Tentative Timeline
- April 11, 2023: competition starts. Train and validation sets are released
- ~~May 2~~ **May 8, 2023: Submission opens! Public leaderboard is made available**
- **~~June 1~~ June 9, 2023: hidden test set is released (input data only). Private leaderboard is made available.**
- ~~June 10~~ June 18, 2023: end of the challenge
- June 25, 2023: final leaderboard is released
- July 15, 2023: deadline for final report submission
- July 31, 2023: final decision and winners are announced


# Organizers
- Luca Colomba, PhD student, Politecnico di Torino, Torino, Italy
- Paolo Garza, Associate Professor, Politecnico di Torino, Torino, Italy
- Dino Ienco, Senior Research Scientist, INRAE, UMR TETIS, Montpellier, France
- Daniele Rege Cambrin, PhD student, Politecnico di Torino, Torino, Italy
- Claudio Rossi, Senior Researcher, LINKS Foundation, Torino, Italy

This challenge is brought to you by:
<p align="center">
  <img src="polito_logo.png" width="400">
  <img src="inrae_logo.png" width="400">
  <img src="links_logo.png" width="400">
  <img src="safers_logo.png" width="400">
</p>
