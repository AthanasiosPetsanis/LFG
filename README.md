# LFG
LFG (short for LandFill Generator) is a Blender addon that allows you to easily create realistic and diverse large scale 3D landfill models and estimate the volume and area of the landfill.
It consists of 4 main parts:
  1) The Landscape Generation
  2) The Pile Generation
  3) Volume estimation and
  4) Utilities

So what do these do?
1) The **Landscape Generation** generates a realistic landscape (with a randomly selected drone-captured texture, and random topography).
2) The **Pile Generation** first generates waste in the shape of a cone for any chosen collection, with randomness in scale, location and rotation. Then the next step is letting the Blender simulation run until the waste fall into place forming an accurate pile. You can create as many piles as you want and of any type this way.
3) You can calculate the volume of each pile with **Volume Estimation**.
4) The **Utilities** section allows you to apply the transformation of the piles and join the objects into one entity (useful for importing into simulators).

[images] 

### Advantages
  - Inexhaustible amount of 3D landfill models
  - High realism:
    - Scanned ground textures from drones
    - Scanned landscapes from drones
    - Low-poly closed-surface multi-type materials and waste objects
    - Rigid-body physics (no overlapping of objects + natural pile formation)
  - Ground truth of volume
  - Easy import into Unreal Engine (has been tested for .glb files in Unreal Engine 4 and 5)
  - Expandable collections. Anyone can use their own materials, objects, landscapes and generally 3D models.

### Disadvantages
  - You need to wait for the animation to end until you have realisticly formed piles (this could be cumbersome in slower computer)
  - The more objects you add the slower the animation will be

### Motivation & Usefullness
  - Evaluation of drone path planning algorithms for landfill coverage (via drone simulators like [AirSim]([url](https://github.com/microsoft/AirSim)) or other methods)
  - Acquisition of synthetic images of landfills (via the same simulator as above)
  - Evaluation of photogrammetry algorithms for landfills (we now have the 3D model ground-truth)
  - Evaluation of volumetry algorithms (we now the volume ground-truth of the waste)
  - Augmentation of landfill UAV images with synthetic image data of realistic landfills
There have been few publically available datasets involving UAV images from real landfills. It is a well-known strategy to augment datasets with synthetic data and there exist drone simulators for capturing images in the virtual world. LFG 


# How to install:
Watch the video below or follow the instructions. 

### Prerequisities
LFG has been tested in the latest (as of 01/12/2023) Blender 4.0.1 version.
It requires 2 seperate addons that come preinstalled with Blender to be enabled. These are:
  - The "Add Mesh: A.N.T.Landscape" addon and
  - The "3D-print: toolbox" addon

One last thing needed is to download the files in this [google drive](https://drive.google.com/drive/folders/1ZYW_dM9MNbglxhVGaa26qd7RBJJUuXMa?usp=sharing) and place them inside the folder (and unzip them). This is so that you can have the prescanned landscapes and object collections (they were too big for github).


After you made sure the prequisite addons are enabled and after you downloaded the zip file and extract it:
  1) In Blender, go to Edit --> Preferences --> Addons and click install at the top right 
  2) Then select the lfg.zip file inside of the extracted file.
  3) The addon is located in the Panel section. Click on the Panel "LFG"
  4) Assign the path of the extracted file so that you can have access to all the textures, pre-made landscapes and 3D waste objects.
That's it! you can now use the addon however you like.


https://github.com/AthanasiosPetsanis/LFG/assets/54399132/4706d96b-19b6-42f6-98d1-c320321493a6


# Documentation:
The
This is the easy way for creating a landscape. Of course, you could use the A.N.T.Landscape addon however you want and/or do some easy sculpting on Blender (for example to add bigger hills)
For more details you can refer to the Blender documentation of the addon [here](url)

## Notes:
  - Do not change the name of the pile or object collections after importing or things will break
  - If you want to add your own object collections do so in the collections.blend file 

# Credit
This addon relies on different 3D models and addons. The text file "Credits.txt" has links to the objects used.
