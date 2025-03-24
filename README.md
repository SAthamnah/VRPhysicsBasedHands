# VRPhysicsBasedHands

This is an example project to help you implement a physics based VR hands using OpenXR, we will use the built in handtraking in the vrajo XR3.

___
## Preparation

make sure that you have openXR turned on in the varjo base software.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/378a791f-cecf-48e0-9d8b-b063beb60109" />

add varjo openXR to unreal

https://www.fab.com/listings/aac38f51-491b-4b92-95bf-8ce04311a2ff

go to the plugin menu and turn OpenXR, OpenXRHandTracking, and Varjo OpenXR on

<img width="700" alt="image" src="https://github.com/user-attachments/assets/86ecbf8a-395e-4056-81fb-006add27f679" />

___
## Procedural Virtual Hand Mesh Animation Using OpenXR tutorial

follow this tutorial to get your hands in VR:
[Part1](https://www.youtube.com/watch?v=TPEA1GJr_kU)
[Part2](https://www.youtube.com/watch?v=xEnuephuNmw)

___
## Physics asset

you will notice that the hands you have after finishing the tutorial do not have physics
so, we will be doing that 

first step, right click on the XRHand model and create physics

<img width="600" alt="image" src="https://github.com/user-attachments/assets/f4d04b8b-5781-4a1b-96ed-afdbbe051bbf" />

press create asset

<img width="400" alt="image" src="https://github.com/user-attachments/assets/47b51305-d1c9-4235-91ed-d2914cd9d223" />)

select the already created capsel and delete it

<img width="400" alt="image" src="https://github.com/user-attachments/assets/1c7fa181-1422-43f1-a527-4a67354da494" />

in the skeleton tree menu press on the steeting icon then show all bones

<img width="400" alt="image" src="https://github.com/user-attachments/assets/d25aaf7e-e38e-4b95-b8f3-6f8485b49f0a" />

we have active and unactive bones, select the ones you want to create physics for.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/40fd3ce3-bc1e-465b-92ff-02f200a44802" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/00b76ffd-e96f-400f-8df0-d4f51b269ae3" />

on the right side, in the tools menu press on add bodies

<img width="400" alt="image" src="https://github.com/user-attachments/assets/38ac5b3f-020f-42c3-8514-e1d472eef85e" />

you will have something like this

<img width="400" alt="image" src="https://github.com/user-attachments/assets/fc1b6869-a425-4bc2-86bd-320e2ef219fd" />

press on character, then none for the constraint drawing

<img width="400" alt="image" src="https://github.com/user-attachments/assets/a4f2bf79-6770-4846-8e9f-53e8abe9e7e3" />
_
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
## adding the Physics hands to your pawn

go to your VRPawn and select VRPawn(self) component from the components menu

![image](https://github.com/user-attachments/assets/2fe272eb-5c2d-4398-87e5-55d1ac619433)

add two skeletal mesh components and name them somthing like "XRPhysicsHandRight" and "XRPhysicsHandLeft"

![image](https://github.com/user-attachments/assets/39df5d22-e82a-4c11-8f07-6cd4a279758a)

select the XRPhysicsHandRight component and in the details menu change the mesh to SKM_MannyXR_right do the same for the left one

![image](https://github.com/user-attachments/assets/9886225c-59ae-41c7-9c9d-3ca17331345f)
![image](https://github.com/user-attachments/assets/3dd4b7c2-27b8-4e72-ac43-0ebc0a3a643c)

enable physics for both hands from the details menu

![image](https://github.com/user-attachments/assets/956830f9-f97f-4e3c-91a6-17f011562a3e)

drag from after set visbility and add sequens 

![image](https://github.com/user-attachments/assets/e6b1b4a1-0651-467d-aacd-5aa8a6ef124e)

drag from the sequend input and add a delay of 5 secounds to give the game some time and traking to work and then add physics

![image](https://github.com/user-attachments/assets/3a884d8a-44f7-4c76-b03e-5a0a1dff074e)

add two get motion controller data functions and set one to left and one to right

![image](https://github.com/user-attachments/assets/ccf5dfb3-f8e9-48a5-bb8d-e6cca4f8cec0)

drag from motion controller data and select break xrmotioncontrollerdata then add an and boolian function and connect the valid output to it.

![image](https://github.com/user-attachments/assets/a66ed8d1-e227-4f82-85e7-4c7b5b8a1b86)

add a branch function to the output of the and

![image](https://github.com/user-attachments/assets/02d80df5-5f75-49e6-b77a-905677836862)

add a new boolian variable and call it PhysicsSet, this will be used to know that the physics has been set and only set the physics ones.

![image](https://github.com/user-attachments/assets/8a72274e-2d51-47c0-803c-0baaded1bb16)

get the variable and add a branch on its value

![image](https://github.com/user-attachments/assets/99b954ba-34e0-4673-88bc-be255d50a8e2)

___
### Physics Function

create a new function and call it AddPhysics

![image](https://github.com/user-attachments/assets/00b89eae-3538-4681-80f4-5e6b90df62d8)

cleck on the function and add three inouts, then name them Hand, Mesh, and TrsckedHand, then set their type to EControllerHand, SkeletalMeshComponent, and PoseableMeshComponent repectfully.

![image](https://github.com/user-attachments/assets/08c3f2fb-b4e2-4ac5-b9b3-cbc78b598dbb)
![image](https://github.com/user-attachments/assets/b9575e53-3cf4-418e-baa3-e1ef0ad6ed7e)
![image](https://github.com/user-attachments/assets/2e3c7c7f-8290-42bc-8ac3-d3fa804474d8)

drag from the three inputs and promote them to local variables, name them as shown bellow

![image](https://github.com/user-attachments/assets/7c0fb56f-e1d2-4cb6-9a5b-6166eea2d369)

add the following blueprints to get the hand traking state and verify that the tracking is working correctly

![image](https://github.com/user-attachments/assets/aca39fec-c45e-4b09-814b-77e151a91897)

diable physics temporarly and enable collision on the physics hand

![image](https://github.com/user-attachments/assets/8a848661-a78e-4931-ba9b-d4fecb21e19d)

move the physics hand to the tracked hand location 

![image](https://github.com/user-attachments/assets/43250186-a56d-4751-a242-6a21bb8df6de)

loop on every bone in the hand and add a physics constraint
we start by getting current bone name and skip "None"

![image](https://github.com/user-attachments/assets/251e4f06-4830-4896-9aac-46102febbb8b)

to attach physics constaints to a poseable mesh you need something to attach the constraint to so we will add collision spheres as cheldren to the bones, the skeletal mesh already has collision capsoles, so nothing has to be done to them.
drag from the false output of the brach and get the bone transform of the hand mesh (poseable mesh), make sure you are in world space
create a variable of type and name it AnimationBoneCorrectionRotationOffset, give it the following values

![image](https://github.com/user-attachments/assets/6d541b8f-f558-4fbc-944e-58160c83b186)

split struct pin on the output of get bone transform by name and two make transform functions
then add compose transform and make sure the order is the same as in the picture
add collision spheres at the bones loactions of the tracked hand to attach physics constains to
and then attach them to the hand bones

![image](https://github.com/user-attachments/assets/d879ab58-fa83-41bd-9138-bd7be3c51a97)

Add, attach, and tie the physics constraints between the two hands
make sure you enable manual attachment 

![image](https://github.com/user-attachments/assets/8fc7f320-1a28-4ce3-9814-358e6e5062cd)

set the following options for the physics constraint so it behaves more naturaly

![image](https://github.com/user-attachments/assets/3e5dfcbf-5100-4653-98a6-e0ae44bd01fb)

go back to the start of the loop and add after completed "set simulate physics" and enable it

![image](https://github.com/user-attachments/assets/c2716780-6f0f-437a-9f0d-5ee09d77af78)

the function to tie both tracked hand and physics hand is now complete

___

Go back to the event graph and add the function add physics to times after the branch, drag from false

![image](https://github.com/user-attachments/assets/c57ae462-9364-4caf-a31a-09eedd8d618c)

pass the right parameters to the function as follows

![image](https://github.com/user-attachments/assets/edea6fa3-9959-4969-81aa-74a2b3ed42e6)

set the variable PhysicsSet high to indecate that the physics hands have been tied.

![image](https://github.com/user-attachments/assets/2d699776-a72d-4aa1-9cf9-7a81f767f4c9)

add an event lesner for the key H, that can call this part of the code on demand.

![image](https://github.com/user-attachments/assets/b4eeb107-aa96-44a9-abf1-e00d1d47075a)

connect it to the start of this part

![image](https://github.com/user-attachments/assets/d6052b20-8cd3-4f1e-b142-3cb85e76c8c6)

go back to the parts implemnted in the previos mentioned tutorial and disconnect the update hand visablity, so we only see the physics hands

![image](https://github.com/user-attachments/assets/52e1d0f1-d815-4f9d-8b02-fd5a33e91476)

replace the branching condition for both update hand animation to PhysicsSet, make the track hands meshes only move after we tie them to the physics hands.

![image](https://github.com/user-attachments/assets/acf9e86c-d338-487f-9be0-2f829e80723f)

# VR Tablet with Blui (Touch Based Interaction)
This part is an example to help you integrate [Blui (WebBrowser Widget)](https://github.com/getnamo/BLUI-Unreal) with your VR project. We will use Blui in this example to create a VR tablet.

___
## Download Blui
1. Please first download the appropriate version of Blui for your Unreal Engine from [Here](https://github.com/getnamo/BLUI-Unreal/releases)

___
2. Copy The Plugins folder to your Unreal VR project

<img width="500" alt="image" src="https://github.com/user-attachments/assets/7a6109ee-83bf-4d79-ac9d-176ecca5b25d" /> 
--> <img width="400" alt="image" src="https://github.com/user-attachments/assets/d422c27e-825f-4431-9367-749b5ae2fbf3" />

___
3. Open Project plugins and make sure the plugin is Enabled:

<img width="600" alt="image" src="https://github.com/user-attachments/assets/70c55c99-6cf8-47dd-b33d-f6e9c45704ff" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/431098bb-372b-4e15-b436-00a04e3971f6" />

___
## Test Blui

1. Press on the button in the corner of the content browser and then select BLUI Content

<img width="400" alt="image" src="https://github.com/user-attachments/assets/78d6aadf-83cd-4bf4-a03f-402720dfe6f7" />

___
2. Drag and drop "BluiWorldWidgetActorExample" to your scenes

<img width="600" alt="image" src="https://github.com/user-attachments/assets/c4d3754e-780a-454d-9393-b3ee78303478" />

___
3. Play from current camera position to test if the plugin runs correctly youtube should load on the widget

<img width="300" alt="image" src="https://github.com/user-attachments/assets/e6e961fe-e4a3-4b0d-898a-23b273fa28fa" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/814b6884-90b6-4c8c-9537-e85933055ecf" />

___
### Change URL to load
From the details tab you can change the URL to be loaded on the widget

<img width="200" alt="image" src="https://github.com/user-attachments/assets/f2d7dbc2-b4cf-4b7a-b5ed-710ad51f7969" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/43891bd5-6d52-41ce-8884-3465d5ad92b7" />

___
### Change Dimensions
If you select the widget under the defualtsceneroot you can change the resolution and ratio of the widget, Ex. 2000 by 1000:

<img width="200" alt="image" src="https://github.com/user-attachments/assets/44317aa6-abfd-44ec-b9a5-c0ea377d58df" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/61b8b920-9fd9-4f83-a737-b22b8ebd3553" />

___
## Touch Interaction in 3D space (VR Tablet)
### Create VRTablet (New Blui Widget in 3D space)
1. Click on Add/Import in your Content Browser and create a new folder

<img width="300" alt="image" src="https://github.com/user-attachments/assets/cf8a99ca-7d8f-4d05-9588-5a434531c583" />

___
2. Open the new folder and Click on Add/Import again, press on Blueprint Class. Then select Actor and name it "VRTablet", open it by double clicking on it

<img width="300" alt="image" src="https://github.com/user-attachments/assets/87ad36dc-2090-4757-8bfc-c951ec02fc1d" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/d90124c8-a43d-400b-b959-b425f44e7fc3" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/cd28b1e5-164e-430a-bcc8-d1c0e5e8e51d" />

___
3. Press on Add Component and search for widget then click on it, Name it "screen". 

<img width="400" alt="image" src="https://github.com/user-attachments/assets/bf5f90c9-159c-4863-9bf8-641c4ebe039d" />

___
4. Under the details tab, Change the widget class to BluiWidget. You can view the widget from the Viewport tab.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/a2718be5-d5f4-4b98-b730-4d41e32eb53c" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/4ca5cb5a-be87-4155-ad26-fef86b150361" />

___
5. Go back to the content browser and open "BluiWorldWidgetActorExample" right click on "InitBluiWidget" and copy the function, then go to your "VRTablet" Actor and right click on the functions section and paste the function.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/9c70f904-59dd-461f-9e42-bed9b3138b25" />
<img width="236" alt="image" src="https://github.com/user-attachments/assets/611951af-f4cd-4553-8152-f3f1c3a4f616" />
<img width="352" alt="image" src="https://github.com/user-attachments/assets/000f2b27-ef5f-49dd-a768-ee2b217dd327" />

___
6. Open the function and drag and drop the screen component to replace the widget component. Right click on each missing variable then press create. Compile.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/b85172a3-e63c-4c6c-8baf-845061c8d7b9" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/1342158c-acb7-4aa2-925f-6fadb7526930" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/c98b7a1a-c8c0-4287-ac36-0bd829790862" />

___
7. Open the Event Graph, Right click in the empty space, search for "initBluiWidget" and add it to your graph. Then connect it with "Event BeginPlay" then hit compile.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/dac27ffd-25fd-4405-990d-f7639c9ea5c9" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/b5237355-69c9-4502-adc4-1733deb3f8d3" />

___
8. Change the default value of the URL variable to any website you want by clicking on the variable and writing the URL in the details tab.
<img width="700" alt="image" src="https://github.com/user-attachments/assets/f5a8e371-3159-4fdc-b9fc-0f77ce2ecbc0" />

___
If you drag and drop the current "VRTablet" to the scene it will look like this

<img width="700" alt="image" src="https://github.com/user-attachments/assets/fd180dfd-9112-4194-a46c-b5feb6cbb2c2" />

___
9. To fix the rendering change the screen Draw size to something similar to a real tablet (1920,1080), then scale it down in your scene.

<img width="700" alt="image" src="https://github.com/user-attachments/assets/697bcd1f-27ac-4ccd-97e2-b8e5a4d23185" />
<img width="700" alt="image" src="https://github.com/user-attachments/assets/a9cf6a40-f7c0-4d76-a8d7-b863ecd87b82" />

___
10. Go back to your "VRTablet" Actor and add a new cube component, name it "Body". Unlock the scale and adjust it to the appropriate size. Move the "Body" back to make the screen appear on the surface.

<img width="200" alt="image" src="https://github.com/user-attachments/assets/65e5b010-5b55-4676-9d1e-45ef5dc6e0b2" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/41d93819-c9e6-408c-9927-87268612316a" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/b813e115-04f7-4c76-991b-422458819d65" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/9eb1eac6-16a5-4d70-beda-2c093fd62852" />

___
### Touch Interaction
Blui takes mouse events as input, so we will translate the users touch interactions to mouse clicks and scrolls based on the location of touch.

1. Open the "VRTablet" Actor and select the screen, scroll down in the details tab and Add the events "On Component Begin Overlap" and "On Component End Overlap" to your graph. Create a new Variable and change its type to Primitive Component. Name it "Overlapping Components", Change it from a single value to an array by clicking next to its data type and then choosing array.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/b50f4b0d-3a24-4ec2-ad84-e69cd088da7c" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/69f8fd42-2112-4e07-bf7c-7e8a0cd05807" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/e7ad654f-b7fa-4ee7-89c1-2901414af65a" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/1b753478-37f9-478b-a5ca-bca81acc73b2" />

___
2. Drag the variable and drop it in the graph, press on get. Drag from the variable reference and search for "Add Unique". Connect the components like in the screenshot. This will add any component that overlaps the screen to an array, we will use this to find out how many fingers are touching the screen. do the same with the "On Component End Overlap" but "remove item" instead of "add unique".

<img width="300" alt="image" src="https://github.com/user-attachments/assets/50af0cc9-b9c7-4818-84ab-9d3310eafd3a" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/408fcc87-be76-4911-9a54-152494676e0e" />
<img width="581" alt="image" src="https://github.com/user-attachments/assets/43cd4c77-568b-4777-96af-504e84662258" />
<img width="461" alt="image" src="https://github.com/user-attachments/assets/2e82f7cb-334c-4536-b2a9-2ae694ad0738" />

___
3. Use a branch component to distinguish if one finger is touching the screen, two fingers are touching the screen, or more. If one is touching, we do a Tap gesture or a Pan gesture, if two are touching we do a pinch/stretch gesture, if more we do nothing.

<img width="581" alt="image" src="https://github.com/user-attachments/assets/07d2e51f-31fa-40f2-b205-005d3651f052" />

___
#### Tap and Pan Gestures
To do a pan or a tap, we need to use three mouse events "Trigger Left Mouse Down" then "Trigger Mouse Move" and when the overlap ends, we use "Trigger Left Mouse up" to finish the gesture.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/10397313-ff42-4eb5-8446-6c5047937920" />
<img width="509" alt="image" src="https://github.com/user-attachments/assets/630583c2-c893-49b8-8fa6-9dfce8a9d18e" />

___
4. To use these functions, we need to copy the function "GetBlui" from "InteractableBluiWidgetActor" from "Blui Content" in the content browser, paste the function in our VRTablet Actor functions section. Drag and drop the screen component to replace the widget after copying. Drag and drop the function to the graph and connect it to the target of the ones we have already.

<img width="300" alt="image" src="https://github.com/user-attachments/assets/aaff0a3c-4db2-4341-a098-252b2f869815" />
<img width="300" alt="image" src="https://github.com/user-attachments/assets/7ec4862a-9d6b-48d7-baab-57aa91a86cad" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/00b5bf3e-19b9-419b-ae81-2fed5e6a32e5" />
<img width="700" alt="image" src="https://github.com/user-attachments/assets/109b2f20-ffbe-488a-aca9-b54e941eb08d" />

___
5. To Know the position we are touching at, we need to translate the 3d world location of the finger to a 2d position on the tablet screen. go back to the main scene.
Change the perspective to front or left based on your tablets’ orientation, measure the width and height of the tablet by pressing close to one corner of the tablet the mouse middle button and dragging to the other corner of the tablet. 

<img width="600" alt="image" src="https://github.com/user-attachments/assets/ecd2f648-4d44-4cb1-a5d4-a7f8e7f1ee69" />
<img width="500" alt="image" src="https://github.com/user-attachments/assets/92c3dfec-2923-4548-9791-9a10886ed777" />

___
6. Use the measured numbers (Ex. 600,344) and the screen resolution (Ex. 1920,1080) to translate the distance the finger will travel in 3d space to a relative 2d position on the tablets screen.
   - First, we get the World location of the center of the Other comp (the finger) and the World location of the center of the screen, then we find the difference between them.
   - Second, we get the rotation of the tablet
   - Then we translate the distance the finger travels on the X, Y, and Z axis to a 2D array. Write the Width in "the Map Range Clamped" function. Note that you have to divide the measured length on 2 because the relative reference is the center of the tablet. do the same for the Hight of tablet. The Lerp function is used with two cosine functions to adjust for any tilt in the tablet.
   - Finaly, we send that 2D array to the Mouse triggers as input.

<img width="1000" alt="image" src="https://github.com/user-attachments/assets/2fe2bebf-6649-4d48-a1cc-9567cc60cd53" />

___
7. Drag and drop the other comp and then press on promote to variable, move the set other object and connect it where we only have one finger detected.

<img width="680" alt="image" src="https://github.com/user-attachments/assets/384b51e8-01db-4ac2-bb71-6efc416e14a8" />
<img width="728" alt="image" src="https://github.com/user-attachments/assets/ac267629-5545-4ed1-bfa3-56b9a00b1634" />


___
8. Create a custom event and name it panning, add set timer by event and connect it to the panning event. Make sure the looping flag is set to true and set the time to 0.01. Add a branch that checks if the current other object (finger) is the other object (finger) that did the mouse down. drag and drop the return value of the set timer by event function and promote it to a variable. Add "Clear and invalidate timer by handle" after the "On Component End Overlap" event.

<img width="416" alt="image" src="https://github.com/user-attachments/assets/275aa919-d376-4930-be13-850d0fa9f921" />
<img width="431" alt="image" src="https://github.com/user-attachments/assets/941323ce-0775-4956-95d3-ada4c5151fb5" />
<img width="456" alt="image" src="https://github.com/user-attachments/assets/6b4d10cd-1133-463d-80d6-3aee5d2c05a2" />
<img width="420" alt="image" src="https://github.com/user-attachments/assets/73364f65-3fbf-4ebc-b409-47fe8364a649" />
<img width="203" alt="image" src="https://github.com/user-attachments/assets/069aefb8-dad3-4246-87c9-4106070c2365" />
<img width="668" alt="image" src="https://github.com/user-attachments/assets/598ae43e-48fd-411b-94ad-09e1d93de20c" />

___
9. Create a variable and call it noRappiedFire, compile. change its default value to true. branch on it before you trigger mouse down. Set its value to false, add a delay of 0.5s and set it back to true. This will allow one finger to trigger the mouse at a time.

<img width="242" alt="image" src="https://github.com/user-attachments/assets/d5f8ce62-5423-461b-a8cb-8130977c7183" />
<img width="311" alt="image" src="https://github.com/user-attachments/assets/1f28f147-a076-40a2-875c-11a3a111e6fb" />
<img width="705" alt="image" src="https://github.com/user-attachments/assets/353b7dbd-8c6e-4ac9-988f-bf3cb08397e6" />
<img width="1052" alt="image" src="https://github.com/user-attachments/assets/a13973d7-42d2-4993-83a2-02bb3ae4806e" />

___
10. Connect "Trigger Left Mouse up" after the end. Copy the position translation code and connect it to the "Trigger Left Mouse up" function. connect the other comp from "On Component End Overlap" to the copied the position translation code.

<img width="973" alt="image" src="https://github.com/user-attachments/assets/1d69260f-7025-4f7b-b7ac-3e8de5d12fc9" />

___
11. Code so far, we should be able to Tap or Pan/Swipe with the implementation so far.

<img width="1028" alt="image" src="https://github.com/user-attachments/assets/4a4b00a2-2209-424e-bff8-d2342cdf63b0" />

___
#### Zoom Gesture
This gesture will happen when we have two fingers on the screen. Two fingers will satisfy the if statement that checks the length of the overlapping components array. 
1. First, we need to make sure that the code we wrote will execute once, so we start by adding a branch that only allows one of the two touching fingers to run the code.

<img width="650" alt="image" src="https://github.com/user-attachments/assets/676d59fc-d797-44f0-8fa1-605e92a1dd5d" />

___
2. Create a vector array to save the fingers locations, compile. add two elements to the array by clicking on the "+" button below default values. Use a for each loop to record the locations of the two touching fingers

<img width="1286" alt="image" src="https://github.com/user-attachments/assets/4163bb8e-5560-4ef8-aed1-1b63de69c962" />
<img width="182" alt="image" src="https://github.com/user-attachments/assets/8108976f-45ea-479f-ad15-298383431d6c" />
<img width="205" alt="image" src="https://github.com/user-attachments/assets/aba4cad0-4e82-4d5f-a25d-541b3dc1451f" />
<img width="746" alt="image" src="https://github.com/user-attachments/assets/be1bc07d-ab90-40b7-9b97-ec651aa0528b" />

___
3. Create a var and call it Dest, Set it after the completion  of the for loop with the distance between the fingers.

<img width="789" alt="image" src="https://github.com/user-attachments/assets/e30e1126-a703-440d-85ef-873f2ee6652a" />

___
Create a custom event and name is zooming, add a set timer by event and connect it, set looping to true. promote the return value to a variable. and clear and invalidate timer by handle.

<img width="509" alt="image" src="https://github.com/user-attachments/assets/ac69d595-89d3-4ea7-8042-19bc44c0dbc8" />
<img width="884" alt="image" src="https://github.com/user-attachments/assets/e18f7802-7ba2-4e20-a9ee-e4b54d1439d8" />

___
Get the distance between the fingers again and negate it from the reading from the previous one

<img width="872" alt="image" src="https://github.com/user-attachments/assets/4776fa5c-6532-4572-b474-bd21b37d201f" />

___
Add a "Trigger mouse wheel" function, and connect it as follows. Set the value of dest at the end. Copy the code we used to generate that mouse interaction location, modify the part we get the finger location. This will take the location in the middle between the finger as the interaction location.

<img width="1174" alt="image" src="https://github.com/user-attachments/assets/88a1c7e6-389d-4d58-9c6a-0f8d5c5d02a8" />
<img width="1174" alt="image" src="https://github.com/user-attachments/assets/0da74d69-9418-40e1-9b24-0852eb194ae6" />

___
This is the final code for zooming

<img width="1082" alt="image" src="https://github.com/user-attachments/assets/1ae4c496-a9a4-40b6-a600-5ed7ccbe73b8" />

___
### Final blueprint

<img width="800" alt="image" src="https://github.com/user-attachments/assets/c4630b78-9db6-48c9-8376-75245e32f675" />


MIT License














