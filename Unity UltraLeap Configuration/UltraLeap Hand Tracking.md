# UltraLeap Motion Controller 2 - Hand Tracking in Unity

This project demonstrates how to set up UltraLeap (Leap Motion) hand tracking in Unity and implement a basic interaction, such as grabbing an object in a virtual environment.

## Table of Contents

1. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
2. [Setting up UltraLeap in Unity](#setting-up-ultraleap-in-unity)
   - [Basic Configuration](#basic-configuration)
   - [Adding Hand Tracking to Your Scene](#adding-hand-tracking-to-your-scene)
4. [Basic Interaction: Grabbing an Object](#basic-interaction-grabbing-an-object)

---

## Getting Started

### Prerequisites

Make sure you have the following software and hardware:

- **Unity** (Latest version recommended, download from [Unity Download Page](https://unity.com/download))
- **UltraLeap Hand Tracking Device** (Download the latest tracking software from [UltraLeap Software Download](https://developer.leapmotion.com/tracking-software-download))

### Installation

1. **Download Unity Hub** from [Unity's website](https://unity.com/download).
2. **Install Unity** and make sure to select the build support options for your platform (PC, Android, etc.).
3. **Download and install** the **UltraLeap Hand Tracking Software** and connect your UltraLeap sensor.

## Setting up UltraLeap in Unity

#### NOTE: Ensure the orientation is set as Desktop after installing the UltraLeap Hand Tracking software.

### Basic Configuration
1. Set up the Unity XR Plugin Management Package, which can be installed from **Edit > Project Settings**.

 ![XR Management](../Images/xrplugin.png)

2. Subsequently select the Open XR option.
3. Ensure that all the necessary fixes which may pop up are fixed through **Edit > Project Settings > XR Plugin Management > Project Validation**.

### Hand Tracking

#### Step 1: Add Ultraleap Scoped Registry

1. In Unity, go to **Edit -> Project Settings -> Package Manager**.
2. Add a new scoped registry with the following details:
   - **Name**: Ultraleap
   - **URL**: [https://package.openupm.com](https://package.openupm.com)
   - **Scope(s)**: com.ultraleap
  
 ![scopedregistry](../Images/scopedregistry.png)


#### Step 2: Open Package Manager

1. Open the **Package Manager** by navigating to **Window -> Package Manager**.
2. In the dropdown at the top left of the window, select **My Registries**.

 ![mrregistries](../Images/myregistries.png)


#### Step 3: Install Ultraleap Tracking Package

1. In the list on the left, you should see **Ultraleap UPM packages**.
2. Find the **Ultraleap Tracking** package and select it.
3. Click **Install** in the bottom right corner.


 ![list](../Images/packagelist.png)



#### Step 4: Include Example Content

1. To include sample content that demonstrates many features of the plugin:
   - Select **Samples** for the package in the Package Manager.
   - Import the samples as shown in the Package Manager interface.


 ![imports](../Images/sampleimport.png)

  


#### Step 5: Test the Setup with Capsule Hands Scene

1. To ensure everything is set up correctly:
   - Since we are using desktop mode, we add the **service provider (Desktop)** to the scene.

   ![service provider](../Images/desktop_oritent.png)

   - Open the **Capsule Hands** scene from the package samples. You can find it here:
     - Assets > Samples > Ultraleap Tracking > x.x.x > Examples > 1. XR Examples > 2. Building Blocks > 1. Basics > 1. Capsule Hands.unity
2. Press **Play** in Unity. You should now be able to see your hands tracking in the scene.


 ![sample hands](../Images/capsule-hands-xr.png)



### Adding XR Rig to the Scene

1. **Add the XR Rig** by right clicking under sample scene and convert the main camera to XR Rig.
   
    ![xr rig](../Images/xr-rig.png)

2. **Position the XR Rig** correctly relative to your main camera so that the UltraLeap device can track your hands accurately.

## Basic Interaction: Grabbing an Object

To allow interactions such as grabbing objects in your scene, follow these steps:

1. **Create a 3D object** (e.g., Cube) in your scene by going to **GameObject > 3D Object > Cube**.
2. Select the Cube, and add the **Interaction Behaviour** component:
   - Go to the **Inspector**, click **Add Component**, and search for **Rigidbody**.

3. **Create an Physical Interaction Manager**:
   - In the **Hierarchy**, add an GameObject named **Physical Hands Manager**.
   - Add the **Interaction Manager** component by clicking **Add Component > UltraLeap > Physical Interactions > Physical Hands Manager**.

   ![physical hands manager](../Images/physical-hands-manager.png)

4. **Test Interaction**:
   - Press **Play** in Unity.
   - Use your hands in front of the UltraLeap sensor to grab the Cube.



That's it! You have successfully set up UltraLeap hand tracking in Unity and implemented a basic interaction in your scene. You can now build upon this project to create more complex interactions and virtual environments. 

I will be adding a video tutorial for this setup soon. The sample projects I have created can be found ![here](https://drive.google.com/drive/folders/113gcTg3pcFRkuKl_jSpt5L4TmSt_RQkQ?usp=drive_link). There are 3 demo projects, each showcasing different interactions using UltraLeap Hand Tracking.

## Demo Projects Overview
- **Basic Interaction Project**: Contains simple interaction mechanics.
- **Advanced Interaction Project**: Includes the following interactions:
  1. Grabbing an object
  2. Throwing an object
  3. Rotating an object
  4. Drawing (painting)

## Project Files
- The zip files for both the basic and advanced interaction projects include:
  - Code and assets required to run the project.
  - Build files that can be run on any Windows machine.

## Demo Videos
- The demo videos for these interactions can be found in the linked drive below.


![Demo Videos](https://drive.google.com/drive/folders/1ryPLg95XQumVqqkawhKMK2yDl9PGU4E5?usp=drive_link)

---