# UltraLeap Motion Controller 2 - Hand Tracking in Unity

This project demonstrates how to set up UltraLeap (Leap Motion) hand tracking in Unity and implement a basic interaction, such as grabbing an object in a virtual environment.

## Table of Contents

1. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
2. [Setting up UltraLeap in Unity](#setting-up-ultraleap-in-unity)
   - [Installing UltraLeap SDK](#installing-ultraleap-sdk)
   - [Adding Hand Tracking to Your Scene](#adding-hand-tracking-to-your-scene)
3. [Basic Interaction: Grabbing an Object](#basic-interaction-grabbing-an-object)
4. [Images](#images)
5. [References and Resources](#references-and-resources)

---

## Getting Started

### Prerequisites

Make sure you have the following software and hardware:

- **Unity** (Latest version recommended, download from [Unity Download Page](https://unity.com/download))
- **UltraLeap Hand Tracking Device** (Download the latest tracking software from [UltraLeap Software Download](https://developer.leapmotion.com/tracking-software-download))
- **UltraLeap SDK for Unity** (Available on the [UltraLeap Developer site](https://developer.leapmotion.com/unity))

### Installation

1. **Download Unity Hub** from [Unity's website](https://unity.com/download).
2. **Install Unity** and make sure to select the build support options for your platform (PC, Android, etc.).
3. **Download and install** the **UltraLeap Hand Tracking Software** and connect your UltraLeap sensor.
4. **Download UltraLeap SDK for Unity** from [UltraLeap Developer Unity](https://developer.leapmotion.com/unity).

## Setting up UltraLeap in Unity

### Installing UltraLeap SDK

1. **Import the UltraLeap SDK**:
    - Download the UltraLeap Unity Modules package.
    - In Unity, navigate to **Assets > Import Package > Custom Package** and select the UltraLeap SDK you downloaded.
    - You should now see a `LeapMotion` folder in your project’s Assets directory.

### Adding Hand Tracking to Your Scene

1. **Drag the Leap Rig prefab** from the `LeapMotion` folder into your scene.
2. The **Leap Rig** prefab includes everything needed for hand tracking (hand models, tracking camera, etc.).

3. **Position the Leap Rig** correctly relative to your main camera so that the UltraLeap device can track your hands accurately.

## Basic Interaction: Grabbing an Object

To allow interactions such as grabbing objects in your scene, follow these steps:

1. **Create a 3D object** (e.g., Cube) in your scene by going to **GameObject > 3D Object > Cube**.
2. Select the Cube, and add the **Interaction Behaviour** component:
   - Go to the **Inspector**, click **Add Component**, and search for **Interaction Behaviour**.
   - Check **Can Be Grasped** to make the object grabbable.

3. **Create an Interaction Manager**:
   - In the **Hierarchy**, create an empty GameObject named **InteractionManager**.
   - Add the **Interaction Manager** component by clicking **Add Component > Interaction Manager**.

4. **Test Interaction**:
   - Press **Play** in Unity.
   - Use your hands in front of the UltraLeap sensor to grab the Cube.

---
