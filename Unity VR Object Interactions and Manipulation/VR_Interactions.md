# Interactions and Manipulation in VR (Unity)


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


![packet manager](../Images/vr_5.png)


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

<br>
<br>

**NOTE**
> Since XR Origin already has a camera, hence if you do have an another camera kindly remove it for less confusion.

7. Navigate Projects -> Assets -> Samples -> XR Toolkit -> Starter Assets -> Presets (left Controller)

7. Navigate Projects -> Assets -> Samples -> XR Toolkit -> Starter Assets -> Presets (left Contoller)


![left controller](../Images/vr_11.png)

<br>


8. Do same for right controller

![right controller](../Images/vr_12.png)

9. Import the Oculus package to the unity project

![import oculus](../Images/vr_13.png)

![import oculus](../Images/vr_14.png)

10. Navigate to Project -> Oculus Hands -> Prefabs - drag and drop the models of respective hands under its controllers.

![import hands](../Images/vr_15.png)

![import hands](../Images/vr_16.png)

![import hands](../Images/vr_17.png)


11. Add a New script (AnimateOnHandInput) to manipulate with the help of VR hands


#### With this, the basic VR setup is Complete

### VR Interactions

1. Add a New script (AnimateOnHandInput) to manipulate with the help of VR hands

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.InputSystem;

public class AnimateOnHandInput : MonoBehaviour
{
    // Start is called before the first frame update

    public InputActionProperty pinchAnimationAction;
    public InputActionProperty gripAnimationAction;
    public Animator handAnimator;

    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        float triggerValue = pinchAnimationAction.action.ReadValue<float>();
        handAnimator.SetFloat("Trigger", triggerValue);

        float gripValue = gripAnimationAction.action.ReadValue<float>();
        handAnimator.SetFloat("grip", gripValue);

    }
}
```
2. Add the script to both hand models
![import hands](../Images/vr_18.png)

![import hands](../Images/vr_19.png)


3. Under the Animated on Hand Input, tick both "Pinch Animation Actions" and "Grip Animation Actions" References.
   - For Pinch reference, search Activate Value
   - For Grip reference, search Select Value
   - Drag and drop the "Animator" above into "Hand Animator"



4. Kindly Repeat the above step for both hands.

![import hands](../Images/vr_20.png)


5. Now, Let us add RayCasting in order to interact with distant objects.
   - Right click on Camera offset and navigate to XR -> Ray Interactor
   - Duplicate it,since 2 hands.
   - click on settings of the XR controller and select the respective preset


![import hands](../Images/vr_21.png)

<br>

![import hands](../Images/vr_22.png)


### Conclusion

Now we can build this project and test it on your laptop device. This project will help you understand the basics of VR interactions and manipulations in Unity. You can further enhance this project by adding more features and functionalities.

![build](../Images/vr_23.png)


### The basic interactions and manipulation techniques are now all implemented. Free feel to experiment with other techniques in order to interact with objects.