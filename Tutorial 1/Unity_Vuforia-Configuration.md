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

- Open [Vuforia Download SDK](https://developer.vuforia.com/downloads/SDK) and download the Vuforia Engine to Unity Project.
  
- To allow Unity to recognize images/3D models using the laptop camera and track and display virtual objects on these images, we will import the Vuforia Unity Package. To do this, we will navigate to Assets/Import Packages/Custom Packages at the top of the menu toolbar.

Here is a more detailed explanation of each step:

1. Open Unity.

<img width="1014" alt="setup_1" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/b3bc391e-4f23-4954-95e3-c1d4b1b6911a">



2. In the menu toolbar, navigate to Assets > Import Packages > Custom Packages.



<img width="913" alt="Screenshot 2023-08-31 at 7 35 34 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/44600144-d495-4a5f-b8e2-1e214b8efdb3">


<img width="784" alt="Screenshot 2023-08-31 at 7 36 19 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/7c439478-64d6-4232-9c8f-59a6f8abc76e">


3. In the Import Package dialog, select the Vuforia Unity Package and click Import.

<img width="350" alt="Screenshot 2023-08-31 at 7 36 55 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/fcf32b5d-be08-4624-a852-f0cbfb4117ba">



4. Unity will import the Vuforia Unity Package and add the Vuforia namespace to your project.
5. You can now use the Vuforia API to recognize images/3D models using the laptop camera and track and display virtual objects on these images.

#### XR Plug-In Management

1. In the menu toolbar, navigate to Edit > Project Settings.

<img width="1504" alt="Screenshot 2023-08-31 at 7 47 42 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/23159ae5-3995-4e60-a7f2-df4c689fe819">


2. In Project Settings, select XR Plug-in Management and click Android settings, select Google ARcore.

<img width="940" alt="Screenshot 2023-08-31 at 7 48 41 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/fa8d983f-e1d7-4f10-b8c3-855acc20a197">


3. (Optional) click iOS settings, Apple ARKit.

<img width="940" alt="Screenshot 2023-08-31 at 7 48 53 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/588f5914-fcab-4438-9aaa-b347e9c2b246">


### Vuforia AR Camera Set Up

1. In the menu toolbar, navigate to GameObject > Vuforia > AR Camera.

<img width="940" alt="Screenshot 2023-08-31 at 7 58 58 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/2dfd7a68-50bc-4c16-beac-fd6061f03f87">

2. Rename the camera to "Vuforia_ARCamera" for better identification. Delete the other 2 objects "AR Session" & "AR Session Origin"

<img width="210" alt="Screenshot 2023-08-31 at 8 24 02 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/e3756f10-136f-4532-9ef6-1f4b476a4b22">

3. Navigate to Assets > Resources > Vuforia Configuration, Add Vuforia License Key

<img width="1504" alt="Screenshot 2023-08-31 at 8 17 55 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/29ff80a7-aec3-44c0-972a-654c0626364d">

#### Vuforia License Key

- Login to the [Vuforia License Manager](https://developer.vuforia.com/vui/develop/licenses) page with the Vuforia Account you created. Click on Add License Key to create a free key enabling your Unity application to use Vuforia's image recognition services.

1. Click "Get Basic" (FREE) and give a name to your License Key.

<img width="1213" alt="Screenshot 2023-08-31 at 8 40 10 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/2cdae7a2-7d28-4afe-b018-7c1ea0b5e41f">



<img width="1213" alt="Screenshot 2023-08-31 at 8 43 50 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/7038972c-9f30-401a-9fa2-e5b5bba9f8fb">

2. Click on the License Name, and it will have the Vuforia license key. Copy and paste into the Vuforia Configuration App License key text field in the Unity application.

<img width="1213" alt="Screenshot 2023-08-31 at 8 48 07 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/0a4647aa-a299-410e-88b4-9e749b9bb6ff">



<img width="1213" alt="Screenshot 2023-08-31 at 8 53 44 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/76af35f5-667a-4325-afc5-ff9acdf72f13">


#### Target Management

- This step is crucial since target management containing databases helps the Vuforia Engine identify the target image. 

1. Open [Target Manager](https://developer.vuforia.com/vui/develop/databases), click on "Add Database" 

<img width="1213" alt="Screenshot 2023-08-31 at 9 04 02 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/1cc2176e-a46a-4a07-abc0-61649d4da956">

2. When creating the database, click on the name and click on the "Add Target" Button to start adding the images to be recognized.

<img width="872" alt="Screenshot 2023-08-31 at 10 21 23 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/596d59a1-22e0-4cea-ab20-fcc65c3ae787">


3. After uploading your image targets, click the Download Database(All) button and select Unity Editor to download image database files into a Unity package.

<img width="513" alt="Screenshot 2023-08-31 at 10 23 55 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/017e7b3b-9e9d-4b9d-b4d8-d9acc40c7b53">


4. Go back into the Unity program, navigate Assets/Import Packages/Custom Packages, and select the downloaded Image Database Unity Package.

<img width="1504" alt="Screenshot 2023-08-31 at 10 36 12 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/583c74b6-3540-42af-9699-4ae4c3adef4e">


5. Right-click under "SampleScene" and navigate to Vuforia Engine > Target Image.

<img width="892" alt="Screenshot 2023-08-31 at 10 36 41 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/8cf6a658-36a9-4f2e-9568-e275f119e982">


6. Right-click on the newly created "ImageTarget" and navigate to 3D Object > Quad.

<img width="891" alt="Screenshot 2023-08-31 at 10 37 07 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/c3ecbf28-c0bc-42f9-bacf-a913b3a30672">



7. Go to "ImageTarget", and on the right-hand side, add the target image onto the scene via the database package you imported. (Type -> "from database")


<img width="1504" alt="Screenshot 2023-08-31 at 11 33 56 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/8f3fc7c3-40d6-4335-ab20-2bbfcc6e0ce9">


### 3. Setting Up a Virtual Object

- Navigate to the Unity Asset Store section and select the login option. Once you've successfully logged in, you'll gain access to a wide variety of assets available for both free and purchase. These assets encompass an array of items such as 3D models, environments, characters, textures, shaders, scripts, and various other components that can be seamlessly integrated into your application or game development process.


<img width="652" alt="Screenshot 2023-09-01 at 1 28 09 AM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/7ce99278-200d-40f3-a83f-7fe8d35a7ea9">

We will download the free Medium Mech Strikes asset, a rigged 3D model with animations. In the search bar, search for Medium Mech Strikes and click on the "Medium Mech Strikes" Model link.


<img width="830" alt="Screenshot 2023-09-01 at 1 58 54 AM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/02d31958-aa49-432f-a167-914cbd1c60d5">

Drag and drop the GameObject under Image Target. (Alter the position and scale as deemed necessary.)


<img width="784" alt="Screenshot 2023-09-01 at 2 16 44 AM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/330f3d48-2153-4a01-a2bc-5b1c4d29cea2">


<img width="1504" alt="Screenshot 2023-09-01 at 2 20 07 AM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/3192e755-b5ed-4ae8-b9a9-eda011a00762">


To test it out, you must print/digital copy of the target image for the engine to recognize. Click on the Play button above the scene view to start the app in Unity. If Vuforia correctly identifies the default camera, you should be able to see the live camera feed on the Unity Gamemode screen.


### Great job! You've successfully created an augmented reality scene in Unity where a virtual object is generated upon recognizing a specific target image.
