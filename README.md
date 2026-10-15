# Openstudio

Openstudio is a local Windows desktop studio for making and editing game assets. It includes a 3D viewport, model creation and editing workflows, an independent modeling/sculpting/animation preview, material and 8K texture tools, world data workflows, and project history.

**Download:** get the Windows portable build from the [Openstudio 0.2.0-beta.1 release page](https://github.com/itsjukajr-netizen/Openstudio/releases/tag/v0.2.0-beta.1). Choose the `.exe` asset. No installer or administrator rights are required. Openstudio keeps projects, settings, and history in your existing Windows application-data folder.

## First launch

The portable application includes the Openstudio interface and worker scripts. It does not include Blender, Python, AI model weights, or third-party AI backends. Open **Setup** inside the app to check dependencies and install supported model packages. Model downloads need internet access and several gigabytes of free storage; after setup, supported generation runs locally. A CUDA-capable NVIDIA GPU is recommended for local AI and GPU processing. CPU fallbacks and unsupported GPU operations are reported by the app.

Close any older Game Tools Studio window normally before starting Openstudio. They share the same single-instance and project-data identity so that your previous projects stay available.

For the full local toolchain, install Python 3.11 and Blender 5.2, then follow the Setup panel. The application is Windows-only in this release. It does not send projects to a hosted generation service. OSM/geographic data downloads require internet access and the relevant data attribution shown by the app.

## What works in this preview

Create models from text, a single image, or multiple reference views when the corresponding local backend is installed. Edit imported or generated assets with parts, optimization, UVs, materials, rigging, and exports. The texture workflow supports 2K, 4K, and 8K outputs, GPU baking/upscaling where available, resumable tiled refinement, and revision-safe apply/cancel behavior. The independent editor provides modeling, sculpting, and animation authoring workflows.

Some tools depend on separately installed backends. The independent editor is still a preview and does not claim complete Blender parity. Read [Capabilities and limits](CAPABILITIES.md) before relying on a specialized workflow; the app also reports missing tools and unsupported settings in Setup and Details.

**Optional Hunyuan3D-2mv terms:** this backend is provided by Preston Harmon and is not affiliated with, sponsored, or endorsed by Tencent. Its pinned community license does not apply in the European Union, United Kingdom, or South Korea, and the license restricts use of both the model and its outputs to its defined Territory. It also prohibits using the model or outputs to improve another AI model. Do not install or use this backend where its license does not authorize you. Read the [included license copy](licenses/TENCENT_HUNYUAN_3D_2.0_COMMUNITY_LICENSE.txt) and its Acceptable Use Policy before setup.

## Data and recovery

Projects use portable manifests, immutable asset revisions, thumbnails, and a local job/revision database. Processing creates new revisions, and cancellation or failure preserves committed work. Keep the entire project folder when moving a project. The default Windows data directory remains `%APPDATA%\game-tools-studio` so installations renamed from earlier releases continue to find existing projects and settings. An explicit `STUDIO_DATA_DIR` overrides that location.

## Credits and licenses

Openstudio is created by Preston Harmon. Openstudio does not grant redistribution rights to separately downloaded models, Blender, Python, or optional third-party applications. See [third-party notices](THIRD_PARTY_NOTICES.md) and the license files included with bundled runtime components. The Hunyuan3D-2mv backend uses its own community license and must be installed separately.

## Troubleshooting

If a tool is unavailable, open **Setup** and follow its status and repair actions. Open **Details** on a failed job for the saved diagnostic log. Generation has a bounded timeout; after failure, reopen the project and submit the job again. Existing revisions remain available.

Report issues in the repository's [Issues](https://github.com/itsjukajr-netizen/Openstudio/issues) page. Include the app version, tool status, and relevant sanitized diagnostic details; do not attach private project files or model weights.
