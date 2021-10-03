# badges
Creative Process and Generative Workflow for converting 2D Icons into extruded 3D Badges

![screenshot](https://github.com/TheMindVirus/badges/blob/main/screenshot.png)

## Links
https://pokemon.fandom.com/wiki/Gym_Badges \
https://bulbapedia.bulbagarden.net/wiki/Generation \
https://bulbapedia.bulbagarden.net/wiki/Elite_Four \
https://pokemon.fandom.com/wiki/Legendary_Pok%C3%A9mon \
https://pokemongo.fandom.com/wiki/Season_1

## Software
Windows Explorer - File & Directory Management (.zip) \
Microsoft Edge - Research & Development (.html) \
Python3 - Batch Scripting Facility (.py) \
Paint - Compositing (.jpg) \
Paint3D - Alignment (.png -Alpha) \
Paint.NET - Alpha Keying (.png +Alpha) \
Inkscape - Vector Stencil (.svg) \
Blender - Extrusion (.fbx) \
Unity3D - Packaging (.prefab) \
Tabletop Simulator - Presentation (.unity3d)

## Instructions
### 1. Find a 2D Image and convert to .PNG \
 - 1.1 - File -> Open (.jpg) -> Save As (.png) \
 - 1.2 - Resize or Super-resolve the image \
 - 1.3 - Edit to remove background, add fixes etc... \
 - 1.4 - Pixelate to your liking then Save and Close

### 2. Import .PNG into Inkscape for tracing .SVG \
 - 2.1 - File -> Import (.png) \
 - 2.2 - Edit -> Resize Page to Selection \
 - 2.3 - Path -> Trace Bitmap \
 - 2.4 - Brightness Threshold ~ 0.9 \
 - 2.5 - Save and Close

### 3. Import .SVG into Blender for generating .FBX \
 - 3.1 - File -> Import -> Scalable Vector Graphics (.svg) \
 - 3.2 - Solidify Modifier: Thickness = 0.001, Offset = 0 \
 - 3.3 - Switch 3D View to Rendered mode instead of Solid mode \
 - 3.4 - Material Nodes: Base Colour & Emission = Image Texture (Icon.png) \
 - 3.5 - Object Mode -> Object -> Convert -> Mesh (and optionally Shade Flat) \
 - 3.6 - View -> Viewpoint -> Top then Align and Scale to Center of Viewport \
 - 3.7 - Select -> Select All / Select Linked etc. in both 3D View and UV Editor \
 - 3.8 - Edit Mode -> UV -> Project From View (align camera in UV Editing mode) \
 - 3.9 - Optionally flip between UV Editing Mode and Texture Paint Mode to fine tune \
 - 3.10 - Use the Hard Light Brush to touch up unclean edges \
 - 3.11 - Rescale to your liking and Export to .fbx \
 - 3.12 - Open .fbx in 3D Viewer and make a quick Visual Inspection for Quality Assurance \
 - 3.13 - If colours look washed out, use the matching art style to enhance and darken it \
 - 3.14 - Use the Mix Brush to touch up missing faces \
 - 3.15 - Save and Close (also Save the changes to the .png if prompted)

### 4. Import .FBX into Unity3D for generating AssetBundles (.prefab and .unity3d) \
 - 4.1 - Use Tabletop Simulator Modding Template Project for Unity 2019.1.0f2 (64-bit) \
 - 4.2 - Assets -> Import New Asset (.fbx) (.png) (Check "Alpha Is Transparency") \
 - 4.3 - Drag Object from Project View into Scene Hierarchy and Save the Scene \
 - 4.4 - Materials (Metallic = 0.5, Smoothness = 1.0), Reflection Probes (Realtime, 2048) \
 - 4.5 - Drag Object from Scene Hierarchy into Project View and Save the Prefab \
 - 4.6 - When prompted for Original Prefab or Prefab Variant, select Prefab Variant \
 - 4.7 - Inspector -> Asset Labels -> AssetBundle (and name the AssetBundle) \
 - 4.8 - Multi-Select All the Prefab Variants using Ctrl + Click in the Project View \
 - 4.9 - Export Package to .unitypackage "With Materials And Textures" for later editing \
 - 4.10 - Assets -> Build AssetBundles (folder) \
 - 4.11 - Save and Close

### 5. Import .unity3d into Tabletop Simulator \
 - 5.1 - Create -> Single Player -> Close Dialog \
 - 5.2 - Objects -> Backgrounds | Objects -> Tables \
 - 5.3 - Objects -> Components -> Custom -> AssetBundle \
 - 5.4 - Left Click the Table and then Right Click the Table \
 - 5.5 - Main -> Browse Local Files (.unity3d) \
 - 5.6 - Wait and then select Local (or Cloud if available) \
 - 5.7 - Select Import then Right Click for more options (e.g. Scaling) \
 - 5.8 - Save the Mod (optionally upload to Steam Cloud if available) and Close

### Further Notes:
 * Solid Backgrounds instead of Alpha for Textures wraps edges better for the .fbx viewer
 * Concave Icons need to be exactly fitted or dilation needs to be applied on the stencil
 * Most Project Files can be cloned to save effort instead of creating them from scratch
 * Initial Imports can be misaligned and incorrectly scaled - correct this before exporting
 * There are Shortcut Keys and Macros which can help simplify most of the above tasks
 * Edges and Faces have to be reselected in Edit Mode before they appear in UV Editor
 * Converting a Curve/Path Object to Mesh in Blender Applies the Solidify Modifier
 * Rendered View has to be selected separately for each Editing Mode Tab (e.g. UV Editing)
 * Darkening an Image with a tint of the average saturation used enhances that colour
 * To save space in large batch builds, remove some of the redundant files (e.g: .blend1)
 * Exporting to .obj and .mtl from Blender gets rid of some material info (use .fbx)
 * Exporting to .fbx from Unity3D gets rid of all Reflection Probes (use .unitypackage)
 * A lot of the process can be simplified and automated to convert any 2D Image to 3D
