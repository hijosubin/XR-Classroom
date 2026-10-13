# XR Classroom

> **A Real-World Dynamic Multi-View Classroom Dataset Captured with Heterogeneous RGB Cameras for 3D/4D Gaussian Splatting**

**Institution:** Sungkyunkwan University (SKKU)\
**Captured by:** IMCLab & Department of Immersive Media Engineering\
**Version:** October 2026\
**Contact:** Soo-Been Jo (josubin@skku.edu)

XR Classroom is a real-world classroom capture dataset intended for research on multi-view reconstruction, novel-view synthesis, and 3D/4D Gaussian Splatting. It contains dynamic classroom activity recorded with heterogeneous RGB camera systems.

## Dataset at a glance

- **Scene:** Real-world classroom lecture and activity
- **Capture:** Heterogeneous multi-view RGB cameras
- **Views:** Up to 44 camera views per scenario; the available view count varies by scenario
- **Intended research:** Multi-view reconstruction, 3D/4D Gaussian Splatting, and view synthesis

## Capture setup

The first XR Classroom session used ceiling-mounted Basler cameras and floor-level Intel RealSense cameras.

| Camera system | Model | Views in Session 1 | Image resolution |
| --- | --- | ---: | --- |
| Basler RGB cameras | acA2500-60uc | 19 | 1952 × 1088 |
| Intel RealSense RGB cameras | L515 | 25 | 1920 × 1080 |

The usable view count can differ across scenarios. Please check the per-scenario metadata distributed with each release.

## Data and access

The dataset files are distributed separately from this GitHub repository because the image sequences are large. The download link and package details will be added here when the release package is ready.

This repository currently provides dataset documentation. It does not contain the image sequences.

## Citation

Citation information will be added when the associated dataset publication is available.

## License

Dataset usage terms will be stated with the release package. Until then, please contact the dataset maintainers before redistributing any data.

## Related links

- [Intelligent Multimedia Computing Laboratory, SKKU](https://imclab.skku.edu/)
