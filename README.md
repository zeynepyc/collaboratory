# collaboratory

This is an AR application built with Unity to present artifacts from the Ancient Mediterrenean Lamps collection in a virtual setting. Once deployed to an iPhone, simply point the camera to an image of a lamp copy. This should trigger a 3D model of the actual lamp on your screen.

For future interns at the Collaboratory:
  - You can pull this repository to your local machine to develop this project further, or
  - You can follow the instructions below to create your own AR project from scratch


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
