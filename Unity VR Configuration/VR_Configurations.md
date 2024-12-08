# VR Configuration & Skybox Setup in Unity

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

### 2. VR Setup

Here is a more detailed explanation of each step:

1. Open Unity.
   
![open unity](../Images/vr_1.png)

2. Click Edit -> Project Settings.

![project settings](../Images/vr_2.png)

3. Please then add the device you would like.

![add device](../Images/vr_3.png)


![add device](../Images/vr_4.png)


4. Click Windows -> Packet Manager -> click of the "+" button and install package by name

![packet manager](../Images/vr_6.png)

![import samples](../Images/vr_7.png)


5. Click samples and import the marked elements.

![import samples](../Images/vr_8.png)

![import samples](../Images/vr_9.png)


6. Right Click under the section "SampleScene" and add an XR Origin (VR) Rig

![add XR Origin](../Images/vr_10.png)

<br>
<br>

**NOTE**
> Since XR Origin already has a camera, hence if you do have an another camera kindly remove it for less confusion.

7. Navigate Projects -> Assets -> Samples -> XR Toolkit -> Starter Assets -> Presets (left Contoller)


![left controller](../Images/vr_11.png)

<br>


8. Do same for right controller

![right controller](../Images/vr_12.png)

#### With this basic VR setup is Complete

### 3. Adding SkyBox

**NOTE**
> A VR skybox is a virtual environment that surrounds the user, providing a realistic and expansive backdrop to the immersive VR experience. Instead of being a flat, static image on the interior faces of a cube, a VR skybox is more dynamic and responsive to the user's movements and interactions.

- We can use any panoramic picture for this purpose. We can also create one using a website called [Skybox AI](https://skybox.blockadelabs.com)
- Download the Image and import it to the unity project.
- Change the Texture shape to "Cube". Then drag and drop the image to the scene.

> The skybox is limitlessly long (Endless Horizon) and in a particular scene, we can have only one skybox.
<br>

### You have Successfully added a skybox to your VR project.
