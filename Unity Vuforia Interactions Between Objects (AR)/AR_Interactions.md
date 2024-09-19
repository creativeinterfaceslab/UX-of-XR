# AR Interactions

This tutorial illustrates the interaction between two AR objects and their behaviour upon contact. Please ensure you have Unity and Vuforia installed before you dive into this tutorial. 
This tutorial guides you through setting up an augmented reality environment using Unity and Vuforia to create a collision simulation between two 3D models representing cars.

## Unity Project Setup

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


## Vuforia AR Camera Set Up

1. In the menu toolbar, navigate to GameObject > Vuforia > AR Camera.

<img width="940" alt="Screenshot 2023-08-31 at 7 58 58 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/2dfd7a68-50bc-4c16-beac-fd6061f03f87">

2. Rename the camera to "Vuforia_ARCamera" for better identification. Delete the other 2 objects "AR Session" & "AR Session Origin"

<img width="210" alt="Screenshot 2023-08-31 at 8 24 02 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/e3756f10-136f-4532-9ef6-1f4b476a4b22">

3. Navigate to Assets > Resources > Vuforia Configuration, Add Vuforia License Key

<img width="1504" alt="Screenshot 2023-08-31 at 8 17 55 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/29ff80a7-aec3-44c0-972a-654c0626364d">

## Vuforia License Key

- Login to the [Vuforia License Manager](https://developer.vuforia.com/vui/develop/licenses) page with the Vuforia Account you created. Click on Add License Key to create a free key enabling your Unity application to use Vuforia's image recognition services.

1. Click "Get Basic" (FREE) and give a name to your License Key.

<img width="1213" alt="Screenshot 2023-08-31 at 8 40 10 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/2cdae7a2-7d28-4afe-b018-7c1ea0b5e41f">



<img width="1213" alt="Screenshot 2023-08-31 at 8 43 50 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/7038972c-9f30-401a-9fa2-e5b5bba9f8fb">

2. Click on the License Name, and it will have the Vuforia license key. Copy and paste into the Vuforia Configuration App License key text field in the Unity application.

<img width="1213" alt="Screenshot 2023-08-31 at 8 48 07 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/0a4647aa-a299-410e-88b4-9e749b9bb6ff">


<img width="1213" alt="Screenshot 2023-08-31 at 8 53 44 PM" src="https://github.com/dhyanpatel3010/Vuforia_Unity-Configuration/assets/76202184/76af35f5-667a-4325-afc5-ff9acdf72f13">

## Target Management

- This step is crucial since target management containing databases helps the Vuforia Engine identify the target image.
  
1. We need the Vuforia Engine to recognise two objects simultaneously, hence, we need to make a few changes in the Vuforia Configurations file.

<img width="1181" alt="Screenshot 2023-11-03 at 8 28 35 pm" src="https://github.com/Dhyan-21041/AR_Demo/assets/106147710/1fc66f55-4501-446a-9770-705085d9ec83">


## Vuforia ImageTarget and Collider Setup

1. Let's first create and add the `ImageTarget`.

<img width="1178" alt="Screenshot 2023-11-03 at 8 44 49 pm" src="https://github.com/Dhyan-21041/AR_Demo/assets/106147710/2edd5e18-2093-469e-b9d3-fd21f021907a">

2. Select the first `ImageTarget` added to the Hierarchy and drag the first of the two 3D models onto the `ImageTarget`, making it a child of the `ImageTarget`.

3. Select the game object instance containing the 3D model and add a `RigidBody` component, ensuring to set `Use Gravity` to `False` and `Is Kinematic` to `True`.

<img width="1182" alt="Screenshot 2023-11-03 at 8 48 48 pm" src="https://github.com/Dhyan-21041/AR_Demo/assets/106147710/a48b9d6d-47b5-4db3-9924-9710cd94cf77">

4. Within the 3D model, identify the child game object associated with the `Mesh Renderer` component. Add both `BoxCollider` and `CapsuleCollider` components to this child game object, setting the `IsTrigger` option to `True`.

<img width="1180" alt="Screenshot 2023-11-03 at 8 51 11 pm" src="https://github.com/Dhyan-21041/AR_Demo/assets/106147710/d872d79a-0b31-4bb1-9fe7-8094a6dbd98d">

5. Once this is done, you have to create a smoke or flame effect to simulate the impact; even if exaggerated, it is ultimately a game, so either you build it yourself with the Particle System, or you get a free one available on the Unity Asset Store.

6. As you will certainly have noticed, the figure also shows a component called ColliderManager, which is the script you need to create to manage the collision; then create a CSharp script and paste the following code into it.

```csharp
   using System.Collections;
   using System.Collections.Generic;
   using UnityEngine;

   public class ColliderManager : MonoBehaviour
   {
       private static ParticleSystem fireFront;
       private static ParticleSystem fireBack;

       void Start ()
       {
           fireFront = GameObject.FindGameObjectWithTag("FireFrontA").GetComponent<ParticleSystem>();
           fireBack = GameObject.FindGameObjectWithTag("FireBackA").GetComponent<ParticleSystem>();
       }

       void OnTriggerEnter(Collider other)
       {
           if (other is BoxCollider)
           {
               fireFront.Play(true);
           }
           else if (other is CapsuleCollider)
           {
               fireBack.Play(true);
           }
       }
   }
```
- In the `Start()` method, the private variables `FireFront` and `FireBack` are assigned to two effect instances using `GameObject.FindGameObjectWithTag("FireFrontA").GetComponent<ParticleSystem>()`. For simplicity, tags are utilized, necessitating the creation of `FireFrontA` and `FireBackA` tags, which should be associated with the game objects containing the explosion effects. Note that in augmented reality, the collider is triggered by the 3D model displayed by Vuforia, not the physical target held in hand.

- Within the `OnTriggerEnter()` event, a check is performed to identify the intercepted collider and execute the corresponding effect.

- Conversely, the `OnTriggerExit()` event is triggered when a vehicle ceases to touch the other car's collider, containing instructions to halt the effects if they are ongoing.

## Conclusion

- Assuming all preceding steps have been accurately followed, upon pressing the play button and upon camera recognition of the objects, their respective 3D models will appear. As you manoeuvre them closer and induce a collision, a dramatic explosion 💥 will take place.


![Screenshot 2023-11-03 at 9 28 35 pm](https://github.com/Dhyan-21041/AR_Demo/assets/106147710/e0c52a75-5e78-45df-b9e2-fc66404fc99a)

#### Thank you for completing this tutorial! We hope you have gained a deeper understanding of handling collisions in augmented reality using Unity and Vuforia. Your engagement and effort in following through with the steps are highly appreciated.
