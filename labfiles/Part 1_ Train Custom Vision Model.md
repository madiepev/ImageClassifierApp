## Part 1:  Train Your Model
Before you start, make sure you a have a folder with your images (50 per category, minimum of 2 categories), access to the Azure portal and an Office365 account.

The content for training your model and building a classifier in Custom Vision is based on: https://docs.microsoft.com/en-us/azure/cognitive-services/custom-vision-service/getting-started-build-a-classifier. 



Create a Custom Vision project and train the model on your images
-	Navigate to customvision.ai. 
-	Click on Sign in. 
-	Log in with your company’s credentials (that are linked to Azure).	 

<img src="/media/Part%201/1.png" alt="drawing" width="800"/>

When this pop-up appears during the log-in:

<img src="/media/Part%201/2.png" alt="drawing" width="800"/>

-	Make sure to check the box to agree, after you read the agreement and terms. 
-	Click on I agree.  	



You are now in the home page of Custom Vision. Here you see your existing projects. On the top right you see the settings for your account. If there are any issues with the account that is linked to Custom Vision now, you can check there if the right account or directory is linked. 
-	Let’s start with clicking on a New Project.	 

<img src="/media/Part%201/3.png" alt="drawing" width="800"/>

A pop-up will appear to help you create a new project.
-	Fill in a name for your project. 
-	Entering a description is optional. 
-	For Resource Group, click on create new on the right.	 

<img src="/media/Part%201/4.png" alt="drawing" width="800"/>

A new pop-up appears to help you create a new resource group. Behind the scenes, a new resource group will be created in Azure. 
-	Give your new resource group a name. 
-	Choose in which Azure Subscription this resource group should be created. 
-	Choose South Central US for location. 

Note! This is necessary because of the current PowerApps connector. In a later phase, when the connector is not in preview anymore, you can choose whatever region you want.
-	Keep the Pricing Tier at S0. 
-	Click on Create resource.

<img src="/media/Part%201/5.png" alt="drawing" width="800"/>

Note! If any problems may arise here, it may have something to do with your Azure permissions, ask for help from your IT department if that occurs.	 


Back to the pane where we were creating a new project. 
-	Name and resource group should be right now.
-	Make sure Project Types is set on classification. 
-	Classification Types can stay on Multiclass. 
-	You can keep the Domains at General, or choose whatever domain best fits your images. 
-	Click on Create project, to continue.	 

<img src="/media/Part%201/5.png" alt="drawing" width="800"/>

We are now in our project. We will cover different aspects part by part. Let’s start with the most important thing: our data.
-	Upload your images by clicking on Add images.
-	Navigate to the folder on your laptop and upload these. 
	 
	 
<img src="/media/Part%201/5.png" alt="drawing" width="800"/>

This example has used images from Kaggle containing pictures of signs of the American Sign Language meaning either “A” or “B”. For your workshop you will work with your own ML problem

After you have clicked on Add images:
-	Browse to the folder with the images. 
-	Select all images of one category. This makes the tagging easier.	 
In this example, we’ve selected all images where an “A” is signed. 

<img src="/media/Part%201/6.png" alt="drawing" width="800"/>

After selecting the images, you can add a tag to the batch of images you have selected. 
-	Add your label for these images (in the example “The letter A”) to My Tags. 
-	Click on Upload 50 files.	 

<img src="/media/Part%201/7.png" alt="drawing" width="800"/>

The images will be uploaded and automatically tagged. 
-	Click on Done, when the process is completed.	 

<img src="/media/Part%201/8.png" alt="drawing" width="800"/>

You’ll now see all your images. On the left pane you see that under Tags, the option Tagged is selected and that “The letter A” is showing. 

We have now tagged all uploaded images. By clicking on Untagged, you may, at any time, check whether there are still some images that have not been tagged and subsequently tag them. All images need to be tagged in order to train the model. 

You can also see how many images you have per category. 

Before we train the model, we still need to add one more category (we need at least two categories before we can train a classifier model).

<img src="/media/Part%201/9.png" alt="drawing" width="800"/>

Let’s upload our second category of images.
-	From the options in the top, choose Add images. 	 

<img src="/media/Part%201/10.png" alt="drawing" width="800"/>


Again, a pop-up will appear. This time make sure you only upload images you haven’t uploaded yet.
Select all images from your second category and click on Open to upload them.
-	Add your label (in this example “The letter B”) to My Tags. 
-	Click on Upload 30 files.

<img src="/media/Part%201/11.png" alt="drawing" width="800"/>

-	 Click on Done.	 

<img src="/media/Part%201/12.png" alt="drawing" width="800"/>

All the necessary images have been uploaded. You have enough images and categories now to train the model. 
-	Check in the left pane that you have two categories or more. And that you have at least 10 pictures for each category. 
-	On the right top, click on Train.	 

<img src="/media/Part%201/13.png" alt="drawing" width="800"/>

When Custom Vision is done training the model, it will bring you to the new pane: Performance. Here you can see per time that you train a model, so per Iteration, what the results are. It seems our model has very positive results. Let’s see how well it actually does by testing it. 
-	On the right top, click on Quick Test.	 

<img src="/media/Part%201/14.png" alt="drawing" width="800"/>

-	Click on Browse local files. 
-	Select a test image (in this example a test image for the letter B). 

<img src="/media/Part%201/15.png" alt="drawing" width="800"/>

The trained model will now make a prediction of which category this image is. On the right bottom you see Predictions where “The letter B” gets a 99.9% probability, which is right!

-	Click on the right cross at the top right to close this pane.	

<img src="/media/Part%201/16.png" alt="drawing" width="800"/>
Now that it works as we like we need to publish it so that we can get the endpoints necessary to connect our model with other applications. 
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


