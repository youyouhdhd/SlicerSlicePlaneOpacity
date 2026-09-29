# Contributing

Bug reports and small pull requests are welcome.

When changing behavior, please keep the extension focused on the display of Slicer's standard Red, Yellow, and Green slice planes in 3D views. Avoid adding unrelated volume-processing functionality.

## Development checks

- Keep the module free of external Python dependencies when possible.
- Run a Python syntax check before committing.
- Test the module in a current 3D Slicer 5.x release.
- Confirm that changing 3D slice-plane opacity does not change 2D foreground/background compositing.
