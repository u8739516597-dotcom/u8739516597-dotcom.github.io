---
title: "Lecture 2: Locomotion Pitch"
date: "2026-02-02"
weight: 7
draft: false
---




### **Lecture 2: Locomotion Pitch**

#### 1. **Slide Link**

3 Creative Ideas for VR Locomotion:

https://drive.google.com/file/d/1Yu3T573hupCwZj9BVJq5NSAc7eCApzyJ/view?usp=sharing

Ptich:

https://drive.google.com/file/d/1e-EcriRIjRLWaMXqHNB59H5v7EqJTJeG/view?usp=sharing





#### 2. **Critical Reflection: Challenges and Improvements**

After testing the prototype, I found three main issues with the "Arm Swing" in fast-paced parkour and how I plan to fix them:

* **Fatigue**:

  * **Problem**: Long courses with fast arm swinging cause user fatigue and reduce the ability to keep going.
  * **Improvement**: I plan to add "sensitivity adjustment." When the arm swing slows down, the system will automatically increase sensitivity to allow for smaller, faster movements.

* **Precision at High Speeds**:

  * **Problem**: When swinging fast, the body shakes a lot, making it hard to accurately pick up small coins in the air.
  * **Improvement**: I added a system that uses distance sensing to create a dynamic "magnet" effect for coins, ensuring players can collect them even at high speeds.

* **Physics Engine Failures (Tunneling)**:

  * **Problem**: At very high speeds, the Unity physics engine sometimes misses triggers, causing the player to fail the level.
  * **Improvement**: I developed a "CheckNearbyBanners" logic that replaces physics checks with distance-based checks to make sure level transitions work properly.



#### 3. **Future Outlook**

To improve further, I have two advanced ideas:

* **Stage 1: Haptic Feedback**:

  * Using controller vibrations to simulate "wind resistance" based on arm swing power, helping to reduce motion sickness caused by visual displacement.


* **Stage 2: Full-Body Multi-Sensor Integration**:

  * Using leg trackers to spread the physical movement across the whole body, reducing fatigue from arm swinging and making the movement feel more natural.



#### 4. **Conclusion**

Good VR movement technology should not only focus on speed but also respect physical limits and predict user fatigue. The main value of the "Arm Swing Power Glide" is that it converts the unstable physical energy from the body into smooth, reliable, and rewarding virtual movement.



