<div align="center">
<h1>AdaDiffDrive</h1>
<h3>Multi-Modal Adaptive Diffusion-Based Trajectory Planning for End-to-End Autonomous Driving</h3>
 
  Yingqiang Zhong. (2026).<sup>1,2</sup> 
  
 <sup>1</sup> Institute of Artificial Intelligence, HUST, <sup>2</sup> School of EIC, HUST
 
 AdaDiffDrive_code. Zenodo. https://doi.org/10.5281/zenodo.20626700


</div>

## Abstract
Generating safe, diverse and even human-like trajectories in complex traffic environments is a major challenge for end-to-end autonomous driving (E2E-AD). Diffusion-based planners have recently gained popularity as a promising solution owing to their ability to approximate the high-dimensional and multi-modal action distribution. Unfortunately, existing standard diffusion planners need to iteratively denoise from noisy samples, with a high cost, whereas the existing truncated diffusion planners are usually defined via an existing fixed static anchor, which may not fit highly dynamic or long-tail driving situations. To overcome these issues, we present AdaDiffDrive, an adaptive truncated diffusion planner that substitutes the existing static statistical prior with scene-aware dynamic priors. AdaDiffDrive consists of three key components. First, a Multi-modal Sparse Fusion Transformer (MSFT) compresses camera and LiDAR observations into compact sparse scene tokens, aligning perception sparsity with planning intent. Second, these tokens are used to generate $K$ scene-adaptive anchors and construct an adaptive anchored gaussian distribution (AAGD), which provides context-aware trajectory priors while preserving multi-modal diversity. Third, a cascaded diffusion decoder equipped with adaptive truncated cross-attention selectively associates noisy trajectory points with nearby safety-critical sparse tokens, providing localized scene guidance during the denoising process. By coupling sparse scene encoding with adaptive truncated diffusion, AdaDiffDrive mitigates the trade-off between trajectory diversity, generation quality, and planning efficiency. Experiments on the NAVSIM planning benchmark show that AdaDiffDrive achieves 84.7 PDMS. Additional evaluation on nuScenes further demonstrates competitive trajectory accuracy, collision avoidance performance, and near real-time inference. These results indicate that adaptive scene-aware priors and sparse safety-guided diffusion decoding can improve the robustness and safety of E2E-AD trajectory planning.
</div>


