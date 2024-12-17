Below is a detailed, step-by-step demo of integrating the MX Ink stylus into a Unity project, using the Meta Core SDK, and setting it up so that it can interact with the Meta Quest headset environment. This tutorial also covers pairing with the Meta Horizon app and establishing a basic drawing experience in a VR scene using Unity. It’s intended as a comprehensive walkthrough, from pairing your stylus with your Quest headset all the way to rendering stylus-driven brush strokes in a 3D space.

---

### Prerequisites

1. **Hardware:**
   - Meta Quest 3 (or supported Meta VR headset)
   - MX Ink Stylus (Logitech VR Ink Stylus)
   - A suitable working environment with your Quest headset.

2. **Software:**
   - Unity 2021.3 LTS or later, although you can use newer versions if they are compatible with the Meta SDKs.
   - Meta (Oculus) Integration Package (Core SDK and/or OpenXR Plugin depending on your approach)
   - Git/GitHub client or a web browser for downloading required assets.
   - MX Ink stylus Unity Integration Assets (provided by Logitech; a GitHub URL or package that you clone or download)

3. **Developer Accounts & Setup:**
   - Meta Quest developer mode enabled on your device.
   - Proper setup of the Meta Quest environment and platform utilities.

---

### Step 1: Pairing the MX Ink Stylus with the Meta Quest

Before you begin in Unity, ensure that your MX Ink stylus is paired with your Quest headset.

1. **Install the Meta Horizon Mobile App:**
   - Download the Meta Quest (formerly Oculus) mobile app on your smartphone.
   - Log in with the same account you use on your Quest headset.

2. **Pairing the Stylus:**
   - With your Quest headset turned on and connected to the same account as the mobile app, open the **Meta Horizon mobile app** on your phone.
   - Go to **Headset Settings** and select the Quest device you’re working with.
   - Find **Controllers** and tap **Pair New Controller**.
   - From the list, select **Pair Stylus**.
   - On your MX Ink Stylus, hold down the **Meta button** along with the **rear button** for about 4 seconds. The stylus should enter pairing mode.
   - The app will detect the stylus. Once detected, it may either connect immediately or prompt you to update the stylus firmware. If a firmware update is needed, complete that step.
   - After this process, your MX Ink Stylus will be recognized as an input device by your Quest headset.

3. **Alternative Step**
    - If you’re using the stylus with a Meta SDK (Oculus Integration), you may pair it directly through the Quest headset’s settings.
    - Go to **Settings** > **Devices** > **Bluetooth Devices**.
    - Hold down the **Meta button** and **rear button** on the stylus to enter pairing mode.
    - Select **Pair New Device** on the Quest and choose the stylus from the list of available devices.

**Verification Step:**  
Inside your Quest headset’s Settings > Devices, you should now see the stylus listed as a paired input device. Additionally, the stylus might show indicators or haptic feedback confirming connection.

---

### Step 2: Preparing the Unity Project

1. **Create or Open Your Unity Project:**
   - Launch Unity Hub and create a new 3D project (Unity 2021.3 LTS or higher is recommended).
   - Once open, configure your project for VR. Go to **Project Settings** > **XR Plug-in Management** and enable either:
     - **Meta Oculus (Core) SDK Support**, or
     - **OpenXR** with the Meta Quest feature sets enabled.

2. **Install the Meta/Oculus Integration Packages:**
   - Download and import the latest **Meta (Oculus) Integration** from the Unity Asset Store or from the Oculus Developer website. Look for version **v68 or later** (at the time of this tutorial, v69 is also suitable).
   - If using **OpenXR**, ensure you have the **OpenXR Plugin** from Unity’s Package Manager and enable the Quest device features under **Project Settings** > **XR Plug-in Management** > **OpenXR**.

3. **Clean and Configure Project Settings:**
   - Remove any legacy Oculus SDK packages if they conflict with the new integration.
   - In **Project Settings > Player > Other Settings**, set the scripting backend to IL2CPP and API Compatibility Level to .NET Standard 2.1 for optimal performance.
   - Ensure **Quest 3** and **Quest Pro** support is enabled if using the OpenXR path.

---

### Step 3: Integrating the MX Ink Stylus Unity Assets

