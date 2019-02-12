# Capstone Project
## Beer Image Recognizer and Recommender
### Javier Martinez

---

## Problem Statement
---

Beer is the most consumed alcoholic beverage in the world, however there are thousands of different ways beer can be brewed. So rather than going and trying every beer in the world to see which ones you like, I would like to create an application that takes in an image of a beer label, recognizes it and returns information about the beer as well as recommended beers that are similar to these.

This project is divided into three separate parts being:
1. Creating a model that recognizes beer labels
2. Making a reccomender system that suggest similar beers based on user reviews and features of the beer
3. Creating an app using Flask web framework
---

## Recognizing Beer Labels

### Gathering Data

BreweryDB.com has quite a complete database of beers extending in over 80,000 beers worldide. In fact, they claim to be the most complete database for the beer industry. BreweryDB has a great API that is easy to work with in order to gather data, however, there are some caveats. The free API limits to a little over a thousand beers, therefore going for the subscription is the best way to go for a complete dataset. The subscription API limits you to 200 pulls per day in which you can retrieve 50 beers per pull (10,000 beers per day)

---
### Retrieving Images From Database
 
 The database returns a number of features per beer. Some of which are 'abv', 'ibu', 'name', 'description','food_pairings' etc. The feature we are most interested in for this projects are beers that have labels in them. By filtering out beers without labels or that have no interest to us (E.g. retired beers), we can narrow down our dataset for beers that we can train.
 
---
### Generating Image Transformations 

If we were to train on the base images of the beer, then we would hypertrain on the perfetion of the label image. However if we take an image of a beer label with our phone camera, the image will not be exactly the same as the original label, no matter how many times we try. To account for this, we will create 30 images for each label that are distorted in some way so that we create some variablilty in our model.

---

### Converting Images To Vectors

Because the Convolutional Neural Network that we will be training requires images in form of an array, we need to transform all of the images we have into numpy arrays, which is what the model needs as inputs. This step is quite a simple step, made easy by Keras' img_to_array

---

### Modeling

Using Convoluional Neural Networks to train on our data. First, doing a train test split to be able to simulate our model being tried on 'new' data. The issue with Convolutional Neural Networks is that there is no set 'guideline' on how parameters should be set. So trial and error by tweeking parameters is a long and tedious process that has to be done.

---

### Recognizer: Conclusions

There were quite a few roadblocks throughout this project. From having to reinstall anaconda to crashing multiple VM instances, there was definitley a lot to learn. In terms of the actual model itself, I am more than happy on how it turned out. I set myself a benchmark of what I thought was a success 80% accurate. However, looking back on it, it makes sense that the model performed quite well. It is infact training on the same image constantly. While the distortions do help it not be hyptertained, it certainly feels like the lack of outside data does not do my model any favor.

In terms of what's next, I would really like to optimize my model by adding in extra images of beers, as well as get started on the recommender system. I want to build two reccomender systems, one that is user review based (beeradvocate.com) and one that is feature based.

---
## Reccomender System

Part 2 not yet started 
 
---
## Application

Part 3 not yet started


---
