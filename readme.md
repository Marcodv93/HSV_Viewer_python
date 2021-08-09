# Summary
A simple visualization tool to generate and modify interactively images coded with HSV colorspace.

# Case use
In Forster Resonance Energy Transfer (FRET) biosensors fluorescence imaging, it's common to represent the FRET ratios as proxy for the biosensor response.

This tool can be useful to create and display FRET ratio images (instead of simple traces) coding the FRET response of the biosensor in HSV colorspace. In this way, the spatio-temporal information can be mantained.

# Implementation
_Function RGBtoHSV()_ implements the colorspace conversion as outlined [here](https://en.wikipedia.org/wiki/HSL_and_HSV#HSV_to_RGB).

_Function RGBForRatioIntensity()_ sets the **Hue** to the FRET ratio clipped between 0 and 300 (not the full 360 deg so that the color limits are clearer), **Value** to a normalized intensity coming from the image brightness itself and **Saturation** to 1.

_Function IMDImage()_ creates a 16bit image in HSV colorspace coding the FRET ratio using the define 2 functions above.

_Function HSV_Display()_ together with the interact module can be used to display and play around with the parameters of the generated HSV ratio image.

# Known issues
Its current implementation is too slow with medium-large (512x512, or 1024x1024) images for the interactive slider to work well on the fly.
