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
   
<img width="1084" alt="Screenshot 2023-12-12 at 10 31 26 pm" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/fa66f07c-21a1-4f4e-a979-94a128028bc4">

3. Click Edit -> Project Settings.

<img width="879" alt="Screenshot 2023-12-12 at 10 52 49 pm" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/44783a66-7199-4511-a765-57af4502422f">

3. Please then add the device you would like.

<img width="854" alt="Screenshot 2023-12-13 at 1 45 40 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/0fe38518-0e65-4b63-a5b7-f346e3d32d6d">

4. Click Windows -> Packet Manager -> click of the "+" button and install package by name
   
<img width="754" alt="Screenshot 2023-12-13 at 1 50 26 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/951cf788-76f3-4966-a260-fb23f84cb8a4">

5. Click samples and import the marked elements.

![Screenshot 2023-12-13 at 1 54 43 am](https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/61f64852-ffbc-449f-9961-b36d2d9fe531)

6. Right Click under the section "SampleScene" and add an XR Origin (VR) Rig

<img width="377" alt="Screenshot 2023-12-13 at 2 06 37 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/dbed9544-43ea-47b6-99ed-775108d16c24">


<br>
<br>

**NOTE**
> Since XR Origin already has a camera, hence if you do have an another camera kindly remove it for less confusion.

7. Navigate Projects -> Assets -> Samples -> XR Toolkit -> Starter Assets -> Presets (left Contoller)

<img width="519" alt="Screenshot 2023-12-13 at 2 23 40 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/7d467464-5abd-4ec2-b4cc-327a834ad496">
<br>
<img width="454" alt="Screenshot 2023-12-13 at 2 29 09 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/8a416122-9215-4807-a153-e13c1d063678">

8. Do same for right controller

<img width="410" alt="Screenshot 2023-12-13 at 2 30 35 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/23217498-245b-4915-83c0-5dc623f080db">

9. Import the Oculus package to the unity project

![Screenshot 2023-12-13 at 2 37 07 am](https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/e64c896f-f0a3-4609-8af8-c2ed4ebfc7de)

10. Navigate to Project -> Oculus Hands -> Prefabs - drag and drop the models of respective hands under its controllers.

<img width="259" alt="Screenshot 2023-12-13 at 2 56 58 am" src="https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/de4ef690-f880-41c8-828b-0888f6e2c18d">

#### With this basic VR setup is Complete

### 3. Adding SkyBox

**NOTE**
> A VR skybox is a virtual environment that surrounds the user, providing a realistic and expansive backdrop to the immersive VR experience. Instead of being a flat, static image on the interior faces of a cube, a VR skybox is more dynamic and responsive to the user's movements and interactions.

- We can use any panoramic picture for this purpose. We can also create one using a website called [Skybox AI](https://skybox.blockadelabs.com)
- Download the Image and import it to the unity project.
- Change the Texture shape to "Cube". Then drag and drop the image to the scene.
![Screenshot 2023-12-13 at 3 07 59 am](https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/bccb703e-2029-4edf-9f78-6b2146912f05)

![Screenshot 2023-12-13 at 3 18 02 am](https://github.com/Dhyan-21041/UDXR_Tutorials/assets/106147710/2a8b3b4e-dfcc-4d5d-bbe5-bc7ac1441e02)


> The skybox is limitlessly long (Endless Horizon) and in a particular scene, we can have only one skybox.
<br>

### You have Successfully added a skybox to your VR project.
