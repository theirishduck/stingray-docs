# Bake lightmaps

To generate lightmaps for your level, do the following:

1.	Prepare the objects and lights in your level for baking:

	- Each bake target needs to be set up with a secondary UV set. You can do this manually in your DCC tool before you import the unit. Or, you can generate the UV mapping automatically either when you import the unit, or at any time in the **Unit Editor**. See ~{ Unwrap UVs for light baking }~.

	- For each light, set the **Baking** option in the **Property Editor** to determine whether or not the light's direct illumination should be included in the lightmap. See ~{ Lightmap baking settings }~.

	>**Important:** An object with a black base color can not receive any baked lighting. Avoid a pure black base color or color map if you want any light baking contribution for your object(s).

	>**Note:** The light baker does not support box lights.

1.	If you have made any changes to your level, units or lights, save the current level before you bake to ensure all of your changes are reflected correctly in the lightmaps.

1.	(Optional) If you want to bake a part of your scene, make a selection before you start your baking session.

1.	Select **Window > Lighting > Light Baking** from the main menu. The editor opens the **Light Baking** window.

	![Light baker settings](../../../images/bake_lightmaps_stingray.png)

1.	In the **Light Baking** window, set the baking options.

	> **Note:** Hover over the other options in this dialog box for descriptions of each attribute.

1.	Click **Bake** to bake your entire scene or **Bake Selection** to bake part of your scene.

## Bake results

The light baker creates a new subfolder in the same folder as the current level's *.level* resource file, named `<level_name>-lightmaps`. In this folder, it saves a set of textures that contain the lighting for the bake targets in your scene. The number of lighmaps required is generated automatically, depending on the number of different bake targets in the scene.

Next to your level's resource file, the baker also creates a *.baked_lighting* resource. This file records the lightmaps generated for your level, and which meshes each map is associated with.

You don't have to do anything with the generated lightmap textures or the *.baked_lighting* file in order for the lightmaps to show up on your objects; the engine handles it automatically. However, you might want to use the ~{ Texture Manager }~ to configure the way the textures are processed and compressed when they are compiled for each platform. Baked lightmaps automatically get tagged with the `Lightmap` texture category, so you can easily find them in the **Texture Editor**.

>**Tip:** To delete all baked lightmaps, click **Clear** (**Window > Lighting > Light Baking**). Lightmaps are removed and no longer appear in the `<level_name>-lightmaps` subfolder.

## Visualizing bake results

The interactive editor viewport offers a visualization mode that shows the diffuse lighting that it applies to the objects in the scene. You can use this mode to see the illumination baked into each object's lightmap projected onto that object as a texture.

For example, the image below on the left shows a fully rendered scene. The right shows only the indirect illumination stored in the lightmaps, which clearly shows the green and red colors bleeding from the side walls into the indirect light that shines on the other parts of the scene. (The color bleed is more subtle in the full render due to direct lighting from the overhead light, and due to specular reflections that are drawn from a reflection probe located in the middle of the box, not shown.)

![Visualizing bake results](../../../images/baked_light_visualization.jpg)

To activate this diffuse visualization mode:

-	From the viewport overlay, click **Full Render > Lighting > Diffuse Ambient**.

If you find artifacts in the way your baked objects are rendered, a good first troubleshooting step is to inspect the UV unwrapping of your objects in the **Level Viewport**. By improving your UV unwrapping, you may be able to eliminate seams and improve resolution. See *View UV unwrapping in the Level Viewport* under ~{ Unwrap UVs for light baking }~.
