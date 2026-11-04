Exploring Patch-Based Representation for Efficient Quantum Image Encoding

This repository contains the implementation of fixed and adaptive patch-based preprocessing strategies for Quantum Image Representation (QIR) using the Flexible Representation of Quantum Images (FRQI) framework.

The project investigates how image partitioning and different intensity-retention strategies influence image reconstruction quality and quantum-resource requirements.

Research Overview

Quantum Image Representation (QIR) encodes classical image information into quantum states. However, encoding complete images can require considerable quantum resources as image dimensions increase.

This project explores patch-based preprocessing as an approach to reducing the number of encoded image elements while retaining important image information.

The study compares conventional FRQI, fixed-size patching, and adaptive patch-based representations within a common FRQI framework.

Objectives

Investigate fixed-size and adaptive patching as preprocessing strategies for QIR.

Compare different patch sizes in terms of reconstruction quality and representation efficiency.

Explore content-based adaptive patch selection using variance, gradient, and entropy.

Evaluate different intensity-retention strategies within adaptive FRQI.

Analyze the trade-off between image reconstruction quality and quantum-resource requirements.

Methodology

The implementation is organized into three experimental stages.

1. Fixed and Adaptive Patching

Fixed patching is evaluated using:

2 × 2 patches

4 × 4 patches

8 × 8 patches

Adaptive patching uses three local image-complexity measures:

Variance: Measures intensity variation within a region.

Gradient: Identifies edges and local intensity transitions.

Entropy: Measures the information content of the intensity distribution.

Larger patches are assigned to relatively homogeneous regions, while smaller patches are used for regions with greater complexity.

2. FRQI-Based Quantum Representation

FRQI is used as the common quantum image encoding framework.

The following representations are investigated:

Conventional FRQI

Fixed-patch FRQI

Error-based Adaptive FRQI

Two-Value Adaptive FRQI

Multi-Value Adaptive FRQI

The adaptive representations retain different amounts of intensity information within each patch to study their effect on reconstruction quality and quantum resources.

3. Evaluation

The approaches are evaluated using the following metrics.

Image Reconstruction Metrics

Mean Squared Error (MSE)

Peak Signal-to-Noise Ratio (PSNR)

Structural Similarity Index Measure (SSIM)

Quantum Resource Metrics

Number of encoded elements

Qubit count

Gate count

Circuit depth

Dataset

The experiments use the MNIST handwritten digit dataset, consisting of grayscale images of handwritten digits from 0 to 9.

Original image dimensions: 28 × 28 pixels

Intensity range: 0–255

Evaluation subset: First 100 images from the test set

For classical patching experiments, images are resized to 32 × 32 pixels. For FRQI experiments, images are resized to 16 × 16 pixels.

Simulation Environment

The FRQI circuits are evaluated using Qiskit's statevector simulation through Statevector.from_instruction().

This approach computes the ideal quantum state without finite-shot measurement sampling. The reported quantum-resource results are obtained from the simulated circuits.

Note: The experiments use ideal statevector simulation and have not been evaluated on actual quantum hardware.

Repository Structure

Patch-Based-Quantum-Image-Representation/
│
├── README.md
├── requirements.txt
│
├── notebooks/
│   ├── conventional_frqi.ipynb
│   ├── fixed_patch_frqi.ipynb
│   ├── adaptive_variance.ipynb
│   ├── adaptive_gradient.ipynb
│   ├── adaptive_entropy.ipynb
│   ├── error_based_adaptive_frqi.ipynb
│   ├── two_value_adaptive_frqi.ipynb
│   └── multi_value_adaptive_frqi.ipynb
│
├── results/
│   ├── reconstruction/
│   ├── resource_comparison/
│   └── evaluation_metrics/
│
└── LICENSE

The filenames and folders can be adjusted to match the final uploaded files.

Key Findings

The experimental results demonstrate that:

Fixed patch sizes involve a trade-off between reconstruction quality and quantum resources.

Adaptive patching provides a balance between reconstruction quality and the number of encoded elements.

The error-based adaptive representation reduces gate count and circuit depth compared with conventional FRQI.

The two-value adaptive representation provides a balance between reconstruction quality and quantum-resource requirements.

The multi-value adaptive representation achieves the highest reconstruction quality among the investigated adaptive approaches, with increased quantum-resource requirements.
