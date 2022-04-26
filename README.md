
# **Project Brief**

## **Problem Statement:**
An Online Jewelry Brand would like to add a feature where users can upload a picture of their jewelry and the system will recommend. Unfortunately they do not know how to establish image recognition.
With the end goal being a recommendation engine, the first phase of the process is to produce an image classifier able to label jewelry into one of the four categories; rings, earrings, necklaces or bracelets. This was accomplished by implementing a Convolutional Neural Network. 

## **Current State:**
The original collection of images were 1272 in total consisting of 475 earring images, 193 ring images, 309 bracelet images and 320 necklace images. Approximately 40 of those images were corrupted or unreadable and had to be removed from the data bunch.

## **Data Preparation:**
As an advantage of using the Fast AI neural network library, little data preparation is required before fitting a model . One simply needs to compile all the necessary images into one folder with each image going to its respective subfolder based on the classification. Once that was sorted out a Data Bunch was created which reshapes the data and ensure that all the images are formatted to the proper dimensions in order to be used for the neural network. Additionally, in order to improve the accuracy of image classifications, transformations were applied to the Data Bunch which creates varying configurations of the images. This includes how much the image is zoomed in or not, the different angles of rotation of the image, the contrast etc.. This aids in predicting images regardless of their configurations if a user were to input a picture in more difficult contexts. Lastly, again in pursuit of improving the model performance, the images provided were the jewelry items in the center of the picture with a white background. This proved to cause issues when attempting to classify images with varying backgrounds, for example, a ring on a hand. For this reason an additional 400 images per category were imported from google images in order to increase the diversity of the Data Bunch simulating more real inputs from potential users.

## **Modelling:**
Once all pre-processing steps were accomplished a neural network called named Resnet50 was fitted to the data. This is a pre-trained neural network meaning that the weights of each neuron for each layers have already been optimized on the famous Image Net containing 1.5 million images across 1000 separate classifications. This is what decreases the compute times of training drastically as the weights of only the last layers of the neural network need to be trained on by your specified data. As well, the weights will take less time to adjust in order to be optimized for your predictions. Resnet50 specifically means its a residual neural network containing 50 layers. From it’s initial fitting with the data and running for 4 epochs, the validation accuracy came to 92%. However when testing on new google images it produced a test accuracy of 65%. In response the layers of the network were then unfrozen and trained once again while plotting the loss vs the learning rate to determine what learning rate range as well as number of epochs create the most accurate neural net. The learning rate range with the steepest descent in loss came to be 1e-4 to 5e-3 while maintaining 4 epochs. After fitting the data once again the accuracy jumped to 78%. 

## **Summary and Future Work:**
In conclusion, Fast AI does seem to outperform other neural network libraries and is a highly recommended method of quickly applying a classifier. However as a result of reducing the number of steps needed for usability and speed, this lowers the interpretability going on in the backend. Thus, exploring other libraries would be beneficial for a deeper understanding of each framework. While not a poor performance this model of course can be improved upon by optimizing many more hyperparameters. The current approach to acquiring a higher accuracy was simply through trial and error. Additionally, the next step would be to begin building a multi-label classifier by looking into identifying not just the type of jewelry but the material, the style, the color and many more specific features that go into the images.

## **Output/Deliverable/Usage:**
Presentation and Image Classifier

## **Stakeholders:**
Technical Team

## **Due Date:**
October 1st 2019

## **Measures of Success:**
The performance of this project is purely based on the ability of the image classifier to accurately distinguish images between rings, necklaces, earrings and bracelets. This accuracy came to 78% which is significant however requires much more fine tuning.

