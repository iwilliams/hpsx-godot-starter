# hpsx-godot-starter

![Preview](/readme_images/preview.gif)

## Intro
The purpose of this repository is to act as a staring point for Godot games looking to imitate PSX style graphics. I've set up some defaults and included a material to use on your models with some
explanation below. Please feel free to open a PR if you have some other techniques or examples that might fit in with this starter pack! 

## Window Settings

The original PS1 supported resolutions from 256×448 to 640×480 pixels. I've set the resolution to 320x240 for a nice nostalgic 4:3 look, 
but in reality your player isn't going to use this tiny resolution so we scale it up using the test width/height options. To make sure everything
scales properly, we also set the window stretch mode to viewport and aspect to expand. Using this stretch mode we can easily support 16:9 and fullscreen.

![Window settings](/readme_images/window_setting.png)

## Importing models from Blender

The best luck I've had importing models from Blender is using the [Godot colloda-exporter](https://github.com/godotengine/collada-exporter) (Check the pull requests for a vesion that works with Blender 2.8+)
with the following import settings:

![Model import settings](/readme_images/model_import_setting.png)

I've made these import settings the default for all models.

The important bits here are setting your Materials location to `Mesh`, storage to `Built-In` and your Meshes storage to `Files (.mesh)`. This will prevent your PSX material from being removed every
time you re-import a new version of your model.

## PSX Material
When you assign a material to your model's surface, do so on the `MeshInstance` node and not the mesh itself. Use the `psx_material.tres` found in `assets/materials`, right click and press "Make unique", and then right click and "Save". 
This will create a unique material for each texture in your game. Take a look in the `assets/textures` directory for some examples.

I've included a few variations on the PSX material, ray_material, and water_material. These are just some examples, and meant to give you an idea of how you might modify the original shader to get a look you want.
When you want to modify the underlying shader for a new material, after you duplicate the original psx_material, make sure to right click on the shader and click "Make unique" so you don't accidentally modify
the original shader.

## Texture import settings

Here you just want to disable filter and mipmaps for that crunchy psx look. I've made this setting the default for all textures.

![Texture import settings](/readme_images/texture_import_setting.png)
