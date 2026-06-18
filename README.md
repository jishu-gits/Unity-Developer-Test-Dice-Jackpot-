# Dice Jackpot 3D

A 3D physics-based casino-style dice game built as a Unity Developer Test. 

## How to Play

### Option 1: Play the Standalone Build
1. Download and extract the `DiceJackpot_Build.zip` folder.
2. Run the executable file (`.exe`) located inside the extracted folder.
3. Click the **Roll** button to toss the dice.

### Option 2: View the Source Code
1. Open Unity Hub and create a new 3D project (Unity 6000.x / Unity 6 recommended).
2. Drag and drop the `.unitypackage` file into the Unity Editor's Project window.
3. Click **Import All**.
4. Open the primary scene to view the hierarchy, scripts, and component setup.

## Features & Implementation Highlights

### Core Requirements
* **3D Physics Integration (Major Plus):** Bypassed 2D sprites to utilize Unity's native Rigidbody system. Applies randomized `AddForce` and `AddTorque` for organic, unpredictable dice throws.
* **Dynamic Face Detection:** Eliminates the need for hardcoded animations by using Vector3 Dot Product math against `Vector3.up`. This mathematically detects which numbered face is pointing at the ceiling once the physical velocity settles.
* **The Pity System Algorithm:** Tracks consecutive player losses. Upon reaching 3 losses, the system intercepts the standard physics roll on the 4th attempt to guarantee a Jackpot win.

### Bonus Points Achieved
* **Easing & Procedural Animation:** The guaranteed Pity System win avoids jarring visual snaps. It utilizes a custom Coroutine combining `Mathf.SmoothStep` (easing), `Vector3.Lerp`, and `Quaternion.Slerp` to seamlessly transition the dice from a mid-air physical toss into a perfectly aligned, mathematically calculated winning position.
*  **Physics Interaction:** Implemented invisible physical bounds to contain the dice within the table area, ensuring reliable, contained physics interactions.
*  **Visual Polish:** Integrated a custom confetti Particle System that strictly triggers upon a successful Jackpot evaluation.
*  **Audio Elements:** Configured an `AudioSource` via script to play localized rolling sound effects during the toss phase and a dedicated victory chime upon a successful match.
