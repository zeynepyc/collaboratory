# collaboratory

This is an AR application built with Unity to present artifacts from the Ancient Mediterrenean Lamps collection in a virtual setting. Once deployed to an iPhone, simply point the camera to an image of a lamp copy. This should trigger a 3D model of the actual lamp on your screen.

For future interns at the Collaboratory:
  - You can pull this repository to your local machine to develop this project further, or
  - You can follow the instructions below to create your own AR project from scratch

## Use This Project
To test this project or develop it further, clone this repository using the clone link from above. 
&nbsp;  
Type ```` git clone link ```` on your command line. 
&nbsp;  
Connect your iPhone to your laptop and turn on the Developer mode on your phone from Settings. Open up the project in Unity and go to File -> Build and Run. This will open up XCode. Make sure your personal phone is selected as target device on XCode. When you run the project, XCode will build the app on your phone!

## Build Your Own Project
First, install Unity Hub from https://unity.com/download
&nbsp;  
Once installed, go to Installs tab on the left side of Unity Hub and install version 2022.2.12f1.
&nbsp;  
Click on the settings symbol on the right of your desired version box. This should pop an "Add Modules" window.
&nbsp;  
Select IOS build support on this window.
&nbsp;  
You are now ready to create you project! Go back to the Projects tab from the left hand side and click on the New Project button on the top right corner.
&nbsp;  
On the top of this pop up, make sure you have the correct version selected next to "Editor Version". Now choose the AR template on this page and click download if you need to. Give your project a name and click create.
&nbsp;  
Now we need to configure some settings. Go to Edit -> Project Settings
- Go to XR Plug-In Management from the menu on the left. Click on the IOS icon and select ARKit. Make sure Initialize XR on Startup is also checked. Under XR Plug-In Management, go to Apple ARKit tab and make sure that the Requirement is selected as Required.
- Navigate to Player Settings from the menu. You can change the name of your app here, which will be displayed when you deploy the app to your phone. Under Other Settings -> Identifier, uncheck Override Default Bundle Name and make sure that Architecture is ARM64. 


Next, go to Window -> Package Manager and update all packages if needed (if they have an up arrow icon).
&nbsp;  
We are now done with project settings!
&nbsp;  &nbsp;  
Under your SampleScene on the left, click on AR Session Origin, which will then dsplay its components on the Inspector on the right. 
&nbsp;  
Delete all default components until you only have the Transform and AR Session Origin (Script). Then, click Add Component and search for AR Tracked Image Manager. This is what is going to enable us to detect and track images through our app camera. We will need a library of images to detect, which we will create now. 
&nbsp;  
To create that library, go to the Assets box at the bottom of your Unity window. Right click -> Create -> XR -> ReferenceImageLibrary. 
&nbsp;  
Drag the image you want to detect to Assets. Then, click on ReferenceImageLibrary -> Add Image. Drag your image from Assets to the box on the Inspector labeled None (Texture 2D). Check specify size and add dimensions (0.062 should work fine for X).
&nbsp;  
Go back to the Inspector for AR Session Origin and drag ReferenceImageLibrary from assets to Serialized Library under AR Tracked Image Manager. 
&nbsp;  
In the same space, click Add Component and now search for New Script. Name it PlaceTrackedImages. Double click on the script which will open VSCode. Copy and paste the C# code in PlaceTrackedImages from this repository. Save it and go back to Unity. 
&nbsp;  
Now it is time to upload our 3D object. Drag the 3D model from your folder to Assets and rename it to give it the same name as your image, so that your app nows which model to trigger when an image is tracked. Then, drag your model from Assets to SampleScene on the left. Also drag it to element 0 under Place Tracked Images -> Ar Prefabs. 
&nbsp;  
Under your SampleScene, click the little arrow by AR Session Origin and the click AR Camera. On the inspector, change Clipping Planes values to Near: 0.01 and Far: 1000. 

&nbsp;  

That is all! You are ready to deploy your app! To do that, connect your iPhone to your laptop and turn on Developer Mode on your phone from Settings. On Unity, click File -> Build and Run. This will open up your XCode. Make sure the target device on XCode is your personal iPhone. XCode will build the app to your phone and you are ready to test it out! If you find that that the object does not appear, you might have to play around with the size and position of 3D model from the Inspector. 
