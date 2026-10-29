# LA-2A Arm Nong Muang — FIXED32 Rotary DrawLine Compile Fix

This project uses JUCE 8 and builds a VST3 plug-in for Windows via CMake/GitHub Actions. FIXED32 resolves the MSVC C2661 errors in the rotary indicator by passing `juce::Line<float>` objects to the JUCE `Graphics::drawLine` overload.

## Rotary controls
- GAIN and PEAK REDUCTION are real `juce::Slider` controls using `RotaryHorizontalVerticalDrag`.
- The custom `PointerLookAndFeel` paints a black bezel, metallic silver face, inner bevel, and value-driven indicator.
- SliderAttachment binds each rotary to APVTS parameters `gain` and `peak`, so automation and saved host state use the actual parameter values.
- The numeric labels below the knobs update from the current slider values.
- The processor applies gain and peak-reduction values in `processBlock()`.

## Build
Open this repository in GitHub and run **Actions → Build LA-2A VST3 (Windows)**. A successful archive/ZIP check is not a substitute for a Windows compiler build; verify the Actions result before installing in Nuendo 15.

## Install
Use the `LA2A-Windows-VST3` artifact produced by a successful workflow run and install/copy the VST3 bundle according to your Windows VST3 setup.
