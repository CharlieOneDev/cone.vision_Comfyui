# ComfyUI Custom Nodes & MiniMax H3 Model Resources

A curated link collection for ComfyUI users, with a focus on MiniMax H3 video generation. This page collects the upstream project repositories and Hugging Face download pages for the custom-node ZIP files shown in the accompanying screenshots.

> **Link check date:** 2026-11-11  
> **Important:** Custom nodes and community model files are maintained by their respective authors, not necessarily by ComfyUI or MiniMax. Please read each repository's README, dependencies, and license before installing or redistributing anything.

## Contents

- [1. ComfyUI custom nodes](#1-comfyui-custom-nodes)
- [2. MiniMax H3 official model resources](#2-minimax-h3-official-model-resources)
- [3. Community MiniMax H3 models](#3-community-minimax-h3-models)
- [4. Installation notes](#4-installation-notes)
- [5. Credits and licensing](#5-credits-and-licensing)

---

## 1. ComfyUI custom nodes

The following list contains **12 unique items** identified from the ZIP filenames. `ComfyUI-DistorchMemoryManager` appeared twice in the screenshots, so it is listed only once.

| ZIP filename / project | Upstream repository | What it is |
|---|---|---|
| `ComfyUI-DistorchMemoryManager.zip` | [ussoewwin/ComfyUI-DistorchMemoryManager](https://github.com/ussoewwin/ComfyUI-DistorchMemoryManager) | VRAM and memory-management utilities. The project is now presented as **ComfyUI-VRAM-Manager** (formerly DistorchMemoryManager); the original GitHub repository URL remains the project link. |
| `ComfyUI-KJNodes.zip` | [kijai/ComfyUI-KJNodes](https://github.com/kijai/ComfyUI-KJNodes) | A broad collection of utility, workflow quality-of-life, and model-related nodes. |
| `comfyui-xnantool.zip` | [otsluo/comfyui-xnantool](https://github.com/otsluo/comfyui-xnantool) | A collection of utility, image/video, detection/segmentation, and API-related nodes. The README is primarily in Chinese. |
| `ComfyUI-Pixaroma.zip` | [pixaroma/ComfyUI-Pixaroma](https://github.com/pixaroma/ComfyUI-Pixaroma) | Image, video, audio, prompt, workflow, and canvas utility nodes. **The project moved to GitLab; use the GitLab repository below for the current upstream.** |
| `comfyui-minimax-h3-prompt-enhancer-T8.zip` | [T8mars/comfyui-minimax-h3-prompt-enhancer-T8](https://github.com/T8mars/comfyui-minimax-h3-prompt-enhancer-T8) | MiniMax H3 prompt enhancement tools, including cloud and local-model workflows. See the English README in the repository. |
| `ComfyUI-LTXVideo.zip` | [Lightricks/ComfyUI-LTXVideo](https://github.com/Lightricks/ComfyUI-LTXVideo) | LTX video-generation custom nodes and example workflows. Check the repository for the current LTX-2 / LTX-2.3 requirements. |
| `Block-Sparse-Attention.zip` | [Comfy-Org ComfyUI documentation: Model Sparse Attention](https://github.com/Comfy-Org/embedded-docs/blob/main/comfyui_embedded_docs/docs/BlockSparseAttention/en.md) | The filename alone does not identify a verifiable standalone third-party repository. ComfyUI documentation currently describes the related **Model Sparse Attention** node. Check your ComfyUI version and the ZIP's original source before installing a separate package. |
| `ComfyUI-LogicUtils.zip` | [aria1th/ComfyUI-LogicUtils](https://github.com/aria1th/ComfyUI-LogicUtils) | Logical processors and utility nodes. |
| `comfyui-art-venture.zip` | [sipherxyz/comfyui-art-venture](https://github.com/sipherxyz/comfyui-art-venture) | Utility nodes for image processing, JSON, model operations, URLs, and LLM/API workflows. |
| `ComfyUI-Jjk-Nodes.zip` | [jjkramhoeft/ComfyUI-Jjk-Nodes](https://github.com/jjkramhoeft/ComfyUI-Jjk-Nodes) | A small set of text and parameter utility nodes. |
| `ComfyUI-Logic.zip` | [theUpsider/ComfyUI-Logic](https://github.com/theUpsider/ComfyUI-Logic) | Conditional execution, comparison, and data-type utility nodes. |
| `Goohaitools-comfyui.zip` | [goohai/Goohaitools-comfyui](https://github.com/goohai/Goohaitools-comfyui) | A large practical node collection, including batch image handling, masks, face/photo utilities, layout, and saving tools. The README is primarily in Chinese. |

### Pixaroma — current upstream repository

The GitHub project page is still available as a historical/reference page, but the project README says it has moved to GitLab. For the latest source, use:

- **Current upstream:** [pixaroma/comfyui-pixaroma on GitLab](https://gitlab.com/pixaroma/comfyui-pixaroma)
- **Clone command:**

```bash
git clone https://gitlab.com/pixaroma/comfyui-pixaroma.git
```

### Block Sparse Attention — please verify the ZIP source

ComfyUI's documentation describes a **Model Sparse Attention** node and its available modes. The documentation is not proof that the screenshot's ZIP came from a particular standalone repository. Before installing it, compare the ZIP's `README`, `__init__.py`, and original download page. Documentation: [Model Sparse Attention](https://github.com/Comfy-Org/embedded-docs/blob/main/comfyui_embedded_docs/docs/BlockSparseAttention/en.md).

---

## 2. MiniMax H3 official model resources

There are two useful Hugging Face repositories. They serve different purposes and should not be confused.

### 2.1 MiniMax official original model

**Publisher:** MiniMax  
**Repository:** [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)

This is the original model repository published under the MiniMaxAI Hugging Face organization. It contains the original H3 model releases and their associated components, including the FL2VA and Ref2VA task families.

- [Open the model card and files](https://huggingface.co/MiniMaxAI/MiniMax-H3)
- [MiniMax official H3 GitHub repository](https://github.com/MiniMax-AI/MiniMax-H3)

Example Hugging Face CLI command for downloading the original task-family checkpoints:

```bash
hf download MiniMaxAI/MiniMax-H3 \
  --include "model_index.json" "FL2VA/*" "Ref2VA/*" \
  --local-dir MiniMax-H3
```

To download only the FL2VA task family:

```bash
hf download MiniMaxAI/MiniMax-H3 \
  --include "model_index.json" "FL2VA/*" \
  --local-dir MiniMax-H3
```

### 2.2 ComfyUI-organized H3 files

**Publisher:** Comfy-Org  
**Repository:** [Comfy-Org/MiniMax-H3](https://huggingface.co/Comfy-Org/MiniMax-H3)

This repository organizes H3 assets in folders that are convenient for ComfyUI users. Browse the folders below and download only the files required by your workflow:

| Asset type | Hugging Face folder |
|---|---|
| H3 diffusion model checkpoints | [`diffusion_models/`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/diffusion_models) |
| H3 text / vision encoder files | [`text_encoders/`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/text_encoders) |
| Visual and audio VAE files | [`vae/`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/vae) |
| LoRAs | [`loras/`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/loras) |
| Model patches / ControlNet-related assets | [`model_patches/`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/model_patches) |
| Embeddings | [`embeddings/`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/embeddings) |

**Encoder terminology:** H3 uses a Qwen3-VL-32B-based text/vision encoder. In ComfyUI discussions it may casually be called a CLIP encoder, but it is not a conventional SD/SDXL CLIP model. Follow the H3 workflow and model-folder instructions rather than substituting a regular CLIP checkpoint.

**Do not download the entire Comfy-Org repository unless you really need it.** The repository is very large; choose only the relevant files for your workflow and hardware.

---

## 3. Community MiniMax H3 models

The following files are **community-created / third-party weights**, not official MiniMax releases. They are shared here as optional alternatives. Check each model card and its license before using or redistributing the files.

### 3.1 Cobijada H3 Hybrid — INT8 ConvRot

**File:** `Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_int8_convrot_pruned.safetensors`  
**Reported Hugging Face size:** approximately 21 GB  
**Format:** INT8 ConvRot

- **Direct download:** [Download the `.safetensors` file](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/resolve/main/Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_int8_convrot_pruned.safetensors)
- **Repository / model card:** [Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI)
- **All files:** [Browse repository files](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/tree/main)

The author describes this as a merged MiniMax H3 checkpoint combining the first/last-frame (FL) and reference-driven (REF) conditioning variants into one hybrid checkpoint. Other formats are also listed in the repository:

- [BF16 hybrid](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/blob/main/Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_BF16_pruned.safetensors)
- [W4A8 ConvRot hybrid](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/blob/main/Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_w4a8_convrot_pruned.safetensors)

### 3.2 Qwen3-VL 32B Ultra Uncensored Heretic — INT8 ConvRot encoder

**File:** `qwen3vl_32b_minimax_h3_ultra_uncensored_heretic_int8_convrot.safetensors`  
**Hugging Face size:** 26.4 GB (approximately 24.55 GiB)  
**Format:** INT8 ConvRot  
**SHA-256:**

```text
d84547412144b7c50a6ec77437a889b869d3ace88da77ef1775d3d2a4901c192
```

- **Direct download:** [Download the `.safetensors` file from p3cyc/minimax](https://huggingface.co/p3cyc/minimax/resolve/main/qwen3vl_32b_minimax_h3_ultra_uncensored_heretic_int8_convrot.safetensors)
- **File details:** [View file page and size / SHA-256](https://huggingface.co/p3cyc/minimax/blob/main/qwen3vl_32b_minimax_h3_ultra_uncensored_heretic_int8_convrot.safetensors)
- **Repository:** [p3cyc/minimax](https://huggingface.co/p3cyc/minimax/tree/main)

This is a community encoder based on the Qwen3-VL-32B Ultra Uncensored Heretic model family. The file page reports a 26.4 GB download and the SHA-256 above. Verify the hash after downloading if you need to confirm file integrity.

A related upstream project with a differently named H3 encoder file is available here:

- [ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot](https://huggingface.co/ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot)

**Naming note:** The `p3cyc/minimax` file linked above includes `_minimax_` in its filename. The related `ethanfel` H3 repository uses a similar encoder filename without that exact naming. Do not rename or interchange files unless your workflow specifically expects that variant.

---

## 4. Installation notes

For most ComfyUI custom nodes, the general installation pattern is:

```bash
cd ComfyUI/custom_nodes

git clone <REPOSITORY_URL>
```

Then follow the specific repository's README. If it provides a `requirements.txt`, install dependencies using the **same Python environment that runs ComfyUI**:

```bash
python -m pip install -r requirements.txt
```

Restart ComfyUI after installation. Some projects also require frontend refreshes, additional models, external services, or specific PyTorch / CUDA versions. Do not assume that every node pack has the same dependencies.

For large Hugging Face files, use the repository's official download instructions or the Hugging Face CLI. Make sure you have enough disk space before starting a multi-tens-of-gigabytes download.

---

## 5. Credits and licensing

- All custom-node code belongs to its respective authors and is linked to its original project page.
- MiniMax H3 official weights and documentation belong to MiniMax and are subject to the license shown on the official model page.
- ComfyUI-organized model files are distributed by Comfy-Org; check the model repository's license and notes.
- Community merges, quantizations, and encoder variants are not official MiniMax releases. Their authors and licenses are identified on their respective model cards.
- This page is a link index for convenience. It does not host or re-upload model weights.

If you maintain one of the linked projects and notice an outdated link or incorrect attribution, please open an issue or submit a pull request.
