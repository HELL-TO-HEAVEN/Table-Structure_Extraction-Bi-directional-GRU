# Abstract
Tables present summarized and structured information to the reader, which makes table structure extraction an important part of document understanding applications. However, table structure identification is a hard problem not only because of the large variation in the table layouts and styles, but also owing to the variations in the page layouts and the noise contamination levels. A lot of research has been done to identify table structure, most of which is based on applying heuristics with the aid of optical character recognition (OCR) to hand pick layout features of the tables. These methods fail to generalize well because of the variations in the table layouts and the errors generated by OCR. In this paper, we have proposed a robust deep learning based approach to extract rows and columns from a detected table in document images with a high precision. In the proposed solution, the table images are first pre-processed and then fed to a bi-directional Recurrent Neural Network with Gated Recurrent Units (GRU) followed by a fully-connected layer with soft max activation. The network scans the images from top-to-bottom as well as left-to-right and classifies each input as either a row-separator or a column-separator. We have benchmarked our system on publicly available UNLV as well as ICDAR 2013 datasets on which it outperformed the state-of-the-art table structure extraction systems by a significant margin.

# Implementation
In our proposed methodology, we have divided our pipeline into three stages.

Note: The Order of execution is very important.

## Pre-processing:
  - The scripts should be run in the order described in the paper
  - The scripts use the same parameters for morphology, noise etc as described in the paper
  - You should run them in order and feed output of one script to the next

## Model:
 - This directory contains the script used for training and validating the model
 - The script has an inner DataLoader class that automatically loads the batches
   for you.

## Evaluation:
 - Contains all the code that we have used for benchmarking. It uses the same 
   approach as described in "An open approach towards the benchmarking of table structure recognition systems" by Shahab et al.
 - The file eval.py contains the core logic and calculates all the results.
 - You should execute the files in this directory in the following order:
    1) adjust_predictions.py
    2) prepare_predictions.py
    3) rescale.py
    4) eval.py