1. **Download MX Ink Stylus Assets:**
   - Navigate to the GitHub repository provided by the Logitech team. You may have a URL such as `https://github.com/YourOrg/MXInkUnityIntegration` (example URL).
   - Clone or download the repository as a ZIP.
   - Extract the files locally.

2. **Import Stylus Assets into Unity:**
   - In your Unity project, go to **Assets > Import Package > Custom Package…** and select the extracted MX Ink Stylus asset folder, or simply drag the folder into your **Assets** directory.
   - After import, you should see a folder (e.g., `MXInkIntegration` or `LogitechMXInk`) containing:
     - **Prefabs:** A stylus prefab for tracking.
     - **Scripts:** Input handling scripts for reading stylus input data.
     - **Resources:** Action maps or input definitions required for reading stylus states.
   
3. **Action Mappings:**
   - The stylus integration typically requires action maps that tell the OVR (Oculus VR) or OpenXR Input System what to listen to.
   - Go to the stylus integration folder’s **Resources** directory and note the action definitions.
   - Open **OVR Input/Action** settings (for the Meta SDK) or **OpenXR Input Mappings** if using OpenXR, and load or reference the provided action sets.

---

### Step 4: Scene Setup

1. **Create a Test Scene:**
   - In your **Scenes** folder, create a new scene named `MXInkDemo`.
   - Open this scene.
   
2. **Add an XR Rig or OVR Player Controller:**
   - For Meta SDK: Drag an **OVRCameraRig** prefab (from the Oculus Integration package) into the scene. This provides head tracking and VR camera setup.
   - For OpenXR: Use the **XR Origin** or **XROrigin (Action-Based)** prefab from Unity’s XR Interaction Toolkit.

3. **Place the Stylus Prefab:**
   - From the MX Ink assets, locate the **Stylus Prefab**.
   - Drag and drop the stylus prefab into the scene. Normally, this prefab is updated at runtime to match the stylus’ real-world position. You do not need to manually position it; just ensure it’s in the scene hierarchy.
   
4. **Input Action Associations:**
   - Select the stylus prefab in the Hierarchy.
   - In the Inspector, find the stylus script component that references action names. You will need to assign the action maps (e.g., **StylusPositionAction**, **StylusPressureAction**) from the Resources folder.
   - This ensures the stylus script can query the VR runtime for its position, orientation, tip pressure, and button states.

---

### Step 5: Tracking the Stylus in Play Mode

1. **Enter Play Mode:**
   - Press Play in the Unity Editor (with your Quest connected to your PC and Link enabled, or after building and deploying to the headset).
   - You should see that the stylus position and orientation matches the physical device in space.
   - Move your stylus around in the real world while viewing through the headset (if connected via Link) or after deploying the build. The stylus object in Unity should move correspondingly.

2. **Verification:**
   - Ensure button presses and tip pressure readings are functional. The provided sample code often includes debug logs. Check the Console for any errors or confirmation messages that input is being read.
   - Confirm that the stylus turns certain materials on and off or changes color based on its input state (if the demonstration code you integrated includes visual feedback).

---

### Step 6: Enabling Drawing with the Stylus

The magic of the MX Ink stylus comes from its ability to provide tip pressure and input that can drive drawing or painting actions in 3D space.

1. **Script Setup for Drawing:**
   - Create a new script called `StylusDrawing.cs` and attach it to the Stylus prefab or a dedicated GameObject.
   - This script will:
     - Listen for stylus tip pressure values (T-values).
     - If the tip pressure is above a certain threshold, start drawing a line.
     - Use a **LineRenderer** to render strokes as you move the stylus.

