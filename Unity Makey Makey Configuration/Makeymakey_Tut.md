# Tutorial: Object locomotion and manipulation with Makey Makey in Unity

## Overview

In this tutorial, you’ll learn how to use a Makey Makey kit to control the movement of an object in Unity. We’ll map the Makey Makey’s arrow keys to move a cube around a 2D scene.

---

## Prerequisites

- A Makey Makey kit.
- Unity installed on your computer.
- Basic understanding of Unity's interface and scripting.

---

## Step 1: Setting Up Your Makey Makey

1. **Plug in your Makey Makey** to your computer using the USB cable.
2. **Connect alligator clips:**
   - Attach clips to the **Arrow Keys (Up, Down, Left, Right)** and connect them to conductive materials.
   - Make sure you hold the **Earth/Ground** connection while testing.

3. **Test inputs:**
   - Open a text editor and press your conductive materials to ensure they output the corresponding arrow keys.

---

## Step 2: Setting Up Unity

1. **Create a new Unity Project:**
   - Open Unity and create a 2D or 3D project.

2. **Create a Scene:**
   - Add a **2D sprite** or **3D cube** to the scene. This will be the object we’ll move around.
   - Rename it to `Player`.

3. **Adjust the Camera:**
   - For a 2D scene, set the camera to orthographic.
   - Ensure the player object is visible in the camera view.

---

## Step 3: Writing the Movement Script

1. **Create a Script:**
   - In the Unity project, create a new C# script called `PlayerMovement`.

2. **Open the Script:**
   - Double-click the script to open it in your code editor (e.g., Visual Studio).

3. **Write the Movement Code:**
   - Replace the default code with the following:

   ```csharp
   using UnityEngine;

   public class PlayerMovement : MonoBehaviour
   {
       public float speed = 5f; // Speed of movement

       void Update()
       {
           // Get input from Makey Makey's arrow keys
           float horizontal = 0f;
           float vertical = 0f;

           if (Input.GetKey(KeyCode.UpArrow))
               vertical = 1f;
           if (Input.GetKey(KeyCode.DownArrow))
               vertical = -1f;
           if (Input.GetKey(KeyCode.LeftArrow))
               horizontal = -1f;
           if (Input.GetKey(KeyCode.RightArrow))
               horizontal = 1f;

           // Move the player object
           Vector3 movement = new Vector3(horizontal, vertical, 0f);
           transform.Translate(movement * speed * Time.deltaTime);
       }
   }
   ```

4. **Save the Script** and return to Unity.

---

## Step 4: Applying the Script

1. **Attach the Script:**
   - Drag the `PlayerMovement` script onto the `Player` object in the Unity hierarchy.

2. **Set Speed:**
   - In the Inspector, set the `Speed` value (e.g., `5`).

---

## Step 5: Testing with Makey Makey

1. **Play the Scene:**
   - Click the **Play** button in Unity.

2. **Test Movement:**
   - Use the conductive materials attached to the Makey Makey’s arrow keys to move the player object.
   - Press **Up, Down, Left, and Right** to see the object move in those directions.

---

## Step 6: Enhancements (Optional)

### Add a Background
- Add a simple background (e.g., an image or color) to make the scene look better.

### Add Collision
- Use Unity’s **Box Collider** or **Rigidbody** to make the player collide with walls or objects.

### Add Visual Feedback
- Add animations or effects that trigger when the object moves.

---

## Troubleshooting

- **Object doesn’t move:**
  - Check if the script is attached to the correct object.
  - Verify the Makey Makey inputs in a text editor.
- **Slow or fast movement:**
  - Adjust the `Speed` variable in the script.

---

## Final Notes

This basic setup demonstrates how to use a Makey Makey to control an object in Unity. From here, you can expand the project into a game by adding objectives, enemies, or interactive elements.