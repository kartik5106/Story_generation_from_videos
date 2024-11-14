Video Captioning and Story Generation
=====================================

This project implements a two-part system for **video captioning** and **story generation** using machine learning and natural language processing techniques. We utilize a CNN-based encoder-decoder model for caption generation on video frames, followed by a locally hosted LLM (Llama 3.1) to generate a themed story from the extracted captions. This project is useful for generating narrative summaries of short videos based on different themes (e.g., romance, comedy).

Project Overview
----------------

1.  **Caption Generation**:

    -   A pre-trained CNN encoder-decoder model based on **Inception V3** architecture is fine-tuned on the COCO 2017 dataset to generate captions for images.
2.  **Story Generation Pipeline**:

    -   Frames from the input video are captured at regular intervals and passed through the caption generation model.
    -   The generated captions are aggregated and fed into a custom prompt for the LLM, along with a specified theme, to produce a coherent story.
3.  **Evaluation**:

    -   The generated story is evaluated using BLEU and ROUGE metrics by comparing it to a reference story.

Requirements
------------

To run this project, the following dependencies are required:

-   Python 3.x
-   PyTorch
-   Transformers (Hugging Face)
-   OpenCV
-   NLTK
-   COCO API (for dataset handling)
-   Llama 3.1 or equivalent model locally hosted for story generation

### Install Dependencies

bash

Copy code

`pip install torch torchvision
pip install transformers
pip install opencv-python
pip install nltk`

Ensure that `Llama 3.1` or the desired LLM is set up and accessible locally.

Downloading the COCO 2017 Dataset
---------------------------------

The COCO 2017 dataset is required for training the caption generation model. To download and set up this dataset:

1.  Go to the COCO dataset download page.

2.  Under "2017 Train/Val", download:

    -   **2017 Train images** [118K/18GB]
    -   **2017 Val images** [5K/1GB]
    -   **Annotations** for the 2017 Train/Val dataset
3.  After downloading, create a folder named `coco` and place these files in a structured format:
   
