# SENSORIUM+ 2022 Competition Submission

<a href="https://github.com/psf/black"><img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg"></a>
[![hub](https://img.shields.io/badge/powered%20by-hub%20-ff5a1f.svg)](https://github.com/activeloopai/Hub)

## Contents

1. [Overview](#1-overview)
2. [Setup Instructions](#2-setup-instructions)
3. [Experiments](#3-experiments)

## 1. Overview

![Fig1](https://user-images.githubusercontent.com/102295389/205992650-ce6d5b0f-99b6-4e25-b88d-7cc7a4124925.png)

The **NeurIPS 2022 The SENSORIUM competition** aimed to find the best neural predictive model that can predict the activity of thousands of neurons in the primary visual cortex of mice in response to natural images. <br/>
### Tracks:
**SENSORIUM** - Stimulus-only - Assessed on how well they predict neural activity solely in response to the visual stimulus averaged over all trials.<br/>
**SENSORIUM+** - Stimulus-and-Behavior - Assessed based on how well they can predict neural activity given additional behavioral variables. <br/> <br/>
This repository contains our submission for this competition, where we attempted to improve the baseline model for the competition track- **Sensorium+**.

## 2. Setup Instructions

We mainly used 2 pathways to run the entire model. Below is a step-by-step guide for getting started.

## PATH 1:  USING WSL
### 1. Pre-requisites
- install [**docker**](https://docs.docker.com/get-docker/) and [**docker-compose**](https://docs.docker.com/compose/install/)
- install git
- clone the repo via `git clone https://github.com/sinzlab/sensorium.git`

### 2. Download neural datasets

You can download the data from [https://gin.g-node.org/cajal/Sensorium2022](https://gin.g-node.org/cajal/Sensorium2022) and place it in `sensorium/notebooks/data`. <br/>
**Note:** Downloading all the files at once as a directory leads to subsequent errors. Hence, download all datasets individually.

### 3. Run the example notebooks

### **Start Google Colab environment**
```
cd sensorium/
docker-compose run -d -p 10101:8888 jupyterlab
```
Now, type `localhost:10101` in your browser address bar, and you are good to go!

### Changes implemented:
While finding the mean and variance of the neuron receptive field location, we introduced proceeding with multiple samplings of the same to increase number of parameters 

### Evaluation

- We use the predictions generated from the submission file, using the API provided by Sensorium to evaluate the performance of our method. 
    

## Tutorial Notebooks
[**Dataset tutorial**](notebooks/dataset_tutorial/):  Visually display the structure of the data and the code to turn it into a PyTorch DataLoader.
<br>[**Model tutorial**](notebooks/model_tutorial/): How to train and evaluate baseline models.
<br>[**Submission tutorial**](notebooks/submission_tutorial/): Using the Sensorium API to make a submission to the competition.
