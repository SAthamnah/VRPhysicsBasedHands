# VRPhysicsBasedHands

This project will use the built in handtraking in the vrajo XR3

make sure that you have openXR turned on in the varjo base software.
![image](https://github.com/user-attachments/assets/378a791f-cecf-48e0-9d8b-b063beb60109)

add varjo openXR to unreal
https://www.fab.com/listings/aac38f51-491b-4b92-95bf-8ce04311a2ff

go to the plugin menu and turn OpenXR, OpenXRHandTracking, and Varjo OpenXR on
![image](https://github.com/user-attachments/assets/86ecbf8a-395e-4056-81fb-006add27f679)

follow this tutorial to get your hands in VR:
[Part1](https://www.youtube.com/watch?v=TPEA1GJr_kU)
[Part2](https://www.youtube.com/watch?v=xEnuephuNmw)

you will notice that the hands you have after finishing the tutorial do not have physics
so, we will be doing that 

first step, right click on the XRHand model and create physics
![image](https://github.com/user-attachments/assets/f4d04b8b-5781-4a1b-96ed-afdbbe051bbf)

press create asset
![image](https://github.com/user-attachments/assets/47b51305-d1c9-4235-91ed-d2914cd9d223)

select the already created capsel and delete it
![image](https://github.com/user-attachments/assets/1c7fa181-1422-43f1-a527-4a67354da494)

in the skeleton tree menu press on the steeting icon then show all bones
![image](https://github.com/user-attachments/assets/d25aaf7e-e38e-4b95-b8f3-6f8485b49f0a)

we have active and unactive bones, select the ones you want to create physics for.
![image](https://github.com/user-attachments/assets/40fd3ce3-bc1e-465b-92ff-02f200a44802)
![image](https://github.com/user-attachments/assets/00b76ffd-e96f-400f-8df0-d4f51b269ae3)

on the right side, in the tools menu press on add bodies
![image](https://github.com/user-attachments/assets/38ac5b3f-020f-42c3-8514-e1d472eef85e)
you will have something like this
![image](https://github.com/user-attachments/assets/fc1b6869-a425-4bc2-86bd-320e2ef219fd)

press on character, then none for the constraint drawing
![image](https://github.com/user-attachments/assets/a4f2bf79-6770-4846-8e9f-53e8abe9e7e3)

you will see something like this
![image](https://github.com/user-attachments/assets/2fbf976c-9a1d-4549-8054-a79acfda3147)

adgust each size and rotation so it looks fine/normal
![image](https://github.com/user-attachments/assets/8d2b4066-7b5a-4bff-a908-4b3cc8cd9418)
![image](https://github.com/user-attachments/assets/0aa1a915-54cc-471e-b5d5-293bc5fda49f)

it could look like this
![image](https://github.com/user-attachments/assets/cfcc5879-2784-4c18-b705-20f8104dd67b)

right click on the wrist capcel and press on add shap then box.
![image](https://github.com/user-attachments/assets/8aad26fd-7950-4107-823c-5465ca5ae1ef)

right click again on the capcel and delete it
adgust the box size and location to best fit the hand shap
![image](https://github.com/user-attachments/assets/6a337fd7-0a55-4737-8459-9261108bfe88)

save

now if you press simulate you will see something like this
![image](https://github.com/user-attachments/assets/586ab5eb-26a9-47ec-8cfd-dd828d6330d2)
![image](https://github.com/user-attachments/assets/c1157648-7a2d-4be3-be5c-1321bee39245)

go back to the skeleton tree menu and hide the bones
![image](https://github.com/user-attachments/assets/1ab1fb2f-1480-4a57-861f-bae55ed4ba5e)

right click in the skeleton tree and press select all constrains
![image](https://github.com/user-attachments/assets/faae4e9a-2d7a-4888-b124-aef803b7bf9e)

scroll down in the details menu and turn on SLERP for both oriantation and velocity, modify the orientation stringth to 1500
![image](https://github.com/user-attachments/assets/5aed3ae5-e284-493b-9cd8-ca03534065ce)

if you simulate now you will see something like this 
![image](https://github.com/user-attachments/assets/70a5a14d-43c9-4086-9a9f-2ac8cc0cf977)

save

___

go to your VRPawn and select VRPawn(self) component from the components menu
![image](https://github.com/user-attachments/assets/2fe272eb-5c2d-4398-87e5-55d1ac619433)

add two skeletal mesh components and name them somthing like "XRPhysicsHandRight" and "XRPhysicsHandLeft"
![image](https://github.com/user-attachments/assets/39df5d22-e82a-4c11-8f07-6cd4a279758a)

select the XRPhysicsHandRight component and in the details menu change the mesh to SKM_MannyXR_right do the same for the left one
![image](https://github.com/user-attachments/assets/9886225c-59ae-41c7-9c9d-3ca17331345f)
![image](https://github.com/user-attachments/assets/3dd4b7c2-27b8-4e72-ac43-0ebc0a3a643c)

enable physics for both hands from the details menu
![image](https://github.com/user-attachments/assets/956830f9-f97f-4e3c-91a6-17f011562a3e)

add "set collision enable" to your event graph after "event begin play" for both XRPhysics hands
![image](https://github.com/user-attachments/assets/aacc8f92-31cd-4285-9516-e7744d1a0eb2)

now you have two hand meshs that will fall on the ground and collid with the invinroment, the next step is tying the physics hands to the tracked hands.