2. **Example Drawing Code Snippet:**
   ```csharp

    using UnityEngine;
    using System.Collections.Generic;

    public class MXInkStylusHandler : MonoBehaviour
    {
        [SerializeField] private GameObject mxInkModel;

        [SerializeField] private GameObject clusterFront;
        [SerializeField] private GameObject clusterMiddle;
        [SerializeField] private GameObject clusterBack;

        [SerializeField] private GameObject leftController;
        [SerializeField] private GameObject rightController;

        public Color activeColor = Color.green;
        public Color doubleTapActiveColor = Color.cyan;
        public Color defaultColor = Color.white;

        private StylusInputs stylus;
        private LineRenderer currentLine;
        private bool isDrawing;
        private List<LineRenderer> drawnLines = new List<LineRenderer>(); // Store drawn lines

        // Defined action names.
        private const string MX_Ink_Pose_Right = "aim_right";
        private const string MX_Ink_Pose_Left = "aim_left";
        private const string MX_Ink_ClusterFront = "front";
        private const string MX_Ink_ClusterBack = "back";
        private const string MX_Ink_Docked = "docked";
        private const string MX_Ink_Haptic_Pulse = "haptic_pulse";
        private float hapticClickDuration = 0.011f;
        private float hapticClickAmplitude = 1.0f;

        private void UpdatePose()
        {
            var leftDevice = OVRPlugin.GetCurrentInteractionProfileName(OVRPlugin.Hand.HandLeft);
            var rightDevice = OVRPlugin.GetCurrentInteractionProfileName(OVRPlugin.Hand.HandRight);

            bool stylusIsOnLeftHand = leftDevice.Contains("logitech");
            bool stylusIsOnRightHand = rightDevice.Contains("logitech");

            stylus.isActive = stylusIsOnLeftHand || stylusIsOnRightHand;
            stylus.isOnRightHand = stylusIsOnRightHand;

            string MX_Ink_Pose = stylus.isOnRightHand ? MX_Ink_Pose_Right : MX_Ink_Pose_Left;

            mxInkModel.SetActive(stylus.isActive);
            rightController.SetActive(!stylus.isOnRightHand || !stylus.isActive);
            leftController.SetActive(stylus.isOnRightHand || !stylus.isActive);

            if (OVRPlugin.GetActionStatePose(MX_Ink_Pose, out OVRPlugin.Posef handPose))
            {
                transform.localPosition = handPose.Position.FromFlippedZVector3f();
                transform.localRotation = handPose.Orientation.FromFlippedZQuatf();
                stylus.inkingPose.position = transform.localPosition;
                stylus.inkingPose.rotation = transform.localRotation;
            }
        }

        private void Update()
        {
            OVRInput.Update();
            UpdatePose();

            if (!OVRPlugin.GetActionStateBoolean(MX_Ink_ClusterFront, out stylus.clusterFrontValue))
            {
                Debug.LogError($"MX_Ink: Error getting action name: {MX_Ink_ClusterFront}");
            }

            if (!OVRPlugin.GetActionStateBoolean(MX_Ink_ClusterBack, out stylus.clusterBackValue))
            {
                Debug.LogError($"MX_Ink: Error getting action name: {MX_Ink_ClusterBack}");
            }

            if (!OVRPlugin.GetActionStateBoolean(MX_Ink_Docked, out stylus.docked))
            {
                Debug.LogError($"MX_Ink: Error getting action name: {MX_Ink_Docked}");
            }

            stylus.any = stylus.clusterFrontValue || stylus.clusterMiddleValue > 0 || stylus.clusterBackValue;

            clusterFront.GetComponent<MeshRenderer>().material.color = stylus.clusterFrontValue ? activeColor : defaultColor;
            clusterMiddle.GetComponent<MeshRenderer>().material.color = stylus.clusterMiddleValue > 0 ? activeColor : defaultColor;

            if (stylus.clusterBackValue)
            {
                clusterBack.GetComponent<MeshRenderer>().material.color = activeColor;
            }
            else
            {
                clusterBack.GetComponent<MeshRenderer>().material.color = defaultColor;
            }

            // Trigger erasing or drawing based on cluster front or back
            if (stylus.clusterBackValue)
            {
                EraseLine();
            }
            else if (stylus.clusterFrontValue)
            {
                DrawLine();
            }
            else
            {
                // Stop drawing if the front cluster is released
                StopDrawing();
            }

            // Haptic pulse (optional)
            if (stylus.clusterBackValue)
            {
                TriggerHapticClick();
            }
        }

        public void TriggerHapticPulse(float amplitude, float duration)
        {
            OVRPlugin.Hand holdingHand = stylus.isOnRightHand ? OVRPlugin.Hand.HandRight : OVRPlugin.Hand.HandLeft;
            OVRPlugin.TriggerVibrationAction(MX_Ink_Haptic_Pulse, holdingHand, duration, amplitude);
        }

        public void TriggerHapticClick()
        {
            TriggerHapticPulse(hapticClickAmplitude, hapticClickDuration);
        }

        private void DrawLine()
        {
            if (!isDrawing)
            {
                // Start a new line if not currently drawing
                currentLine = new GameObject("Line").AddComponent<LineRenderer>();
                currentLine.positionCount = 0;
                currentLine.material = new Material(Shader.Find("Sprites/Default"));
                currentLine.startColor = activeColor;  // Change to active color to reflect drawing state
                currentLine.endColor = activeColor;    // Change to active color
                currentLine.startWidth = 0.0025f;
                currentLine.endWidth = 0.0025f;
                isDrawing = true;
            }

            // Update line with current position
            currentLine.positionCount++;
            currentLine.SetPosition(currentLine.positionCount - 1, stylus.inkingPose.position);
        }

        private void EraseLine()
        {
            if (drawnLines.Count > 0)
            {
                // Remove the most recent line (last drawn line)
                LineRenderer lastLine = drawnLines[drawnLines.Count - 1];
                if (lastLine != null)
                {
                    Destroy(lastLine.gameObject);  // Destroy the last line object
                    drawnLines.RemoveAt(drawnLines.Count - 1);  // Remove it from the list
                }
            }
        }

        private void StopDrawing()
        {
            if (isDrawing)
            {
                isDrawing = false;
                drawnLines.Add(currentLine); // Add the current line to the list
                currentLine = null; // Reset the current line to avoid connecting new lines to old ones
            }
        }
    }
   ```

   **Note:** The `StylusInputHandler` is a placeholder for the logic that reads from the OVR action sets or OpenXR Input. You’ll need to integrate this according to the stylus scripts included in the provided assets. Typically, the provided stylus code snippet shows how to query `OVRInput.Get()` or equivalent OpenXR calls to get positions and tip pressure values.

