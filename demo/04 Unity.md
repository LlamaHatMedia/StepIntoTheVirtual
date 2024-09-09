# Chapter 4: Unity

## VRChat Creator Companion
The VRChat Creator Companion (VCC) provides all the SDKs required along with being a package manager for VRChat specific packages. We won't use this too much other than to create our project.

## Setting things up
You will want to create a new scene to make the world in. To do this we right click our assets folder and select "New -> Scene". This will allow us to save what we make.

Next you will want to setup VRChat's dependencies. In your assets folder there is a search bar. Search for "VRCWorld", you will need to uncheck the filter "in Assets" for this to appear as it is in the packages folder instead.

Then select from your top menu bar "VRChat SDK -> Control Panel" and a window should appear that allows you to sign into your VRChat account. With the most recent versions of the VRChat SDK it requires you to navigate to the Build and Publish page and click correct all of the warnings.

## Assets
Our blender FBX will need to be exported into our Unity assets folder before we use it. We can drag the FBX into our scene.

Our texture files can be brought in directly from our file explorer into our assets folder.

## Materials
The FBX will have automatically created materials, don't use these, they will try to bring across texture references but often can be incorrect.

Create new materials with "New -> Material" from the context menu, 

## Colliders
The world that you have created is just rendering the visual, if you try to enter play mode you will end up falling through the world. Thus adding a mesh collider to each object is required for a player to be able to walk around.

## Intractables
We can add an intractable objects in many forms. Buttons that are interacted with to toggle objects in the worlds such as mirrors.

### Pickup-able
The vrc_pickup script will allow users to pickup the object in question.

## Synchronization
The nature of how networking in games works is that every object is run on the clients local instance, and any changes to that are synced. This means that who ever changes the object/slider/toggle needs to tell the rest of the people in the lobby that that has changed. Common practice is that the person who interacts with the object is set to be the owner of said object.

Serialization is the process of packaging up that change and sending it to the VRChat servers for distribution to other users. This is then deserialization on everyone else's machines to make said changes. A simple script that allows interaction between members of a lobby and an object is the script vrc_objectsync. This handles all of the synchronization of the objects position and rotation.