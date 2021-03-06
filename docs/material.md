
Material
========


The material properties of the object’s surface.
Material Attributes
-------------------

|Attribute|Description|Type|Default|Required|
| :--- | :--- | :--- | :--- | :--- |
|src|URI, relative or full path of an image/video file. e.g. 'store/users/wiselab/images/360falls.mp4'|string||No|
|transparent|Whether material is transparent. Transparent entities are rendered after non-transparent entities.|boolean|```False```|No|
|opacity|Extent of transparency. If the transparent property is not true, then the material will remain opaque and opacity will only affect color.|number|```1.0```|No|
|colorWrite|Color write|boolean||No|
|render-order|The render-order system takes a comma-delimited list of strings that name the render order layers. The render order layers will map to a number starting from 0 and counting up from there.|string|```'0'```|No|
|side|Which sides of the mesh to render. Can be one of front, back, or double.|string; One of: ```['front', 'back', 'double']```|```'front'```|No|
|color|Base diffuse color.|string|```'#7f7f7f'```|No|
|alphaTest|Alpha test threshold for transparency.|number|```0```|No|
|depthTest|Whether depth testing is enabled when rendering the material.|boolean|```True```|No|
|flatShading|Use THREE.FlatShading rather than THREE.StandardShading.|boolean|```False```|No|
|npot|Use settings for non-power-of-two (NPOT) texture.|boolean|```False```|No|
|offset|Texture offset to be used.|object|```{'x': 1, 'y': 1}```|No|
|repeat|Texture repeat to be used.|object|```{'x': 1, 'y': 1}```|No|
|shader|Which material to use. Defaults to the standard material. Can be set to the flat material or to a registered custom shader material.|string|```'standard'```|No|
|vertexColors|Whether to use vertex or face colors to shade the material. Can be one of none, vertex, or face.|string; One of: ```['none', 'vertex', 'face']```|```'none'```|No|
|visible|Whether material is visible. Raycasters will ignore invisible materials.|boolean|```True```|No|
|blending|The blending mode for the material’s RGB and Alpha sent to the WebGLRenderer. Can be one of none, normal, additive, subtractive or multiply|string; One of: ```['none', 'normal', 'additive', 'subtractive', 'multiply']```|```'normal'```|No|
|dithering|Whether material is dithered with noise. Removes banding from gradients like ones produced by lighting.|boolean|```True```|No|
