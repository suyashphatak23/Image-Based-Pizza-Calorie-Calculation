# Pizza Image Based Calorie Calculation

## Table of Contents

* Introduction
* Problem Statement
* Planned Objectives
* Literature Review
* Research Gaps
* Dataset Details
* System Architecture
* Method
* Calorie Prediction of Toppings
* H/W & S/W Specifications
* Result Analysis
* Outputs
* Future Scope
* References

## Introduction

* As the world improves every day, our problems are changing. There is an increasing rise in the number of people afflicted with obesity and the health problems that come with it.  

* In 2016, 39% of the adults who are aged 18 years old and above were overweight, and 13% of them were obese according to the data given by WHO, 2018. Hence, it is apparent that fitness is becoming more and more essential to a lot of people.

* To address this issue, we are going to be implementing a program which can recognize pizza images and calculate the approximate number of calories that it contains. This is going to help people be more mindful about the number of calories that they are consuming and hence lead a healthier lifestyle.

## Problem Statement

* Our problem statement is to calculate the number of calories present in each pizza image while accounting for the various toppings on it.

* The input for the program would be a set of pizza images with different toppings for training.

* A robust detection model would be trained to identify the type of pizza and toppings and try to estimate the volume of the pizza to find an approximate number of calories that it would contain.

* A small sample of unseen images would be reserved for testing.

## Planned Objectives

* Estimate the calorie from different types of pizzas and toppings.

* Minimize error of estimated calories.

## Literature Review

## Research Gaps

* While there have been a lot of research papers in the general area of calorie estimation, there are no papers which focus on just pizza calorie estimation in detail.

* Our project aims to give a more accurate calorie estimation for pizza images while also considering the toppings on the pizza for the final calorie value estimation.

## Dataset Details

* We have created our image dataset by using images.cv website which provides various image datasets for computer vision and machine learning applications.

* We have segregated images into three folders which is training, testing and validations.

* Training: 2,975, Testing: 889, Validation: 304, Total   Images: 7230

* After preprocessing, we have reduced the number of images to 7000.

## System Architecture

* Food recognition is a pre-existing concept whose aim is to find and identify any food items present in the given image. Further the goal is to estimate the calorie of the entire pizza along with the toppings which is being recognized.

* We use the Mask-RCNN framework for identifying the food items. For performing calorie calculation, we use a standardized approach by calculating the values using the calories per 1 gram of toppings present in the item.

* The pizza image is provided as an input to the model and based on the standardized values, the approximate calorie in the entire pizza is found.

## Method

* To identify what’s on the pizza, we need to instance-segment the given food image into the possible food categories.

* Pizza and topping size estimation: The entire Pizza along with toppings can be detected using Mask-RCNN.

* The pixels_per_sq is calculated using the actual size of a calibration object (thumb or plate) in real life.

Pixels_Per_Sq = calibrated_obj_pixels_area / actual_obj_area

Food Area = masked_food_pixel_area / pixels_per_sq

**Total Calories = ∑ (Toppings Calories) + (Pizza Base Calorie)**

## Calorie Prediction of Toppings

* We plan to predict calories using a simple CSV that we have created for the toppings in the pizza. The CSV essentially maps each topping to its calorific value.

* Count the number of toppings items where obtaining a count is possible.

* We then use the outputs from our Mask-RCNN model and implement a simple algorithm that uses these as inputs (the food labels detected, and their counts) to determine the calorific value of the entire image using a simple lookup on the CSV file.

## H/W & S/W Specifications

## Result Analysis

| Metric      | Value |
| :---        |    :----:   |
| Precision     | 0.966       |
| Recall   | 0.5166        |
| F1-Score   | 0.6734        |

| Metric      | Value |
| :---        |    :----:   |
| mAP      | 0.9385   |
| mAP 50   | 0.9124 |
| mAP 70   | 0.8722 |

## Outputs

## Future Scope

In the future, this project could be improved where the model would be further enhanced to work for a broader set of images and be more accurate overall. We can also create mobile application or website where user can give input image, and we will get total calories.

## References

<https://www.who.int/news-room/fact-sheets/detail/obesity-and-overweight>
<https://www.cdc.gov/obesity/data/obesity-and-covid-19.html>
<https://arxiv.org/pdf/1705.07632.pdf>
<https://arxiv.org/pdf/1811.00982.pdf>
<https://www.site.uottawa.ca/~shervin/pubs/FoodRecognitionDataset-MadiMa.pdf>
<https://cs229.stanford.edu/proj2015/151_report.pdf>
<https://www.calories.info/food/pizza>
<https://www.popsugar.com/fitness/Calories-Pizza-Toppings-19209681>
<https://www.bacinos.com/pizza-calories-nutrition/>
