# Computer Vision project
## Project description

A supermarket chain would like to explore whether Data Science can help them adhere to alcohol laws by making sure they do not sell alcohol to people underage. 
The shops are equipped with cameras in the checkout area which are triggered when a person is buying alcohol.
Computer vision methods can be used to determine age of a person from a photo.
The task then is to build and evaluate a model for verifying people's age.

## Data description
The data was downloaded from [ChaLearn Looking at People](<http://chalearnlap.cvc.uab.es/dataset/26/description/>).
It is stored in the /datasets/faces/ folder with all the photos (/final_files) and csv file labels.csv with two columns: file_name and real_age.
As the number of image files is rather high, it is advisable to avoid reading them all at once, which would be resource consuming, and to read them sequentially with the ImageDataGenerator generator.

## Overall conclusion
* By the way, in one article about this dataset you are working with, the lowest MAE value reached is 5.4. If you get MAE less than 7, it would be a great result!
* We got Test MAE of 5.8 on Epoch 20/20 and by the rate we can see that if we will increase the ephocs the MAE can go down even more.
* The MAE was better for runnig the same on data after outlier removel of lower\younger than 80.
    * When tring to train the same on all the df I got Test MAE: 6.1
* The accuracy of the model should be checked on the range of 10-20 years old which should be the years where the age should be determine well for the Alcohol limits, and there the MAE of 5 is not enough! this is the risk where we can sell an alcohol to a 16 years old!
* I believe this model should be classification model after all in order to be good enough for the purpose of business tasks described in the beginning to predict if its prohibit or not for Alcohol like I found in this article on the same topic <https://towardsdatascience.com/improving-the-performance-of-resnet50-graffiti-image-classifier-with-hyperparameter-tuning-in-keras-dbb59f43c6f7>.
* So my recommendation for next time.. balance the data for under 21 and the rest and clasify it :) I believe it will give better results.
