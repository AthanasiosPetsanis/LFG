# LFG
LFG (short for LandFill Generator) is a Blender addon that allows you to easily create realistic and diverse large scale 3D landfill models and estimate the volume and area of the landfill.
It consists of 4 main parts:
  1) Add main path
  2) The Landscape Generation
  3) The Pile Generation with Volume estimation and
  4) Utilities

     ![example](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/a45883f2-3c8c-46be-b775-65180c0fc9db)


So what do these do?
1) The **main path** is where the github folder is located. You need to add this path for the addon to work properly
2) The **Landscape Generation** generates a realistic landscape (with a randomly selected drone-captured texture, and random topography).
3) The **Pile Generation** first generates waste in the shape of a cone for any chosen collection, with randomness in scale, location and rotation. Then the next step is letting the Blender simulation run until the waste fall into place forming an accurate pile. You can create as many piles as you want and of any type this way. You can calculate the volume of each pile with the Volume Estimation.
4) The **Utilities** section allows you to apply the transformation of the piles and join the objects into one entity (useful for importing into simulators).

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
  - Easy creation of 3D landfills models (market landfills are often expensive, hard to find, lack variety and unrealistic)
  - Other uses of 3D landfill models

# How to install:
Watch the video below or follow the instructions. 


https://github.com/AthanasiosPetsanis/LFG/assets/54399132/5c4be64e-d2cf-41f4-959b-4c3b568b8780



### Prerequisities
LFG has been tested in the latest (as of 01/12/2023) Blender 4.0.1 version.
It requires 1 seperate addon that comes preinstalled with Blender to be enabled. This is the **"Add Mesh: A.N.T.Landscape"** addon:
  
![image](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/d1205099-bb31-4665-bdd6-e3c723bab4e7)

One last thing needed is to download the files in this [google drive](https://drive.google.com/drive/folders/1ZYW_dM9MNbglxhVGaa26qd7RBJJUuXMa?usp=sharing) and place them inside the folder (and unzip them). This is so that you can have the prescanned landscapes and object collections (they were too big for github).

### Addon Install
After you made sure the prequisite addons are enabled and after you downloaded the zip file of this github project and extracted it:
  1) In Blender, go to Edit --> Preferences --> Addons and click install at the top right
     ![image](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/ebc5dcaa-f0a2-4a6f-9cba-6c54ba903ad4)  ![image](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/26de24ed-db84-4c83-804b-a57c96f419d5) 
     
  3) Then select the lfg.zip file inside of the extracted file.
     ![image](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/288d93aa-adf7-47cf-a220-384d6246182b)
     
  5) Enable the addon the same way as with the previous addons
     ![image](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/a912aa1a-3646-4700-9f68-c8696c5f475a)

  7)  The addon is located in the 3D-View Panel section. Click on the Panel "LFG"
  8) **IMPORTANT:** Assign the path of the extracted file so that you can have access to all the textures, pre-made landscapes and 3D waste objects. Make sure it points to the folder of the main project and not a file. For example:
     
  
