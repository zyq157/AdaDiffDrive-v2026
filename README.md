<div align="center">
<h1>AdaDiffDrive</h1>
<h3>AdaDiffDrive: Multi-Modal Adaptive Diffusion-Based Trajectory Planning for End-to-End Autonomous Driving</h3>

</div>

## Abstract
Generating safe, diverse and even human-like trajectories in complex traffic environments is a major challenge for end-to-end autonomous driving (E2E-AD). Diffusion-based planners have recently gained popularity as a promising solution owing to their ability to approximate the high-dimensional and multi-modal action distribution. Unfortunately, existing standard diffusion planners need to iteratively denoise from noisy samples, with a high cost, whereas the existing truncated diffusion planners are usually defined via an existing fixed static anchor, which may not fit highly dynamic or long-tail driving situations. To overcome these issues, we present AdaDiffDrive, an adaptive truncated diffusion planner that substitutes the existing static statistical prior with scene-aware dynamic priors. AdaDiffDrive consists of three key components. First, a Multi-modal Sparse Fusion Transformer (MSFT) compresses camera and LiDAR observations into compact sparse scene tokens, aligning perception sparsity with planning intent. Second, these tokens are used to generate $K$ scene-adaptive anchors and construct an adaptive anchored gaussian distribution (AAGD), which provides context-aware trajectory priors while preserving multi-modal diversity. Third, a cascaded diffusion decoder equipped with adaptive truncated cross-attention selectively associates noisy trajectory points with nearby safety-critical sparse tokens, providing localized scene guidance during the denoising process. By coupling sparse scene encoding with adaptive truncated diffusion, AdaDiffDrive mitigates the trade-off between trajectory diversity, generation quality, and planning efficiency. Experiments on the NAVSIM planning benchmark show that AdaDiffDrive achieves 84.7 PDMS. Additional evaluation on nuScenes further demonstrates competitive trajectory accuracy, collision avoidance performance, and near real-time inference. These results indicate that adaptive scene-aware priors and sparse safety-guided diffusion decoding can improve the robustness and safety of E2E-AD trajectory planning.
</div>

## Qualitative Results on NAVSIM Navtest Split
<div align="center">
<b>Going straight with car-following and lane-changing behaviors.</b>
<img src="assets/straight_0.png" />
<b>Going straight with diverse lane-changing behavior, which interacts with traffic light and stops at the stop line.</b>
<img src="assets/straight_1.png" />
<b>Turning left with diverse lane-changing behavior, which interacts with surrounding agents.</b>
<img src="assets/left_0.png" />
<b>Turning right with car-following and overtaking behaviors.</b>
<img src="assets/right_0.png" />
</div>

## Video Demo on Real-world Application


https://github.com/user-attachments/assets/bd2364f3-73fd-4c29-b8b2-ead11f78926d





## Getting Started

- [Getting started from NAVSIM environment preparation](https://github.com/autonomousvision/navsim?tab=readme-ov-file#getting-started-)
- [Preparation of DiffusionDrive environment](docs/install.md)
- [Training and Evaluation](docs/train_eval.md)


## Checkpoint

> Results on NAVSIM


| Method | Model Size | Backbone | PDMS | Weight Download |
| :---: | :---: | :---: | :---:  | :---: |
| DiffusionDrive | 60M | [ResNet-34](https://huggingface.co/timm/resnet34.a1_in1k) | [88.1](https://github.com/hustvl/DiffusionDrive/releases/download/DiffusionDrive_88p1_PDMS_Eval_file/diffusiondrive_88p1_PDMS.csv) | [Hugging Face](https://huggingface.co/hustvl/DiffusionDrive) |

> Results on nuScenes


| Method | Backbone | Weight | Log | L2 (m) 1s | L2 (m) 2s | L2 (m) 3s | L2 (m) Avg | Col. (%) 1s | Col. (%) 2s | Col. (%) 3s | Col. (%) Avg |
| :---: | :---: | :---: | :---: | :---: | :---: | :---:| :---: | :---: | :---: | :---: | :---: |
| DiffusionDrive | ResNet-50 | [HF](https://huggingface.co/hustvl/DiffusionDrive) | [Github](https://github.com/hustvl/DiffusionDrive/releases/download/DiffusionDrive_nuScenes/diffusiondrive_stage2.log.log) |  0.27 | 0.54  | 0.90 |0.57 | 0.03  | 0.05 | 0.16 | 0.08  |



## Contact
If you have any questions, please contact [Bencheng Liao](https://github.com/LegendBC) via email (bcliao@hust.edu.cn).

## Acknowledgement
DiffusionDrive is greatly inspired by the following outstanding contributions to the open-source community: [NAVSIM](https://github.com/autonomousvision/navsim), [Transfuser](https://github.com/autonomousvision/transfuser), [Diffusion Policy](https://github.com/real-stanford/diffusion_policy), [MapTR](https://github.com/hustvl/MapTR), [VAD](https://github.com/hustvl/VAD), [SparseDrive](https://github.com/swc-17/SparseDrive).

## Citation
If you find DiffusionDrive is useful in your research or applications, please consider giving us a star 🌟 and citing it by the following BibTeX entry.

```bibtex
 @article{diffusiondrive,
  title={DiffusionDrive: Truncated Diffusion Model for End-to-End Autonomous Driving},
  author={Bencheng Liao and Shaoyu Chen and Haoran Yin and Bo Jiang and Cheng Wang and Sixu Yan and Xinbang Zhang and Xiangyu Li and Ying Zhang and Qian Zhang and Xinggang Wang},
  journal={arXiv preprint arXiv:2411.15139},
  year={2026}
}
```
