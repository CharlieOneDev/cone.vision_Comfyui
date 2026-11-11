# ComfyUI & MiniMax H3 Resources

A curated collection of ComfyUI custom nodes, MiniMax H3 model files, community model variants, and useful installation references.

The links below point to the original project pages or Hugging Face repositories whenever available. Model weights are hosted by their respective publishers and contributors; this repository is a resource index and does not re-host the files.

> **Last reviewed:** November 11, 2026  
> **Note:** Always check each project's README, dependencies, model card, and license before installing or using a model.

## Contents

- [1. ComfyUI custom nodes and references](#1-comfyui-custom-nodes-and-references)
- [2. Official MiniMax H3 resources](#2-official-minimax-h3-resources)
- [3. Community MiniMax H3 models](#3-community-minimax-h3-models)
- [4. Installation notes](#4-installation-notes)
- [5. Licenses and attribution](#5-licenses-and-attribution)

---

## 1. ComfyUI custom nodes and references

A collection of useful ComfyUI extensions and related documentation.

| Project | Repository / Resource | Description |
|---|---|---|
| **ComfyUI-VRAM-Manager** (formerly DistorchMemoryManager) | [GitHub](https://github.com/ussoewwin/ComfyUI-DistorchMemoryManager) | Memory and VRAM management utilities for ComfyUI, including model and cache cleanup tools. |
| **ComfyUI-KJNodes** | [GitHub](https://github.com/kijai/ComfyUI-KJNodes) | A broad collection of utility, workflow, and model-related nodes. |
| **ComfyUI XnanTool** | [GitHub](https://github.com/otsluo/comfyui-xnantool) | A collection of extended ComfyUI nodes, including API, image, video, and utility features. |
| **ComfyUI-Pixaroma** | [GitLab — current upstream](https://gitlab.com/pixaroma/comfyui-pixaroma) · [GitHub — project history](https://github.com/pixaroma/ComfyUI-Pixaroma) | A large collection of workflow, prompt, image, video, and interface utilities. The project moved its active development to GitLab. |
| **MiniMax H3 Prompt Enhancer (T8)** | [GitHub](https://github.com/T8mars/comfyui-minimax-h3-prompt-enhancer-T8) | Prompt-enhancement nodes and related workflows for MiniMax H3. Check the README for supported modes and setup requirements. |
| **ComfyUI-LTXVideo** | [GitHub](https://github.com/Lightricks/ComfyUI-LTXVideo) | Custom nodes and example workflows for LTX video generation. |
| **Block Sparse / Model Sparse Attention** | [ComfyUI documentation](https://github.com/Comfy-Org/embedded-docs/blob/main/comfyui_embedded_docs/docs/BlockSparseAttention/en.md) | Documentation for ComfyUI's Model Sparse Attention feature. This link is a documentation reference, not a standalone custom-node repository. |
| **ComfyUI-LogicUtils** | [GitHub](https://github.com/aria1th/ComfyUI-LogicUtils) | Logical processors and general-purpose utility nodes. |
| **ArtVenture Custom Nodes** | [GitHub](https://github.com/sipherxyz/comfyui-art-venture) | Image-processing, JSON, model-operation, URL, and other utility nodes. |
| **ComfyUI-Jjk-Nodes** | [GitHub](https://github.com/jjkramhoeft/ComfyUI-Jjk-Nodes) | Lightweight text and parameter utility nodes. |
| **ComfyUI-Logic** | [GitHub](https://github.com/theUpsider/ComfyUI-Logic) | Conditional execution, comparison, and data-type utility nodes. |
| **Goohaitools-ComfyUI** | [GitHub](https://github.com/goohai/Goohaitools-comfyui) | A practical node collection for batch image handling, masks, image layout, face/photo utilities, and more. |

### Installing custom nodes

For most GitHub-hosted custom nodes, use the following general pattern from your ComfyUI installation:

```bash
cd ComfyUI/custom_nodes
git clone <REPOSITORY_URL>
```

For Pixaroma, use its current GitLab repository:

```bash
cd ComfyUI/custom_nodes
git clone https://gitlab.com/pixaroma/comfyui-pixaroma.git
```

After cloning, follow the installation instructions in that project's README. Install any required Python dependencies in the same Python environment used by ComfyUI, then restart ComfyUI.

---

## 2. Official MiniMax H3 resources

There are two primary resources for MiniMax H3: the original model published by MiniMax and the ComfyUI-oriented model package maintained by Comfy-Org.

### 2.1 MiniMax official model repository

**Publisher:** MiniMax  
**Hugging Face:** [MiniMaxAI/MiniMax-H3](https://huggingface.co/MiniMaxAI/MiniMax-H3)  
**Official GitHub:** [MiniMax-AI/MiniMax-H3](https://github.com/MiniMax-AI/MiniMax-H3)

The Hugging Face repository contains the official MiniMax H3 model release and its associated files. Refer to the model card and repository file browser for the latest versions and usage instructions.

### 2.2 ComfyUI-organized model files

**Publisher:** Comfy-Org  
**Hugging Face:** [Comfy-Org/MiniMax-H3 — all files](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main)

This repository repackages MiniMax H3 assets in a directory structure designed for ComfyUI. It is usually the most convenient starting point when setting up H3 in ComfyUI.

| Model component | Hugging Face directory | Typical ComfyUI destination |
|---|---|---|
| H3 diffusion checkpoints (FL2VA / REF2VA) | [`diffusion_models`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/diffusion_models) | `ComfyUI/models/diffusion_models/` |
| Qwen3-VL H3 text / vision encoders | [`text_encoders`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/text_encoders) | `ComfyUI/models/text_encoders/` |
| H3 LoRAs | [`loras`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/loras) | `ComfyUI/models/loras/` |
| Audio and video VAEs | [`vae`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/vae) | `ComfyUI/models/vae/` |
| ControlNet / model patch files | [`model_patches`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/model_patches) | `ComfyUI/models/model_patches/` |
| H3 embeddings | [`embeddings`](https://huggingface.co/Comfy-Org/MiniMax-H3/tree/main/embeddings) | `ComfyUI/models/embeddings/` |
| Example workflows | [Model card — Workflows](https://huggingface.co/Comfy-Org/MiniMax-H3#workflows) | Load the workflow JSON in ComfyUI |

**Text encoder note:** The H3 text/vision encoder is based on Qwen3-VL-32B. It may be referred to informally as a CLIP model in ComfyUI workflows, but it is not a conventional SD/SDXL CLIP checkpoint. Use an H3-compatible workflow and encoder type.

**Download tip:** The Comfy-Org repository is very large. Download only the checkpoints and supporting files required by your workflow and hardware. Its model card recommends `int8_convrot` diffusion checkpoints when using a compatible PyTorch CUDA 13.0 environment; consult the current model card for format guidance.

---

## 3. Community MiniMax H3 models

The following files are community-created or community-modified alternatives. They are **not official MiniMax releases**. Review the model cards and applicable licenses before downloading or using them.

### 3.1 Cobijada H3 Hybrid — INT8 ConvRot

**File name:**

```text
Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_int8_convrot_pruned.safetensors
```

- **Format:** INT8 ConvRot
- **Download size:** approximately 21 GB
- **Model repository:** [Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI)
- **Direct download:** [Download the INT8 ConvRot file](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/resolve/main/Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_int8_convrot_pruned.safetensors)
- **Other available formats:** [BF16](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/blob/main/Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_BF16_pruned.safetensors) · [W4A8 ConvRot](https://huggingface.co/Winnougan/Cobijada_Minimax-H3_Hybrid_Pruned_ComfyUI/blob/main/Cobijada_H3_Hybrid_Uncensored_pruned_hybrid_w4a8_convrot_pruned.safetensors)

The author describes this as a merged H3 checkpoint combining first/last-frame (FL) and reference-driven (REF) conditioning into one hybrid model. Check the model card for its design, supported workflows, and license information.

**SHA-256:**

```text
85a4573a861810bfb250b3cc38f492870b6a3b01048feaa02a85bc7c511b7ca1
```

### 3.2 Qwen3-VL 32B Ultra Uncensored Heretic — INT8 ConvRot H3 encoder

**File name:**

```text
qwen3vl_32b_minimax_h3_ultra_uncensored_heretic_int8_convrot.safetensors
```

- **Format:** INT8 ConvRot
- **Download size:** approximately 26.4 GB (24.55 GiB)
- **Hugging Face repository:** [p3cyc/minimax](https://huggingface.co/p3cyc/minimax/tree/main)
- **Direct download:** [Download the exact file](https://huggingface.co/p3cyc/minimax/resolve/main/qwen3vl_32b_minimax_h3_ultra_uncensored_heretic_int8_convrot.safetensors)
- **Original model / technical information:** [ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot](https://huggingface.co/ethanfel/Qwen3-VL-32B-Ultra-Heretic-H3-ComfyUI-INT8-ConvRot)

This is a community H3 conditioning encoder based on the Qwen3-VL-32B Ultra Uncensored Heretic model family. The encoder contains the Qwen3-VL embedding, language layers 0–49, and the vision tower. It is an H3 conditioning component, not a complete standalone Qwen3-VL generation model.

**SHA-256:**

```text
d84547412144b7c50a6ec77437a889b869d3ace88da77ef1775d3d2a4901c192
```

The p3cyc file page reports this checksum. The original creator's model card lists the matching INT8 ConvRot encoder checksum under a slightly different filename. Verify the checksum after downloading if file integrity is important to your workflow.

---

## 4. Installation notes

1. Check the ComfyUI version and hardware requirements stated by each project.
2. Install custom nodes using ComfyUI Manager or the repository's recommended Git command.
3. Read each node pack's README before installing Python dependencies.
4. Install dependencies in the Python environment that actually runs ComfyUI.
5. Place model files in the matching `ComfyUI/models/` subdirectory and use a workflow compatible with that model format.
6. Restart ComfyUI after installation or model-folder changes. Refresh the browser if newly installed nodes do not appear.

For Hugging Face downloads, the `hf` CLI can also be used when installed and authenticated as required by the repository:

```bash
hf download <REPOSITORY_ID> <FILE_PATH> --local-dir <DESTINATION>
```

Large model files can require tens of gigabytes of free disk space. Confirm the available storage before downloading.

---

## 5. Licenses and attribution

- **MiniMax H3:** The official model is distributed under the [MiniMax H3 Community License Agreement](https://huggingface.co/MiniMaxAI/MiniMax-H3). Read the license before use, especially for commercial applications or redistribution.
- **Comfy-Org model package:** Check the [Comfy-Org repository](https://huggingface.co/Comfy-Org/MiniMax-H3) for the package's license and usage notes. The repository identifies the MiniMax H3 Community License Agreement.
- **Community model variants:** Follow the license and usage conditions stated by each individual model author. A community quantization or merge does not replace the license obligations of the underlying model.
- **Custom nodes:** Each extension remains the work of its respective author and is governed by the license in its own repository.

This page provides links for discovery and convenience. It does not claim ownership of the linked projects or model weights and does not re-host third-party files.

If you maintain one of the linked projects and notice an outdated URL or incorrect attribution, please open an issue or submit a pull request.
