# Unreal Engine Tutorial: VR Physics Based Hands and VR Tablet
In this example project you will find an implementation of a physics based VR hands using OpenXR, and the built in handtraking in the vrajo XR3. In addition a [Blui (WebBrowser Widget)](https://github.com/getnamo/BLUI-Unreal) based VR tablet that you can interact with using your fingers.

Unreal Engine version 5.1

You will find the blue prints in those two actors, Tablet and VRPawn

![image](https://github.com/user-attachments/assets/0f58b9ae-5d0d-4c02-96df-4793cf867ed9)

___
## VR Physics Based Hands
We will build on the two part "VR Procedural Virtual Hand Mesh Animation Using OpenXR Hand-Tracking" tutorial [Part 1](https://www.youtube.com/watch?v=TPEA1GJr_kU&t) [Part 2](https://www.youtube.com/watch?v=xEnuephuNmw&t) by Mamadou Babaei for the OpenXR hand tracking.

See [PhysicsBasedHands.md](./PhysicsBasedHands.md)

___
## VR Tablet With Blui
See [VRTabletWithBlui.md](./VRTabletWithBlui.md)

___
## Tie them together
to make the interaction between the finger tips and the tablet posible you need to add collision spheres on the finger tips and ensure that generate overlap is enabled.

![image](https://github.com/user-attachments/assets/3503aae8-a58c-473f-99dd-117b132abdfc)
![image](https://github.com/user-attachments/assets/73f9d582-8aa2-4eca-9f56-cc45ac85c30d)

make sure to make the parent socket of the spheres the related bone you want. Example:

![image](https://github.com/user-attachments/assets/707f76e4-2713-4753-b814-a55be43ffd6d)






