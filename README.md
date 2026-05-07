# DAIN-app created with Google Colab
See STEP 4 of the below workflow...

## Workflow for upscaling & optionally colorizing old films:

1) Source
MakeMKV → lossless format

2) Pre-clean (critical)
Deinterlace (BWDIF)
Light denoise (don’t overdo it)

3) Upscale (structure first)
Real-ESRGAN OR SeedVR2

4) (Optional but powerful) motion interpolation
RIFE (modern alternative to DAIN with much cleaner temporal interpolation)
or DAIN (used here *more prone to artifacts, slower, edge tearing, ghosting on fast motion)

5) Colorization, if desired
DeOldify (still solid)
or newer diffusion-based colorizers (ComfyUI workflows)

6) Final grading
slight grain reintroduction
contrast + color balance


Will be looking for or creating new Colab pipelines that combine:
Real-ESRGAN
RIFE
FFmpeg
