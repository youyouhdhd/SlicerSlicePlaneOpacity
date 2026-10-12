# Slice Plane Opacity for 3D Slicer

**Slice Plane Opacity** is a small 3D Slicer extension that adds a simple UI for controlling the opacity of the standard **Red**, **Yellow**, and **Green** slice planes when they are displayed in a 3D view.

It is intentionally focused on one task: controlling the 3D slice-plane model opacity. It does **not** change the foreground/background opacity used for 2D slice compositing. No patents are known to apply specifically to this extension.

![Slice Plane Opacity overview](Documentation/SlicePlaneOpacityOverview.png)

## Included module

- **Slice Plane Opacity**: provides Slicer-native controls for the 3D visibility and opacity of the standard Red, Yellow, and Green slice planes.

## Features

- Master opacity slider for all three standard slice planes
- Independent Red, Yellow, and Green opacity sliders
- Per-plane **Show in 3D** switches
- Live updates in 3D views
- Refresh button to re-read current scene state
- One-click opacity reset
- No external Python packages or compiled code

Opacity uses the standard Slicer convention:

- `0.0` = fully transparent
- `1.0` = fully opaque

## Usage

1. Load a volume in 3D Slicer.
2. Open **Slice Plane Opacity** from the **Visualization** module category.
3. Enable **Show in 3D** for any slice plane you want to see.
4. Drag the master slider or the Red/Yellow/Green sliders.

The module changes the `vtkMRMLModelDisplayNode` opacity of each slice model. It does not modify your volume data.

## Installation from source

Until the extension is available in Slicer's Extensions Manager:

1. Download or clone this repository.
2. In Slicer, open **Edit > Application Settings > Modules**.
3. Add the repository's `SlicePlaneOpacity` directory to **Additional module paths**.
4. Restart Slicer.
5. Open **Slice Plane Opacity** from the module selector.

For development, the repository also includes the normal Slicer extension CMake structure and can be opened with Slicer's Extension Wizard.

## Developer notes

The core operation is equivalent to:

```python
sliceLogic = slicer.app.layoutManager().sliceWidget("Red").sliceLogic()
sliceModel = sliceLogic.GetSliceModelNode()
sliceModel.GetDisplayNode().SetOpacity(0.5)
```

The extension wraps this behavior in a small Slicer-native Qt/CTK interface and handles all three standard slice views.

## Slicer Extensions Index

`ExtensionsIndex/SlicePlaneOpacity.json` is included as a ready-to-submit catalog entry for the official [Slicer Extensions Index](https://github.com/Slicer/ExtensionsIndex).

The extension is initially proposed as **Tier 1 (Experimental)**, which is the appropriate entry tier for a new extension. Once it has broader usage and maintenance history it can be considered for a higher tier by Slicer maintainers.

## Compatibility

The extension is pure Python and is designed for modern 3D Slicer 5.x releases. It has no third-party dependencies.

## License

BSD 3-Clause License. See [LICENSE.txt](LICENSE.txt).

## Author and support

Maintainer: **youyouhdhd**

Please use GitHub Issues in this repository for bug reports and feature requests.

## Publication

There is currently no publication associated with this extension.
