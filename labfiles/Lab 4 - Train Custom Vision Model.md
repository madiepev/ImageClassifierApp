# Lab 4 - Train Custom Vision Model

## Prerequisites
- Finish lab files "Getting started" and Labs 1 - 3 before continuing with this. 
- You should already have created a project within Custom Vision.
- Images of at least two categories (with tags) should already have been uploaded to your project in Custom Vision. 
If you encounter any missing prerequisites, go back to previous lab files to fix this.

## Resources
- [Quickstart: How to build a classifier with Custom Vision](https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/getting-started-build-a-classifier)

## Exercise 1

-	Navigate to customvision.ai. 
-	Click on Sign in. 
-	Log in with your credentials (that are linked to Azure).	 

<img src="/media/Part%201/1.png" alt="drawing" width="800"/>

When this pop-up appears during the log-in:

<img src="/media/Part%201/2.png" alt="drawing" width="800"/>

-	Make sure to check the box to agree, after you read the agreement and terms. 
-	Click on I agree.  	

You are now in the home page of Custom Vision. Here you see your existing projects. On the top right you see the settings for your account. If there are any issues with the account that is linked to Custom Vision now, you can check there if the right account or directory is linked. 
-	Select the project you created in the previous steps.	 

<img src="/media/Part%201/30.PNG" alt="drawing" width="800"/>

We are now in our project. We will cover different aspects part by part. Let’s start with the most important thing: our data.

You’ll now see all your images. On the left pane you see that under Tags, the option Tagged is selected. All you tags should be showing here. In the previous step you have uploaded all tagged images. 

By clicking on Untagged, you may, at any time, check whether there are still some images that have not been tagged and subsequently tag them. All images need to be tagged in order to train the model. 

You can also see how many images you have per category.

> You could see less images than you orignally collected from Bing because it couldn't upload the image to Custom Vision in previous steps. This is ok. As long as we have at least 2 tags and 5 images for every tag we can already train the model in Custom Vision.

All the necessary images have been uploaded. You have enough images and categories now to train the model. 
-	Check in the left pane that you have two categories or more. And that you have at least five pictures for each category. 
-	On the right top, click on Train. Select Quick training. 	 

<img src="/media/Part%201/32.PNG" alt="drawing" width="800"/>

When Custom Vision is done training the model, it will bring you to the new pane: Performance. Here you can see per time that you train a model, so per Iteration, what the results are. It seems our model has very positive results. Let’s see how well it actually does by testing it. 
-	On the right top, click on Quick Test.	 

<img src="/media/Part%201/33.PNG" alt="drawing" width="800"/>

-	Find an image you haven't used for training of one of your categories. You can copy the link or save the image locally.
-	Paste the link to the image or click on Browse local files and select the test image (in this example a test image for the kitten through a URL). 

<img src="/media/Part%201/31.PNG" alt="drawing" width="800"/>

The trained model will now make a prediction of which category this image is. On the right bottom you see Predictions where “kitten” gets a 99.9% probability, which is right!

-	Click on the right cross at the top right to close this pane.	

Now that it works as we like, we need to publish it so that we can get the endpoints necessary to connect our model with other applications. 
-	Click on Publish.	 

<img src="/media/Part%201/17.png" alt="drawing" width="800"/>


-	Keep the name as is, or change the name.
-	Click on Publish.	 

<img src="/media/Part%201/18.png" alt="drawing" width="800"/>

Once you’re back in the Performance pane and you see Unpublish instead of Publish, you know your model has been published. 
-	Click on Prediction URL.	

<img src="/media/Part%201/19.png" alt="drawing" width="800"/>


In the app we will create, we will have an image file. So let’s focus on the section that says: “If you have an image file”. 
-	Copy the key that is in red after Prediction-Key. Save it somewhere (e.g. in Notepad). 	 

<img src="/media/Part%201/20.png" alt="drawing" width="800"/>

After we are back in the pane Performance, the last thing for us to do here is make sure we have all the necessary information so that in the next step we can link an app with our model. 

-	On the top right, click on the gear wheel to go to Settings.

We now see an overview of our project settings with information such as Project Id. We will need this information later on, so keep this window open.	 

<img src="/media/Part%201/21.png" alt="drawing" width="800"/>


