<div align="center">

# XR Classroom

### A Real-World Dynamic Multi-View Classroom Dataset Captured with Heterogeneous RGB Cameras for 3D/4D Gaussian Splatting

Soo-Been Jo<sup>1</sup> · Yeongil Ryu<sup>1</sup> · Isaac Yang<sup>1</sup> · Reagan Koo<sup>1</sup> · Seung Huk Ahn<sup>1</sup> · Ye-Eun Yeom<sup>1</sup> · Eun-Seok Ryu<sup>1</sup>

<sup>1</sup>Intelligent Multimedia Computing Laboratory (IMCLab), Department of Immersive Media Engineering, Sungkyunkwan University

![Status](https://img.shields.io/badge/status-data%20upload%20in%20progress-yellow)
![Views](https://img.shields.io/badge/views-44-blue)
![Modality](https://img.shields.io/badge/modality-RGB-green)
![License](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey)

**Version:** October 2026 · **Source:** [Download Dataset](http://gofile.me/6uap5/0BDK8PYXa)

</div>

<!--
TEASER: uncomment after adding the file.
Recommended: a short looping GIF/MP4 of a 4DGS free-viewpoint render (camera orbiting while the lecturer moves), ~800 px wide, < 10 MB.

<p align="center">
  <img src="images/teaser.gif" width="90%" alt="XR Classroom teaser">
</p>
-->

---

## 📢 News

- **[2026.10]** Dataset documentation released. Data packages will be added in upcoming releases.
- **[2026.08]** XR Classroom was presented at the 2026 KACE Summer Conference (Korean Association of Computer Education).

---

## ✨ Highlights

- **Real-world lecture, not a studio:** An instructor and multiple learners moving at the same time in an actual classroom, with continuous mutual occlusions and a room-scale capture area.
- **Heterogeneous camera rig:** Ceiling-mounted Basler industrial cameras and eye-level Intel RealSense cameras with different resolutions, fields of view, and color responses.
- **44 synchronized surrounding views:** All cameras face the center of the classroom and surround it from all sides at two different heights.
- **Original and compatible versions:** The original heterogeneous videos, plus a version with all views unified to 1920 × 1080 for existing training pipelines.
- **Built for 3D/4D Gaussian Splatting:** Supports static 3DGS and dynamic 4DGS training, with a recommended held-out evaluation split for novel view synthesis.

---

## 🖼️ Visual Overview

### Capture Space
<p align="center"><img src="images/capture_space.jpg" width="85%" alt="Capture space"></p>
<p align="center"><em>The classroom used for capture, with Basler camera rigs fixed to the ceiling. Intel RealSense cameras were mounted on tripods at learners' eye level for each capture session (not shown).</em></p>

### Camera Layout
<p align="center"><img src="images/camera_layout_top.png" width="75%" alt="Camera layout (oblique view)"></p>
<p align="center"><img src="images/camera_layout_side.png" width="95%" alt="Camera layout (side view)"></p>
<p align="center"><em>Estimated camera poses of all 44 views. Top: oblique view of the cameras surrounding the classroom. Bottom: side view showing the ceiling-mounted and eye-level camera rows.</em></p>

### Capture Environment
<p align="center"><img src="images/capture_environment.png" width="90%" alt="Capture environment"></p>
<p align="center"><em>Reconstructed classroom point cloud with estimated camera poses.</em></p>

### Multi-View Samples
<p align="center"><img src="images/multiview_grid.png" width="95%" alt="Multi-view samples"></p>
<p align="center"><em>The same synchronized frame of Scenario 2 from all 44 views. The first 19 views (row-major order) are ceiling-mounted Basler cameras; the remaining 25 are eye-level RealSense cameras.</em></p>

### Reconstruction
<p align="center"><img src="images/render.png" width="80%" alt="Render result"></p>
<p align="center"><em>Free-viewpoint render of the lecture scene from a 3DGS model trained on all 44 views (qualitative result).</em></p>

---

## 🏫 Overview

**XR Classroom** is a multi-view dataset captured in a real classroom at Sungkyunkwan University. It provides synchronized dynamic sequences of two lecture scenarios, recorded simultaneously from 44 views of heterogeneous RGB cameras, for research on 3D/4D Gaussian Splatting, novel view synthesis, and volumetric video.

Widely used public multi-view datasets mostly capture a single object or a small space densely, and representative dynamic multi-view datasets use a single camera type in a forward-facing arrangement. XR Classroom instead surrounds a real lecture space from all sides with wide inter-view spacing and two camera types, while an instructor and multiple learners move at the same time.

The dataset contributes:
1. **Real classroom domain:** Dynamic lecture scenes for 3D/4D Gaussian training and evaluation.
2. **Simultaneously captured multi-view video:** A basis for volumetric video compression and streaming research.
3. **Heterogeneous camera configuration:** Unlike datasets with a unified camera type, resolution, and camera parameters, it supports research on pose estimation and reconstruction pipelines that are robust to heterogeneous conditions.

---

## 📷 Capture Setup

A total of 45 cameras were installed: 20 Basler and 25 RealSense. The dataset consists of **44 views**, excluding one Basler view (Basler view 08) that had a capture error.

| | Basler | Intel RealSense |
|---|---|---|
| Model | acA2500-60uc | L515 |
| Installed cameras | 20 | 25 |
| Views in dataset | 19 (1 erroneous view excluded) | 25 |
| Mounting | Fixed to the ceiling (rigs of 5 per wall) | Tripods (learners' eye level) |
| Camera servers | 4 | 5 |
| Resolution (original version) | 1952 × 1088 | 1920 × 1080 |
| Resolution (compatible version) | 1920 × 1080 | 1920 × 1080 |
| Frame rate | Up to 30 fps | Up to 30 fps |

- **Modality:** RGB only. Depth streams of the RealSense cameras and audio are not included.
- **Camera arrangement:** All cameras face the center of the lecture space, and their positions and orientations are fixed during capture.
- **Acquisition:** The cameras are distributed across 9 camera servers (5 cameras each) and captured simultaneously.
- **Synchronization:** Cameras of the same type are synchronized by our in-house software. Across the two camera types, frames are aligned afterward using the moment the room lights are switched off as a common event.

---

## 🎬 Lecture Scenarios

| Scenario | Description | Released frames |
|---|---|---|
| Scenario 1 | The instructor explains using a physical teaching aid (a robot), and learners watch and study it. | Coming soon |
| Scenario 2 | During the lecture, some learners engage in off-task activities (e.g., reading comics, using a smartphone) that are hard to notice from the instructor's frontal viewpoint. | 300 (10 s) |

<p align="center"><img src="images/scenarios.jpg" width="100%" alt="Scenario 1 and Scenario 2"></p>
<p align="center"><em>The same real captured view (cam06, Basler view 06) from each scenario, taken from frame 400 of the raw capture. Orange boxes mark off-task activities in Scenario 2 that are hard to notice from the instructor's viewpoint. Brightness adjusted and annotations added for visualization only.</em></p>

Each scenario was captured for about 20 seconds. The released sequence is the interval that is synchronized across all 44 views (10 seconds, 300 frames at 30 fps, for Scenario 2). The scenes include diverse body motions, such as raising a hand to ask a question, taking notes, observing a teaching aid, talking to a learner sitting behind, and lowering the head. They also contain:

- **Mutual occlusions** between the instructor and multiple learners
- **Two viewpoint heights and fields of view** from ceiling-mounted and eye-level cameras
- **View-dependent and high-frequency regions** such as reflections from indoor lighting, electronic screens, and detailed textures of teaching aids

---

## 📦 Dataset Availability

All packages are available in the [dataset folder](http://gofile.me/6uap5/0BDK8PYXa). Individual download links are listed below.

| Item | Description |
|---|---|
| Multi-view video | RGB videos from 44 views (original / compatible versions, no audio) |
| Camera parameters | Per-view intrinsic and extrinsic parameters estimated with COLMAP / VGGT |
| Supported training | Static-frame 3DGS and dynamic-sequence 4DGS |
| Evaluation split | Recommended held-out views (see below) |

Each scenario folder contains the packages below. Start with the single-frame package if your connection is slow. Large packages are split into parts so that each file can be downloaded separately.

| Package | Content | Scenario 1 | Scenario 2 |
|---|---|:---:|:---:|
| Single frame | One synchronized frame from all 44 views, with camera parameters | Coming soon | Coming soon |
| Compatible | Full sequence, all views at 1920 × 1080, with camera parameters | Coming soon | Coming soon |
| Original | Full sequence at native resolution, split by camera type | Coming soon | Coming soon |
| PLY | Trained 3DGS model (trained on all 44 views, not for NVS evaluation) | Coming soon | Coming soon |

The single frame is one instant of the dynamic sequence, so it can be used directly for static 3DGS training. Each scenario folder also includes `SHA256SUMS.txt` for verifying downloads (`sha256sum -c SHA256SUMS.txt --ignore-missing`).

```
XR-Classroom/
├── scenario_1/
│   ├── XRC_S1_single_frame.zip
│   ├── XRC_S1_compatible_part01.zip, ...
│   ├── XRC_S1_original_basler.zip
│   ├── XRC_S1_original_realsense.zip
│   ├── XRC_S1_3dgs.ply
│   └── SHA256SUMS.txt
└── scenario_2/
    └── ...
```

For questions or collaboration, please contact [josubin@skku.edu](mailto:josubin@skku.edu).

### Original and Compatible Versions

- **Original version:** The core of the dataset. It keeps the differences in resolution and camera parameters between camera types.
- **Compatible version:** All views are unified to 1920 × 1080 for existing dynamic-scene pipelines that assume the same input resolution. The Basler 1952 × 1088 frames are center-cropped by 16 pixels on the left and right and 4 pixels on the top and bottom. Cropping is applied **before** camera parameter estimation, so the provided parameters refer to the compatible version.

### Recommended Evaluation Split

For quantitative evaluation of novel view synthesis, the center view of each Basler wall rig is held out:

- **Held-out views:** `cam03`, `cam12`, `cam17` (Basler views 03, 13, and 18)
- **Training views:** All remaining 41 views

The fourth center view (Basler view 08) is excluded from the dataset because of a capture error. Under this protocol, the RGB frames of the held-out views must not be used for initial point generation, color correction, or model optimization; use them only to evaluate novel view synthesis after training.

### Camera Indexing

Views are stored as `cam01` to `cam44` in the Neural 3D Video (N3DV) layout, so the data can be loaded directly by N3DV-compatible 3D/4D Gaussian Splatting code. Basler and RealSense cameras were originally numbered separately; the mapping is provided in `cameras.csv` in each package.

| Folders | Camera type | Original view numbers |
|---|---|---|
| `cam01` – `cam19` | Basler (ceiling) | Basler views 01–07, 09–20 (view 08 excluded) |
| `cam20` – `cam44` | RealSense (eye level) | RealSense views 01–25 |

---

## 📄 Citation

If you use or refer to this dataset, please cite:

Soo-Been Jo, Yeongil Ryu, Isaac Yang, Reagan Koo, Seung Huk Ahn, Ye-Eun Yeom, Eun-Seok Ryu, "XR Classroom: A Multi-view Dataset for a 3D Neural Representation-Based Educational Platform," *Proceedings of the 58th KACE Summer Conference*, vol. 30, no. 2, Aug. 2026. (in Korean) [[PDF]](https://imclab.skku.edu/MCSL/wp-content/uploads/2026/09/XR-Classroom-3%EC%B0%A8%EC%9B%90-%EB%89%B4%EB%9F%B4-%EB%A6%AC%ED%94%84%EB%A0%88%EC%A0%A0%ED%85%8C%EC%9D%B4%EC%85%98-%EA%B8%B0%EB%B0%98-XR-%EA%B5%90%EC%9C%A1-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%9D%84-%EC%9C%84%ED%95%9C-%EB%A9%80%ED%8B%B0%EB%B7%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%85%8B.pdf)

```bibtex
@inproceedings{jo2026xrclassroom,
  author    = {Soo-Been Jo and Yeongil Ryu and Isaac Yang and Reagan Koo and Seung Huk Ahn and Ye-Eun Yeom and Eun-Seok Ryu},
  title     = {{XR Classroom}: A Multi-view Dataset for a {3D} Neural Representation-Based Educational Platform},
  booktitle = {Proceedings of the 2026 Summer Conference of the Korean Association of Computer Education (KACE)},
  volume    = {30},
  number    = {2},
  year      = {2026},
  month     = aug,
  note      = {in Korean}
}
```

<!-- TODO: add pages once the proceedings are indexed (KoreaScience / DBpia). -->

The capture system and the free-viewpoint rendering pipeline are described in:

Soo-Been Jo, Yeongil Ryu, Isaac Yang, Reagan Koo, Eun-Seok Ryu, "Development of XR Educational Platform by Using 3D Neural Representation," *Proceedings of the 58th KACE Summer Conference*, vol. 30, no. 2, Aug. 2026. (in Korean) [[PDF]](https://imclab.skku.edu/MCSL/wp-content/uploads/2026/09/3%EC%B0%A8%EC%9B%90-%EB%89%B4%EB%9F%B4-%EB%A6%AC%ED%94%84%EB%A0%88%EC%A0%A0%ED%85%8C%EC%9D%B4%EC%85%98-%EA%B8%B0%EC%88%A0%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%B0%A8%EC%84%B8%EB%8C%80-XR-%EA%B5%90%EC%9C%A1-%ED%94%8C%EB%9E%AB%ED%8F%BC.pdf)

---

## 📜 License

This dataset is released under the [Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).

- You may use, share, and adapt the dataset for **non-commercial research and educational purposes** without prior permission.
- Please **cite** the paper listed above when you use the dataset.
- The dataset was captured with the consent of all participants. Do not use it to identify, track, or profile the individuals who appear in it.

---

## 🙏 Acknowledgment

This work was supported by the National Research Foundation of Korea (NRF) grant funded by the Korea government (MSIT) in 2025 (No. RS-2024-00457605). This work was also supported by the Seoul Anchor Center, funded by the Ministry of Education and the Seoul Metropolitan Government in 2026, as part of the Regional Growth Talent Development System (ANCHOR) COSS (No. 2026-ANCHOR-01-113).

We thank our IMCLab members Yeong-Gyu Kim, Priyanka Muthukumaran, Uijoon Jeong, Yuchan Cho, Yeong Hun Jeong, and Inseo Jang for participating in the recorded lecture scenarios and for their help with the capture setup.

---

## 🔗 Contact & Related Links

- **Contact:** Soo-Been Jo ([josubin@skku.edu](mailto:josubin@skku.edu))
- **IMCLab, Sungkyunkwan University:** https://imclab.skku.edu/
- **Other IMCLab datasets:** VRrooms (IPIU 2025), [Library](https://github.com/reagan99/Library) (IEEE VR 2026 Workshops)
