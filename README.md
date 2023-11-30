# LFG
LFG (short for LandFill Generator) is a Blender addon that allows you to easily create realistic and diverse large scale 3D landfill models and estimate the volume and area of the landfill.
It consists of 4 main parts:
  1) The Landscape Generation
  2) The Pile Generation and
  3) Preparation for Export
  4) Volume estimation

So what do these do?
1) The **Landscape Generation** generates a realistic landscape (with a randomly selected drone-captured texture, and random topography).
2) The **Pile Generation** first generates waste in the shape of a cone for any chosen collection, with randomness in scale, location and rotation. Then the next step is letting the Blender simulation run until the waste fall into place forming an accurate pile. You can create as many piles as you want and of any type this way.
3) The **Preparation for Export** section allows you to apply the transformation of the piles and join the objects into one entity.
4) Lastly, you can calculate the volume of each pile with **Volume Estimation**.

[images] 

### Advantages
  - Inexhaustible amount of 3D landfill models
  - High realism:
    - Scanned ground textures from drones
    - Scanned landscapes from drones
    - Low-poly closed-surface multi-various materials and waste objects
    - Rigid-body physics (no overlapping of objects, and natural pile formation)
  - Volume ground truth
  - Easy import into Unreal Engine (has been tested for .glb export in Unreal Engine 4 and 5)
  - Expandable collections. Anyone can use their own materials, objects, landscapes and generally 3D models.

### Disadvantages
  - You need to wait for the simulation to end until you have realisticly formed piles (this could be cubersome is slower computer)

# Motivation

# Prerequisities
LFG has been tested in the latest (as of 01/12/2023) Blender 4.0.1 version.
It requires 2 seperate addons that come preinstalled with Blender to be enabled. These are:
  - The "Add Mesh: A.N.T.Landscape" addon and
  - The "3D-print: toolbox" addon
One last thing needed is to download the files in this [google drive](https://drive.google.com/drive/folders/1ZYW_dM9MNbglxhVGaa26qd7RBJJUuXMa?usp=sharing) and place them inside the folder. This is so that you can have the prescanned landscapes and object collections (they were too big for github).

# How to install:
After you made sure the prequisite addons are enabled and after you downloaded the zip file and extract it:
  1) In Blender, go to Edit --> Preferences --> Addons and click install at the top right 
[image]
  2) Then select the lfg.zip file inside of the extracted file.
  3) The addon is located in the Panel section. Click on the Panel "LFG"
  4) Assign the path of the extracted file so that you can have access to all the textures, pre-made landscapes and 3D waste objects.
That's it! you can now use the addon however you like.

# Documentation:
The
This is the easy way for creating a landscape. Of course, you could use the A.N.T.Landscape addon however you want and/or do some easy sculpting on Blender (for example to add bigger hills)
For more details you can refer to the Blender documentation of the addon [here](url)

## Notes:
  - Do not change the name of the pile or object collections after importing or things will break
  - If you want to add your own object collections do so in the collections.blend file 

# Credit
This addon relies on different 3D models and addons. Below is a list of the creators and their corresponding work:
  - dfs
  - dsfs
  - 
