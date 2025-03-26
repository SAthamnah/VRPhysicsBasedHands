# VRPhysicsBasedHands

This is an example project to help you implement a physics based VR hands using OpenXR, we will use the built in handtraking in the Varjo XR3.

___
## Preparation

1. Make sure that you have openXR turned on in the varjo base software.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/378a791f-cecf-48e0-9d8b-b063beb60109" />

2. Add Varjo openXR to unreal

https://www.fab.com/listings/aac38f51-491b-4b92-95bf-8ce04311a2ff

3. go to the plugin menu and turn OpenXR, OpenXRHandTracking, and Varjo OpenXR on

<img width="700" alt="image" src="https://github.com/user-attachments/assets/86ecbf8a-395e-4056-81fb-006add27f679" />

___
## Procedural Virtual Hand Mesh Animation Using OpenXR tutorial

Follow this tutorial to get your hands in VR:
[Part1](https://www.youtube.com/watch?v=TPEA1GJr_kU)
[Part2](https://www.youtube.com/watch?v=xEnuephuNmw)

___
## Physics asset

You will notice that the hands you have after finishing the tutorial do not have physics
so, we will be doing that.

1. First step, right click on the XRHand model and create physics.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/f4d04b8b-5781-4a1b-96ed-afdbbe051bbf" />

2. Press create asset.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/47b51305-d1c9-4235-91ed-d2914cd9d223" />)

3. Select the already created capsule and delete it.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/1c7fa181-1422-43f1-a527-4a67354da494" />

4. In the skeleton tree menu press on the setting icon then show all bones.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/d25aaf7e-e38e-4b95-b8f3-6f8485b49f0a" />

5. We have active and unactive bones, select the ones you want to create physics for.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/40fd3ce3-bc1e-465b-92ff-02f200a44802" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/00b76ffd-e96f-400f-8df0-d4f51b269ae3" />

6. On the right side, in the tools menu press on add bodies.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/38ac5b3f-020f-42c3-8514-e1d472eef85e" />

You will have something like this:

<img width="400" alt="image" src="https://github.com/user-attachments/assets/fc1b6869-a425-4bc2-86bd-320e2ef219fd" />

7. press on character, then none for the constraint drawing.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/a4f2bf79-6770-4846-8e9f-53e8abe9e7e3" />

You will see something like this:

<img width="400" alt="image" src="https://github.com/user-attachments/assets/2fbf976c-9a1d-4549-8054-a79acfda3147" />

8. Adjust each size and rotation so it looks fine/normal.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/8d2b4066-7b5a-4bff-a908-4b3cc8cd9418" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/0aa1a915-54cc-471e-b5d5-293bc5fda49f" />

It could look like this:

<img width="400" alt="image" src="https://github.com/user-attachments/assets/cfcc5879-2784-4c18-b705-20f8104dd67b" />

right click on the wrist capcel and press on add shap then box.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/8aad26fd-7950-4107-823c-5465ca5ae1ef" />

right click again on the capcel and delete it
adgust the box size and location to best fit the hand shap

<img width="400" alt="image" src="https://github.com/user-attachments/assets/6a337fd7-0a55-4737-8459-9261108bfe88" />

save

now if you press simulate you will see something like this

<img width="400" alt="image" src="https://github.com/user-attachments/assets/586ab5eb-26a9-47ec-8cfd-dd828d6330d2" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/c1157648-7a2d-4be3-be5c-1321bee39245" />

go back to the skeleton tree menu and hide the bones

<img width="400" alt="image" src="https://github.com/user-attachments/assets/1ab1fb2f-1480-4a57-861f-bae55ed4ba5e" />

right click in the skeleton tree and press select all constrains

<img width="400" alt="image" src="https://github.com/user-attachments/assets/faae4e9a-2d7a-4888-b124-aef803b7bf9e" />

scroll down in the details menu and turn on SLERP for both oriantation and velocity, modify the orientation stringth to 1500

<img width="400" alt="image" src="https://github.com/user-attachments/assets/5aed3ae5-e284-493b-9cd8-ca03534065ce" />

if you simulate now you will see something like this 

<img width="400" alt="image" src="https://github.com/user-attachments/assets/70a5a14d-43c9-4086-9a9f-2ac8cc0cf977" />

save

___
## adding the Physics hands to your pawn

go to your VRPawn and select VRPawn(self) component from the components menu

<img width="400" alt="image" src="https://github.com/user-attachments/assets/2fe272eb-5c2d-4398-87e5-55d1ac619433" />

add two skeletal mesh components and name them somthing like "XRPhysicsHandRight" and "XRPhysicsHandLeft"

<img width="400" alt="image" src="https://github.com/user-attachments/assets/39df5d22-e82a-4c11-8f07-6cd4a279758a" />

select the XRPhysicsHandRight component and in the details menu change the mesh to SKM_MannyXR_right do the same for the left one

<img width="400" alt="image" src="https://github.com/user-attachments/assets/9886225c-59ae-41c7-9c9d-3ca17331345f" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/3dd4b7c2-27b8-4e72-ac43-0ebc0a3a643c" />

enable physics for both hands from the details menu

<img width="400" alt="image" src="https://github.com/user-attachments/assets/956830f9-f97f-4e3c-91a6-17f011562a3e" />

drag from after set visbility and add sequens 

<img width="400" alt="image" src="https://github.com/user-attachments/assets/e6b1b4a1-0651-467d-aacd-5aa8a6ef124e" />

drag from the sequend input and add a delay of 5 secounds to give the game some time and traking to work and then add physics

<img width="400" alt="image" src="https://github.com/user-attachments/assets/3a884d8a-44f7-4c76-b03e-5a0a1dff074e" />

add two get motion controller data functions and set one to left and one to right

<img width="400" alt="image" src="https://github.com/user-attachments/assets/ccf5dfb3-f8e9-48a5-bb8d-e6cca4f8cec0" />

drag from motion controller data and select break xrmotioncontrollerdata then add an and boolian function and connect the valid output to it.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/a66ed8d1-e227-4f82-85e7-4c7b5b8a1b86" />

add a branch function to the output of the and

<img width="400" alt="image" src="https://github.com/user-attachments/assets/02d80df5-5f75-49e6-b77a-905677836862" />

add a new boolian variable and call it PhysicsSet, this will be used to know that the physics has been set and only set the physics ones.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/8a72274e-2d51-47c0-803c-0baaded1bb16" />

get the variable and add a branch on its value

<img width="400" alt="image" src="https://github.com/user-attachments/assets/99b954ba-34e0-4673-88bc-be255d50a8e2" />

___
### Physics Function

create a new function and call it AddPhysics

<img width="400" alt="image" src="https://github.com/user-attachments/assets/00b89eae-3538-4681-80f4-5e6b90df62d8" />

cleck on the function and add three inouts, then name them Hand, Mesh, and TrsckedHand, then set their type to EControllerHand, SkeletalMeshComponent, and PoseableMeshComponent repectfully.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/08c3f2fb-b4e2-4ac5-b9b3-cbc78b598dbb" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/b9575e53-3cf4-418e-baa3-e1ef0ad6ed7e" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/2e3c7c7f-8290-42bc-8ac3-d3fa804474d8" />

drag from the three inputs and promote them to local variables, name them as shown bellow

<img width="400" alt="image" src="https://github.com/user-attachments/assets/7c0fb56f-e1d2-4cb6-9a5b-6166eea2d369" />

add the following blueprints to get the hand traking state and verify that the tracking is working correctly

<img width="400" alt="image" src="https://github.com/user-attachments/assets/aca39fec-c45e-4b09-814b-77e151a91897" />

diable physics temporarly and enable collision on the physics hand

<img width="400" alt="image" src="https://github.com/user-attachments/assets/8a848661-a78e-4931-ba9b-d4fecb21e19d" />

move the physics hand to the tracked hand location 

<img width="400" alt="image" src="https://github.com/user-attachments/assets/43250186-a56d-4751-a242-6a21bb8df6de" />

loop on every bone in the hand and add a physics constraint
we start by getting current bone name and skip "None"

<img width="400" alt="image" src="https://github.com/user-attachments/assets/251e4f06-4830-4896-9aac-46102febbb8b" />

to attach physics constaints to a poseable mesh you need something to attach the constraint to so we will add collision spheres as cheldren to the bones, the skeletal mesh already has collision capsoles, so nothing has to be done to them.
drag from the false output of the brach and get the bone transform of the hand mesh (poseable mesh), make sure you are in world space
create a variable of type and name it AnimationBoneCorrectionRotationOffset, give it the following values

<img width="400" alt="image" src="https://github.com/user-attachments/assets/6d541b8f-f558-4fbc-944e-58160c83b186" />

split struct pin on the output of get bone transform by name and two make transform functions
then add compose transform and make sure the order is the same as in the picture
add collision spheres at the bones loactions of the tracked hand to attach physics constains to
and then attach them to the hand bones

<img width="400" alt="image" src="https://github.com/user-attachments/assets/d879ab58-fa83-41bd-9138-bd7be3c51a97" />

Add, attach, and tie the physics constraints between the two hands
make sure you enable manual attachment 

<img width="400" alt="image" src="https://github.com/user-attachments/assets/8fc7f320-1a28-4ce3-9814-358e6e5062cd" />

set the following options for the physics constraint so it behaves more naturaly

<img width="400" alt="image" src="https://github.com/user-attachments/assets/3e5dfcbf-5100-4653-98a6-e0ae44bd01fb" />

go back to the start of the loop and add after completed "set simulate physics" and enable it

<img width="400" alt="image" src="https://github.com/user-attachments/assets/c2716780-6f0f-437a-9f0d-5ee09d77af78" />

the function to tie both tracked hand and physics hand is now complete

___

Go back to the event graph and add the function add physics to times after the branch, drag from false

<img width="400" alt="image" src="https://github.com/user-attachments/assets/c57ae462-9364-4caf-a31a-09eedd8d618c" />

pass the right parameters to the function as follows

<img width="400" alt="image" src="https://github.com/user-attachments/assets/edea6fa3-9959-4969-81aa-74a2b3ed42e6" />

set the variable PhysicsSet high to indecate that the physics hands have been tied.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/2d699776-a72d-4aa1-9cf9-7a81f767f4c9" />

add an event lesner for the key H, that can call this part of the code on demand.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/b4eeb107-aa96-44a9-abf1-e00d1d47075a" />

connect it to the start of this part

<img width="400" alt="image" src="https://github.com/user-attachments/assets/d6052b20-8cd3-4f1e-b142-3cb85e76c8c6" />

go back to the parts implemnted in the previos mentioned tutorial and disconnect the update hand visablity, so we only see the physics hands

<img width="400" alt="image" src="https://github.com/user-attachments/assets/52e1d0f1-d815-4f9d-8b02-fd5a33e91476" />

replace the branching condition for both update hand animation to PhysicsSet, make the track hands meshes only move after we tie them to the physics hands.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/acf9e86c-d338-487f-9be0-2f829e80723f" />

___
Go back to the main page
[Home](./README.md)
