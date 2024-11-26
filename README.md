# Product's Entity Extractor from Product Images

**Amazon ML Challenge 2024**

## Overview

This project, developed for the Amazon ML Challenge 2024, tackles the task of extracting essential entities from product images. It simulates real-world e-commerce scenarios by building a machine learning pipeline that efficiently identifies product details directly from images, especially when textual descriptions are lacking or incomplete.

**Team Achievement:** Ranked in the Top 300 Teams worldwide out of 76,000+ participants.

## Problem Statement

E-commerce platforms often struggle with incomplete product information, particularly when textual details are missing. This project aimed to build a model that directly extracts key entity values (e.g., weight, dimensions, voltage) from product images, enriching and enhancing product metadata.

This capability has practical applications in various industries:

* **Healthcare:** Extracting critical information from medical packaging.
* **E-commerce:** Filling metadata gaps for millions of listed products.
* **Content Moderation:** Extracting data from images for policy compliance.

The extracted entities are crucial for improving search relevance, categorization, and user experience on digital marketplaces.

## Dataset Description

The dataset consists of the following key features:

* **index:** A unique identifier (ID) for each sample in the dataset.
* **image_link:** A public URL to download the product image. (Example: https://m.media-amazon.com/images/I/71XfHPR36-L.jpg)
  - Use the `download_images` function from `src/utils.py` for batch downloads. See example usage in `src/test.ipynb`.
* **group_id:** The category code of the product (e.g., electronics, appliances).
* **entity_name:** The specific attribute to extract (e.g., "item_weight," "item_dimension").
* **entity_value:** The target variable representing the attribute value (e.g., "34 gram," "22 x 15 x 10 cm").

**Note:** The `entity_value` column is absent in the test dataset and is the target you need to predict.

## Tech Stack

The solution leverages a combination of cutting-edge machine learning and computer vision technologies:

**Key Technologies & Models:**

* **Python:** Core programming language for all ML pipelines.
* **Machine Learning Algorithms:** Custom models for feature extraction and prediction.
* **Vision Transformer (ViT):** A state-of-the-art model for image representation.
* **Optical Character Recognition (OCR):**
    * **docTR:** High-performance OCR for image text extraction.
    * **Tesseract:** Open-source OCR for quick and reliable text parsing.
* **Natural Language Processing (NLP):** Entity recognition systems for refining extracted data.

## Solution Highlights

* **Image Preprocessing:** Images were preprocessed to enhance readability and compatibility with OCR models.
* **OCR Implementation:** Used OCR models (docTR and Tesseract) to extract text embedded within images, such as labels or dimensions.
* **Entity Mapping:** NLP techniques were applied to map extracted text to predefined entities like weight, voltage, etc.
* **Model Training:** Trained machine learning models to predict the correct entity value for the given image using the extracted data.
* **Evaluation Metrics:** The solution was evaluated using accuracy and F1 score, ensuring robust performance across varied product categories.

