Create a PowerApp and connect it to your Custom Vision model
-	Navigate to powerapps.microsoft.com. 

<img src="/media/lab%205/51.png" alt="drawing" width="800"/>

For this tutorial, it is assumed you have an account for Office 365 and thus you have an account that is authorized to build PowerApps. If you don’t, check this within your company or start at Get started for free, to create an account. 

Otherwise, if you do have an Office 365 account:
-	Click on Sign in at the top right corner. 
	 
A new screen will appear which will guide you through the signing in process. 
-	Sign in with your work email that is connected to your Office 365 account.	 

<img src="/media/lab%205/52.png" alt="drawing" width="800"/>


Once you are logged in, you will see the home screen for PowerApps. There are a couple of things you can do: you can access the apps that are shared with you, you can go back to apps you’ve created earlier to edit them, but you can also start to create a new app. 
-	Click on Canvas app from blank to create a new app.	 

<img src="/media/lab%205/53.png" alt="drawing" width="800"/>


-	Give your new app a name.
-	Choose whether you want your app to be in Tablet or Phone format. In the tutorial, we will continue with Tablet but it only affects the layout of your app and none of the functionality so it doesn’t matter for the purpose of this tutorial which you choose. 
-	Click on Create. 	 
It may take a while for your app to be created, make sure not to close your browser. Once it has been created, you will see the screen as is shown on the right. 

<img src="/media/lab%205/54.png" alt="drawing" width="800"/>

Take some time to explore the options here, it works similar to other Office products where you have a taskbar on the top with what you can do and a canvas, which will be your end result, in the middle. 

Notice also the fx bar. PowerApps is a low-code application and most of the code is done in this fx bar. 	

<img src="/media/lab%205/55.png" alt="drawing" width="800"/>


To connect to our Custom Vision model, we will first need to add it as a ‘data source’:
-	In the top left bar, click on the tab View. 
-	Then click on Data Sources.	 

<img src="/media/lab%205/56.png" alt="drawing" width="800"/>

A new pane will pop up on the right with the title Data.

-	Click on + Add data source. 

<img src="/media/lab%205/57.png" alt="drawing" width="800"/>

You will see an overview of all data sources that have been connected with PowerApps within your organization, or maybe some data sources you have connect to in PowerApps before. Since we will connect for the first time with the model made in Custom Vision, we will need to create a new connection. 

-	Click on + New connection.

<img src="/media/lab%205/58.png" alt="drawing" width="800"/>


-	Type in custom vision in the search bar to search for the connector for Custom Vision. 
-	Click on the Custom Vision connector that appears below. 	

<img src="/media/lab%205/59.png" alt="drawing" width="800"/>

-	Fill in your Prediction Key. 
This can be found on the settings page of your Custom Vision model at customvision.ai. Go back to the last step of Part 1 for reference.

<img src="/media/lab%205/60.png" alt="drawing" width="800"/>

-	Click on Create. 	 
Your model from Custom Vision has now been added as a data source through a connector in PowerApps. These connectors are built for the usual data sources but can also be custom built using Microsoft Flow, we will not go into that in this tutorial but just know that it is possible. 

-	Click on the cross of the Data pane to close this pane. 	 
<img src="/media/lab%205/61.png" alt="drawing" width="800"/>

We will now create only the basic parts you need for your app but feel free to customize it by adding pictures or text, changing colors or fonts whenever you want. 

-	At the top, select Insert.
-	Then click on Media, and select Add picture.
 
 <img src="/media/lab%205/62.png" alt="drawing" width="800"/>
 
A box where you can add a picture has been added to your canvas. When you select the box or different aspects of the box, you can edit some settings such as the text, size and color amongst other things in the pane on the right.

If you want to try out the functionality of buttons or media like this, hold Alt on your keyboard while clicking on the ‘Tap or click to add picture’. You can also test the functionality by playing a preview of the app by clicking on the Play button on the top right. 	 

<img src="/media/lab%205/63.png" alt="drawing" width="800"/>

We have all we need for now so let’s add the second thing we need: a button. 

-	Again, make sure you are in the Insert tab on the top left. 
-	This time, click on Button. 

<img src="/media/lab%205/64.png" alt="drawing" width="800"/>

A button has been added to your app. You can also drag this to where you want it to be positioned in the app. Notice that now you have selected the button, the pane on the right shows what you can do with this button as well as it did with the add picture box. 
-	In the right pane, while having selected button, change the text from Button to ‘Analyze image’.  	 

<img src="/media/lab%205/642.png" alt="drawing" width="800"/>

As a Next step, we will build the logic around our app. Click on the Button ' Analyze image' and go the the Formula bar. Enter the following function:

ClearCollect(resultprediction,CustomVision.PredictImage("<Project-Id>",UploadedImage1.Image,{iterationId:"Iteration-ID"}).Predictions)

<img src="/media/lab%205/65.png" alt="drawing" width="800"/>

This function will create a collection (of data), named resultprediction. The collection stores the output of an CustomVision.PredictImage function. The only thing we need to fill in is the project id (to point to the right CustomVision Project) and the Iteration ID (to point to the right 'version' of the model)

Make sure to verify if the UploadedImage1 has the same name as the object in PowerApps

As a Last step we will add a Data Table to visualize the data from the resultprediction collection:

Click Insert - Data Table

<img src="/media/lab%205/66.png" alt="drawing" width="800"/>

Select Data Source, choose the resultsprediction

<img src="/media/lab%205/67.png" alt="drawing" width="800"/>


Now we click on add fields: 
We can select the fields/columns we would like to visualize. 
-Choose the Tag and Probability

<img src="/media/lab%205/68.png" alt="drawing" width="800"/>


All Done, we now have build an app that can upload an image, classify if its a cat1/cat2, and bring back the results in the app.

<img src="/media/lab%205/69.png" alt="drawing" width="800"/>


We can test it by clicking the play symbol in the right corner:

<img src="/media/lab%205/70.png" alt="drawing" width="800"/>


Spend the remaining time to improve your app visually (logo/texts/alignment)




