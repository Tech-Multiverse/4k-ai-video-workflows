# 4k AI Video ComfyUI Workflows

These are the workflows I used to create 4K AI videos on a laptop with an RTX4060 that only has 8GB of VRAM.

[Read the article about this project on my blog.](https://tech-multiverse.com/projects/how-to-create-4k-ai-videos-locally-with-low-vram/)


[Watch this YouTube video to learn more about the project.](https://youtu.be/HkIMubtTqhQ)

[This is a sample of the videos I've made with these workflows.](https://youtu.be/2107IdC6nlE)


## Notes
[ComfyUI's WAN examples](https://comfyanonymous.github.io/ComfyUI_examples/wan/)     

[Models on Huggingface](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/tree/main/split_files/diffusion_models)

I found that you tend to avoid issues with each step broken out into a different workflow and running them one at a time rather than tie too many steps together. However, you may still need to restart ComfyUI or your computer at times, especially if you are getting garbage back.

You may need to use the tiled VAE Decoder node, which is included in workflow that might need it.

Text-to-Video can run both `t2v_14B_fp16` or `t2v_14B_fp8_scaled` models, but Image-to-Video crashed unless I used `i2v_480p_14B_fp8_scaled`. 

Image-to-Video produces better quality more often than Text-to-Video. Just try to use a higher resolution image.

**THIS REQUIRES PATIENCE!!**
Is this better than paying for a service? Maybe not, but I wanted to see if I could do it and to see what I would learn.     

I learned a ton from this project, which is what matters most!

### Resolution = Time w/ 8GB VRAM

**480p = 44 minutes** (odd artifacts)          
16:9 = 832x480     


**10-15 minutes!** (low quality)          
16:9 = 512x288     
9:16 = 288x512 

**60 minutes!** (decent quality)         
16:9 = 910x512     
9:16 = 512x910        
    
     
| Target Size | 2x Upscale| 4x Upscale |
| ----------- | ----------- | ----------- |
| 1920×1080| 960×540| 480×270 |
| 3840×2160| 1920×1080| 960×540 |

# Workflows Provided

* Text-to-Video WAN 2.1
* Image-to-Video WAN 2.1
* WEBP-to-4k Upscaler for WAN2.1 generations
* MP4--to-4k Upscaler for FramePack generations

# Getting Started
1. Drop the workflows into the `ComfyUI\user\default\workflows` folder.

2. Download the models (links below)

3. Start ComfyUI
4. Install any missing custom nodes

5. Have Fun!

# Model Links and Locations

Model: [wan2.1_i2v_480p_14B_fp8_scaled.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_i2v_480p_14B_fp8_scaled.safetensors)
Location: `ComfyUI\models\diffusion_models\`

Model: [wan2.1_t2v_14B_fp16.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_t2v_14B_fp16.safetensors)
Location: `ComfyUI\models\diffusion_models\`

Model: [wan2.1_t2v_14B_fp8_scaled.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/diffusion_models/wan2.1_t2v_14B_fp8_scaled.safetensors)
Location: `ComfyUI\models\diffusion_models\`

---
Model: [wan_2.1_vae.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/vae/wan_2.1_vae.safetensors)
Location: `ComfyUI\models\vae\`

---
Model: [4x_foolhardy_Remacri.pth](https://huggingface.co/FacehugmanIII/4x_foolhardy_Remacri/blob/main/4x_foolhardy_Remacri.pth)
Location: `ComfyUI\models\upscale_models\`

---

Model: [clip_vision_h.safetensors](https://huggingface.co/Comfy-Org/Wan_2.1_ComfyUI_repackaged/blob/main/split_files/clip_vision/clip_vision_h.safetensors)
Location: `ComfyUI\models\clip_vision\`

Model: [umt5_xxl_fp8_e4m3fn_scaled.safetensors](https://huggingface.co/Kijai/WanVideo_comfy/blob/main/umt5-xxl-enc-fp8_e4m3fn.safetensors)
Location: `ComfyUI\models\clip_vision\`

---
## Useful Sites

[WAN 2.1 site](https://www.wan-ai.org/)

[FramePack GitHub page](https://github.com/lllyasviel/FramePack)