![image](https://github.com/AthanasiosPetsanis/LFG/assets/54399132/4dea43af-4386-4952-bc56-a41e44ffa2a7)

That's it! you can now use the addon however you like.



# Documentation:
Watch the video or read the description below:


https://github.com/AthanasiosPetsanis/LFG/assets/54399132/3c239845-ee22-4884-b261-f744a7b3c1b7



Let's take it section-by-section:
  1) Landscape Generation:
       - Width: The width of the landscape
       - Length: The length of the landscape
       - Height: The average height of the landscape hills (they are randomly generated)
       - Max Height: The maximum height of the hills allowed
       - Min Height: The minimum height of the hills allowed
       - Texture: The texture of the landscape (random by default or you can select a texture from the dropdown menu)
       - Create Landscape button: Generates the landscape with the above properties
       - Load Landscape button: Loads the selected landscape from the dropdown menu on the right of the button (these are real landscapes scanned with UAVs)
     
     This is the easy way for creating a landscape. Of course, you could use the A.N.T.Landscape addon however you want and/or do some easy sculpting on Blender (for example to add bigger hills)
  2) Pile Generation:
       - Radius: The radius of the cone-pile
       - Depth: The depth of the cone-pile
       - Density: The density of the objects inside the cone-pile
       - Objects scale: The scale of the objects inside the cone-pile (default 1 is the original, realistic scale)
       - Collection: The collection of objects that the cone-pile will consist of (Instances are picked randomly from that collection)
         There are currently 5 different collections currently which you can see in the collecion.blend file you downloaded from the google drive. These are:
         Woods, Plastics, Kitchen_Appliances, Metals, Tyres
       - Create Pile button: Creates the pile with the above properties
       - Estimate Volume button: Estimates the volume of each pile
       - Play/Pause buttons: Begin/Stop the animation
  3) Utilities:
       - ApplyTransformations button: Applies the all transformations to all objects for all piles (This is useful so that you do not lose the current placement of the objects)
       - Join Objects button: Joins all objects from all piles along with the "Landscape" object in one single object (This is usefull if you want to import to Unreal Engine for example)
    
### Expanding
If you would like to use your own objects, landscapes or textures you can do so in the following ways:
  - **Objects:** Open the "collection.blend" file you downloaded from the google drive and create a new collection with your objects or add them inside existing collections
  - **Landscapes:** Open the "landscapes.blend" file you downloaded from the google drive and create a new collection with the landscape object you want to include (or just import it).
  - **Textures:** Go to the Ground Textures folder inside the LFG-main folder and add the folder with the textures. Make sure that the folder you add has the following hierarchy:
    - Texture_name/
        - textures/
            - Texture_name_diff.jpg
            - Texture_name_disp.png
            - Texture_name_nor_gl.exr
            - Texture_name_rough.jpg
    
    The _diff is for the diffusion, _disp for the displacement, nor_gl for the normal map and rough for the roughness. You can find more such textures [here](https://polyhaven.com/textures/aerial)


# Notes:
  - The Mountainous terrain is large and complex coupled with object phyciques as they fall it might end up crashing the Blender project
  - Do not change the name of the pile or object collections after importing or things will break
  - If you want to add your own object collections do so in the collections.blend file 

# Credit
This addon relies on different 3D models and addons. The text file "Credits.txt" has links to the objects used.

# Cite as:
*Petsanis, T., & Kapoutsis, A. C. Lfg: An Easy-to-Use Realistic Synthetic Landfill Generator. Available at SSRN 4771989.* [[Link](https://www.sciencedirect.com/science/article/pii/S2352711024003066)]

```bibtex
@article{PETSANIS2024101936,
title = {LFG: An easy-to-use realistic synthetic LandFill Generator},
journal = {SoftwareX},
volume = {28},
pages = {101936},
year = {2024},
issn = {2352-7110},
doi = {https://doi.org/10.1016/j.softx.2024.101936},
url = {https://www.sciencedirect.com/science/article/pii/S2352711024003066},
author = {Thanos Petsanis and Athanasios Ch. Kapoutsis and Elias B. Kosmatopoulos},
keywords = {Landfill, 3D model, Synthetic data generation, Blender, Waste},
abstract = {In this paper we present a Blender add-on named LFG that allows for easy, large and realistic, 3D model LandFill Generation. Large datasets of vast, diverse synthetic landfills are hard to come by, and greatly in need for the purposes of developing and evaluating a multitude of algorithms (e.g. waste classification, 3D-reconstruction, volume estimation algorithms) in the context of research against environment crime. Additionally, they can be used alongside UAV simulators for the development of path-planning algorithms. Although there are some 3D models of landfills available on online 3D-model marketplaces, these are often expensive, low-quality, low-variety and unalterable models. LFG offers customizable, expandable options and realistic features tailored for landfill generation and research.}
```
