# Capabilities and limits

Openstudio is an early local preview. Controls that require an unavailable backend should report that dependency rather than silently complete.

| Workflow | Current scope | Dependency or qualification |
|---|---|---|
| Create | Text, single-image, and multi-view model generation | Local model setup; multi-view uses separately downloaded Hunyuan3D weights and backend |
| Parts | Select, split, hide/show, rename, merge, separate selected faces, and cap small holes | Some selection and geometry operations are assisted |
| Optimize | Triangle/quad remesh and target face count | Blender adapter is used for supported processing; targets are approximate |
| UVs | Automatic unwrap, packing, and preview | Blender adapter |
| Materials | PBR maps, 2K/4K/8K textures, GPU bake/upscale and AI tiled refinement | CUDA texture workflows and local AI require a working NVIDIA CUDA GPU/driver; CPU-capable Blender/native operations remain available without CUDA. Generated maps may be approximations |
| Rig | Biped/quadruped landmarks, automatic weights, checks, and animation playback | Blender adapter is used for automatic weights; animation import needs matching bones |
| Export | GLB, FBX, OBJ, STL | Blender is required for selected conversions; destination applications should validate the result |
| Independent editor | Modeling, sculpting, and animation authoring preview | Does not yet provide complete Blender parity |
| Worlds | OSM and terrain-based level workflows | Geographic data is downloaded when requested; check source/coverage and attribution |
| Storyboards | Planned game-design workflow | Not included as a completed workflow in this preview |

The app is not a Unity-certified production pipeline. It does not bundle Blender, Python, model weights, or AI backends. The app's Setup screen is the source of truth for this PC's detected components.

The optional Hunyuan3D-2mv setup is by Preston Harmon and has no Tencent affiliation or endorsement. Its pinned license excludes the European Union, United Kingdom, and South Korea; model and output use are limited to the license Territory, and its rules prohibit using the model or outputs to improve another AI model. Read the [included full license](licenses/TENCENT_HUNYUAN_3D_2.0_COMMUNITY_LICENSE.txt) and Acceptable Use Policy before installing it. Leave it uninstalled where the license does not authorize use.
