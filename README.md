# DAIN-app created with Google Colab
_This is STEP 4 of the below (possibly outdated) workflow..._

## Workflow for upscaling & optionally colorizing old films:

### 1) Source
- MakeMKV → lossless format

### 2) Pre-clean (critical)
- Deinterlace (BWDIF)
- Light denoise (don’t overdo it)

### 3) Upscale (structure first)
- Real-ESRGAN
- -OR-  SeedVR2

### 4) Colorization, if desired
- DeOldify (still solid)  -OR-
- -OR- newer diffusion-based colorizers (ComfyUI workflows)
- _*doing this before motion smoothing will produce better results_

### 5) Motion interpolation / "smoothing"
- RIFE (modern alternative to DAIN with much cleaner temporal interpolation)
- -OR- DAIN (used here *more prone to artifacts, slower, edge tearing, ghosting on fast motion)

### 6) Final grading
- slight grain reintroduction
- contrast + color balance

---
### Will be looking for or _creating_ new Colab pipelines that combine:
- Real-ESRGAN → upscale
- RIFE → smooth motion
- FFmpeg → final encode
