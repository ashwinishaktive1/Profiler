# Profiler
Classifying the Instagram accounts based on the content posted, helps users to know if it matches with their preferences and if they would want to follow the account. The proposed pipeline involves web scraping, object detection (semantic segmentation), and category label classification.

## Abstract
With more than a billion Instagram accounts, and accounts covering a wide range of content like food, travel, nature, sports, etc it gets hard to determine what type of account it is. Even though Instagram allows users to select an account type, most of the time the account might have content from other categories as well. Classifying the accounts based on all the content posted in the profile might make it useful for users to understand if it matches the preferences they have and whether they want to follow the account. The categorization will also help the content creators to keep a check on themselves to see if they are going off track from what they want the account to look like. 

Hence, we propose a pipeline involving web scraping, object detection (semantic segmentation), and category label classification divided into two phases. We are selecting 3 different object detection models and 3 different classification models and evaluating the accuracy of these models.

## Dataset
There are several great object detection and image segmentation data sets available on the internet, amongst which we
elected to work with the following: \
- MS COCO dataset: The COCO dataset sponsored by Microsoft comprises over 330K images with over 200K images labeled (used as training and validation data-set). The dataset has 80 labeled object categories. The COCO team has collaborated with Fifty-One, an open-source data-set visualization, and evaluation tool. This can be used to evaluate the subject model’s performance.
- PASCAL VOC dataset: The PASCAL VOC project provides standardized image data sets and annotations for object detection, allowing for quick evaluation and comparison of various models. The most recent version of the data collection, which dates back to 2012, contains around 11.5K photos and 20 object class labels.
- Open Images dataset: The OID sponsored and collected by Google is a data set of millions of images with rich object labels and segmentation annotations. The dataset is annotated with over 19K image-level multi-classes and 600 object localization categories.

## Project implementation
Phase 1 expects the link of the profile to be classified. The scraper will pull all the images from that profile and send images one at a time to the object detection model, where the object detection model detects objects in each image and sums up the entire profile as a document of labels(objects found across all the images of the profile ). \
In phase 2, we train a classification model based on simulated Instagram training data. This trained classification model is provided with the document of labels from phase 1 as input and the classification model outputs the probability of the profile
belonging to each of the 7 given profile types. Based on a threshold we output all the profile types whose probability is more than the given threshold.

## Details
Authors: Ashwin Unnikrishnan, Ashwini Shaktivel Kumar, Shamekh Mohammad Siddiqui\
Institution: Khoury College of Computer Sciences, Northeastern University\
Contact: ashwinishaktivelkumar@gmail.com
