# DAIN-app created with Google Colab
_This is STEP 4 of the below (possibly outdated) workflow..._

Note: Don’t process a whole feature-length film at once. Process by chapter, or 5–10 minute chunks to avoid Colab sessions timeout and VRAM crashes.

## Workflow for upscaling & optionally colorizing old films:

### 1) Source
- _MakeMKV_ → lossless format

### 2) Pre-clean (critical)
- Deinterlace (_BWDIF_, _FFmpeg_  or _Handbrake_)
- Apply light temporal denoise with _hqdn3d_
- -OR- _[VapourSynth](https://github.com/kodxana/VapourSynthColab)_ temporal filtering (don’t overdo it)  
_*AI models love to interpret MPEG mosquito noise as “detail”_

### 3) Upscale (structure first)
- _[Real-ESRGAN](https://github.com/yuvraj108c/4k-video-upscaler-colab)_
- -OR-  _SeedVR2_

### 4) Colorization, if desired
- _DeOldify_ (still solid) 
- -OR- newer diffusion-based colorizers (_ComfyUI_ workflows)  
_*doing this before motion smoothing will produce better results_

### 5) Motion interpolation / "smoothing"
- _RIFE_ (modern alternative to DAIN with much cleaner temporal interpolation)
- -OR- _DAIN_ (used here *more prone to artifacts, slower, edge tearing, ghosting on fast motion)

### 6) Final grading
- slight grain reintroduction
- contrast + color balance

---
### Will be looking for or _creating_ new Colab pipelines that combine:
- Real-ESRGAN → upscale
- RIFE → smooth motion
- FFmpeg → final encode
