# Rendering settings:

Get current Blender version:
```
import bpy
print(bpy.app.version_string)
#out: 4.2.3 LTS
```

Choosing a **render engine**:


```py
import bpy
from IPython.display import display, Image

bpy.context.scene.render.engine = "BLENDER_WORKBENCH"
bpy.context.scene.render.resolution_x = 400
bpy.context.scene.render.resolution_y = 200
bpy.ops.render.render()
bpy.data.images["Render Result"].save_render(filepath="test.png")
display(Image(filename="test.png"))
```

![alt text](image-1.png)


```
bpy.context.scene.render.engine = "BLENDER_EEVEE_NEXT"
bpy.context.scene.render.resolution_x = 400
bpy.context.scene.render.resolution_y = 200
bpy.ops.render.render()
bpy.data.images["Render Result"].save_render(filepath="test.png")
display(Image(filename="test.png"))
```

![alt text](image-2.png)



Setting **sample size** in cycles to 10:

```
bpy.context.scene.render.engine = "CYCLES"
bpy.context.scene.cycles.samples = 10  # Set sample size to 100

bpy.context.scene.render.resolution_x = 400
bpy.context.scene.render.resolution_y = 200
bpy.ops.render.render()
bpy.data.images["Render Result"].save_render(filepath="test.png")
display(Image(filename="test.png"))
```

![alt text](image-3.png)