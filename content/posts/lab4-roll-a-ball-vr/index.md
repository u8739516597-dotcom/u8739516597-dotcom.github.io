---

title: "Lab 4: Unity Roll-a-Ball in VR"

date: 2026-01-26

weight: 5

summary: "Converted Roll-a-Ball to VR: Android build setup, Meta SDK import, XR settings, scene setup, direct selection + raycasting. Documented issues and what I tried."

tags:
  - Unity
  - VR
  - Lab
  - Mixed Reality
draft: false

---

Overview

In this lab, I converted the Roll-a-Ball project to VR. I set the project to Android, imported the Meta SDK, enabled XR, and tested interactions in VR.



---



**Step 1: Create a 3D project and switch to Android platform**

<img src="4fig01.png" width="300" />








---



 **Step 2: Import Meta All-in-one SDK**

Problem: At first, I could not find tutorial examples, so I checked the README file and followed it.

<img src="4fig02.png" width="400" />




---



 **Step 3: Install XR Plugin Management**

<img src="4fig03.png" width="400" />





---



 **Step 4: Create a new scene**

<img src="4fig04.png" width="400" />




---



 **Step 5: Settings for controllers**

<img src="4fig05.png" width="300" />




---



**Step 6: Setup the scene**

<img src="4fig06.png" width="400" />




One major problem I encountered was that, since I’m working on a MacBook, I couldn’t run or test the VR project directly on a Meta headset. To overcome this, I had to rely on the Meta XR Simulator for development and testing. This required configuring the project in Unity 2022, ensuring compatibility with the OpenXR plugin, and properly setting up the simulator as the active runtime. Only after completing these steps was I finally able to simulate controller and headset input on my local machine.

<img src="4fig07.png" width="400" />




---



**Step 7: Add collider for Roll-a-Ball**

<img src="4fig08.png" width="400" />




---



**Step 8: Add layers and assign them to objects**

At first, I did not understand layers clearly. Later, I realized layers are just labels for detection. The order does not matter.

<img src="4fig09.png" width="300" />


<img src="4fig10.png" width="300" />


<img src="4fig11.png" width="300" />



---



 **Step 9: Add collider to hand anchors and set them to the selection layer**

<img src="4fig12.png" width="200" />

<img src="4fig13.png" width="200" />


---



**Step 10: Disable collision between ?oll-a-Ball??and ?election??layers**

<img src="4fig14.png" width="300" />

---



 **Step 11: Add Rigidbody and set different values**

Because we use trigger events, objects need Rigidbody. Hand anchors are set to Kinematic (no gravity). The ball uses gravity (not kinematic).

<img src="4fig15.png" width="200" />

<img src="4fig16.png" width="200" />
<img src="4fig17.png" width="200" />



---



 **Step 12: write the interaction script and assign it to the hand anchor**
<img src="4fig18.png" width="400" />
<img src="4fig19.png" width="400" />
<img src="4fig20.png" width="400" />



In this step we wrote a script allowing the controller to pick up and release a ball in VR. When the controller enters the ball? collider and the player pulls the trigger, the ball becomes a child of the controller and follows its movement. When the trigger is released, the ball is detached, gravity is enabled again, and the ball continues moving based on the velocity of the hand.


Direct Selection
<img src="4fig21.png" width="300" />




---



**Problems / Notes**

  **1) PickUp objects no longer detected**

I implemented direct selection and grabbing, but the original PickUp detection stopped working. I checked colliders, trigger settings, tags, and layers, but it still did not work. Even when I created a new cube with `Is Trigger` and tag `PickUp`, nothing appeared in the console.

<img src="4fig22.png" width="300" />





  **2) Raycasting issue (material / color)**

I tried to change the object color when hit by the ray, but I lost the material. In the end, I only displayed the ray and used it to move the object.

<img src="4fig23.png" width="300" />




---



  **Result**

The VR version can run in VR, and direct selection works (grab/release). Raycasting partially works (ray + moving object).




