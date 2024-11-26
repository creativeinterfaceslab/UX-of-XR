# Configuring Unity and Vuforia

### 1. Unity Installation
   
Follow these steps to download and install Unity software:

- Download Unity Hub:
Unity Hub is a management tool that helps you install and manage different versions of Unity. You can download it from the official Unity website:
[Unity Hub Download](https://unity.com/download)

- Install Unity Hub:
After downloading the installer, you can just run it and follow the on-screen instructions to install Unity Hub on your computer.

- Open Unity Hub:
Once Unity Hub is installed, you can just open it. You'll use Unity Hub to install and manage various versions of the Unity editor.

You can sign in to your Unity account within Unity Hub. This step is optional but allows you to conveniently access your Unity projects and licenses.

- Install Unity Editor:
In Unity Hub, navigate to the "Installs" section. Here, you can choose the version of Unity you want to install. Click the "Add" button to see a list of available versions. Select the version you need and click "Next." Please install the latest "LTS" version.

- Select Modules:
Unity allows you to select additional modules during installation, such as platforms and components. Choose the modules you need for your projects, and then click "Done" to start the installation. Since we have to work with Vuforia, please ensure "Vuforia Augmented Reality Support" is selected. 
"Android Build Support" and "iOS Build Support" are also recommended.

Once the installation is finished, you can close the Unity Hub and launch Unity.

- Start Unity:
Return to the Unity Hub's "Projects" section to open the Unity editor. Click the "New" button to create a new Unity project or open an existing one.


### Account Registrations

- You need to set up new accounts in [Unity](https://id.unity.com/en/conversations/223f330d-a51a-4973-bd18-eccd1226c2a000ff) & [Vuforia](https://developer.vuforia.com).





### 2. Unity Project Setup

- Open [Vuforia Download SDK](https://developer.vuforia.com/downloads/sdk) and download the Vuforia Engine to Unity Project.
  
- To allow Unity to recognize images/3D models using the laptop camera and track and display virtual objects on these images, we will import the Vuforia Unity Package. To do this, we will navigate to Assets/Import Packages/Custom Packages at the top of the menu toolbar.

Here is a more detailed explanation of each step:

1. Open Unity.


![open unity](../Images/vuforia_1.png)


2. In the menu toolbar, navigate to Assets > Import Packages > Custom Packages.


![import packages](../Images/vuforia_2.png)


3. In the Import Package dialog, select the Vuforia Unity Package and click Import.


![import vuforia](../Images/vuforia_3.png)


4. Unity will import the Vuforia Unity Package and add the Vuforia namespace to your project.
5. You can now use the Vuforia API to recognize images/3D models using the laptop camera and track and display virtual objects on these images.

#### XR Plug-In Management

1. In the menu toolbar, navigate to Edit > Project Settings.


![project settings](../Images/vuforia_4.png)


2. In Project Settings, select XR Plug-in Management and click Android settings, select Google ARcore.


![xr settings](../Images/vuforia_5.png)


3. (Optional) click iOS settings, Apple ARKit.


#### Vuforia License Key

- Login to the [Vuforia License Manager](https://developer.vuforia.com/vui/develop/licenses) page with the Vuforia Account you created. Click on Add License Key to create a free key enabling your Unity application to use Vuforia's image recognition services.

1. Click "Get Basic" (FREE) and give a name to your License Key.


![license key 1](../Images/vuforia_8.png)

![license key 2](../Images/vuforia_9.png)

2. Click on the License Name, and it will have the Vuforia license key. Copy and paste into the Vuforia Configuration App License key text field in the Unity application.

![license key 3](../Images/vuforia_10.png)

![license key 4](../Images/vuforia_11.png)


### Vuforia AR Camera Set Up

1. In the menu toolbar, navigate to GameObject > Vuforia > AR Camera.


![ar camera](../Images/vuforia_6.png)

2. Rename the camera to "Vuforia_ARCamera" for better identification. Delete the other 2 objects "AR Session" & "AR Session Origin"


3. Navigate to Assets > Resources > Vuforia Configuration, Add Vuforia License Key


![vuforia key](../Images/vuforia_7.png)




#### Target Management

- This step is crucial since target management helps the Vuforia Engine identify the target image. 

1. Right-click under "SampleScene" and navigate to Vuforia Engine > Target Image.


![target image 1](../Images/vuforia_12.png)


2. Right-click on the newly created "ImageTarget" and navigate to 3D Object > Quad or add a ready asset.


![target image 2](../Images/vuforia_13.png)

![target image 3](../Images/vuforia_14.png)


### 3. Setting Up a Virtual Object

- Navigate to the Unity Asset Store section and select the login option. Once you've successfully logged in, you'll gain access to a wide variety of assets available for both free and purchase. These assets encompass an array of items such as 3D models, environments, characters, textures, shaders, scripts, and various other components that can be seamlessly integrated into your application or game development process.



![asset store](../Images/vuforia_15.png)

![asset store 2](../Images/vuforia_16.png)

We will download the free lotus temple asset, a rigged 3D model with animations. In the search bar, search for lotus temple, we can use sketch fab as well to find assets.


![lotus temple](../Images/vuforia_17.png)

![lotus temple 2](../Images/vuforia_18.png)

Drag and drop the GameObject under Image Target. (Alter the position and scale as deemed necessary.)


![lotus temple 3](../Images/vuforia_19.png)


To test it out, you must print/digital copy of the target image for the engine to recognize. Click on the Play button above the scene view to start the app in Unity. If Vuforia correctly identifies the default camera, you should be able to see the live camera feed on the Unity Gamemode screen.


![gameplay](../Images/vuforia_20.png)


### Great job! You've successfully created an augmented reality scene in Unity where a virtual object is generated upon recognizing a specific target image.