3. **Assign the StylusInputHandler:**
   - The assets you imported should have a script that reads input from the stylus. Assign this script as the `stylusInput` reference in the inspector for `StylusDrawing`.
   - Ensure that the stylus input script is properly configured with the action maps so it can provide real data.

4. **Test Drawing:**
   - Play the scene again. Now, when you press the stylus tip against a real surface (like a table or a book in your room), the tip pressure should increase. As soon as the threshold is met, a line is started and drawn as you move the stylus.
   - You’ll see a red line (or whatever color you chose) following the trajectory of the stylus.

---

### Step 7: Additional Enhancements

- **Haptics:**  
  You can trigger haptic feedback on the stylus to give the user tactile responses. Refer to the provided code snippets from the Logitech documentation, which show how to call haptic functions through the SDK.

- **Color Changing / Material Interactions:**  
  Use the input values from stylus buttons to cycle through colors or brush sizes. For instance, pressing a side button on the stylus could change the drawing color.

- **Advanced Interaction:**
  Combine the stylus input with plane detection (if using Passthrough or AR features on Quest) so that drawing lines appear "anchored" onto real surfaces detected by the Quest’s environment understanding.

---

### Step 8: Deployment and Testing on Quest

1. **Build and Run:**
   - Go to **File > Build Settings** and switch platform to **Android**, if not already.
   - Ensure that **Quest** is recognized by enabling "XR" in the player settings.
   - Click **Build and Run** with the headset connected via USB.
   - Once deployed, put on the headset, pick up the stylus, and test the drawing experience directly in VR.

2. **Optimization & Refinement:**
   - If latency or performance is an issue, consider optimizing your line rendering or adjusting the frequency of new points being added.
   - Experiment with different threshold values and line widths for a better user experience.

---

### Conclusion

By following the above steps, you’ve:

- Paired the MX Ink Stylus with the Meta Quest headset.
- Integrated stylus tracking and input actions into a Unity project using the Meta Core SDK or OpenXR.
- Added a simple drawing system that responds to stylus tip pressure, allowing you to draw in a VR environment.
- Verified precision, latency, and responsiveness of the stylus input.

Check out the following video [Logitech MX Ink Stylus for Meta Quest](https://www.youtube.com/watch?v=o5xn52ARebg) for futher support.

The MX Ink stylus provides a more natural and precise input method than traditional controllers or hand tracking for tasks such as drawing, annotating, or interacting with fine details in VR. With these steps complete, you have a solid foundation from which to build more complex interactions and applications.
