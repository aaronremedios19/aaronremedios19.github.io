---
layout: essay
type: essay
title: Combining MNE and Magic SLAM
# All dates must be YYYY-MM-DD format!
date: 2025-08-26 - current
labels:
  - Nvidia Issac Sim
  - Motion Planning
  - SLAM
  - Multi agent Systems
---

<img class="research-hero" src="{{ site.baseurl }}/images/slam2.jpeg" alt="">



In this project, I conducted a research-focused study on multi-agent SLAM representations, analyzing the strengths and limitations of neural implicit maps and explicit Gaussian scene representations using recent systems such as MNE-SLAM and MAGiC-SLAM. Rather than modifying MNE-SLAM’s neural training pipeline, I instantiated Gaussian submaps externally as an explicit geometric backend to evaluate and analyze multi-agent behavior. This allowed me to inspect global consistency across agents, visualize loop-closure effects, and quantitatively assess map quality using rendering-based metrics such as PSNR, SSIM, LPIPS, and depth error—capabilities that are otherwise expensive or impractical with purely neural implicit fields.

I adopted MAGiC-SLAM’s submap fusion concept as a reference mechanism, including its coarse-to-refined merging strategy and the use of rigid SE(3) corrections applied directly to map elements. While this fusion was not integrated into MNE-SLAM’s learning loop, it served as a drop-in geometric backend to study how loop closures affect global map quality when corrections are applied at the representation level. This approach enabled direct measurement of improvements in rendering quality, depth accuracy, and merge time, which neural-only pipelines cannot easily expose without full neural re-optimization.

A key outcome of this study was an explicit empirical comparison between rigid geometric correction and neural implicit correction. The results showed that applying rigid transformations to Gaussian submaps after loop closure led to immediate global map improvement, without retraining or distillation. This supports the central insight of the project: explicit Gaussian representations are better suited for post-hoc global correction and evaluation, while neural implicit maps excel at distributed learning and communication efficiency. Overall, this work represents a methodological transfer and comparative analysis, providing practical insights into how hybrid SLAM systems can leverage the strengths of both representations for scalable, multi-agent mapping.

