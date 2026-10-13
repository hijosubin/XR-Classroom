<div align="center">

# XR Classroom

### A Real-World Dynamic Multi-View Classroom Dataset Captured with Heterogeneous RGB Cameras for 3D/4D Gaussian Splatting

[**Soo-Been Jo**](mailto:josubin@skku.edu)<sup>1</sup> · Yeongil Ryu<sup>1</sup> · Isaac Yang<sup>1</sup> · Reagan Koo<sup>1</sup> · Seung Huk Ahn<sup>1</sup> · Ye-Eun Yeom<sup>1</sup> · [**Eun-Seok Ryu**](https://imclab.skku.edu/)<sup>1</sup>

<sup>1</sup>Intelligent Multimedia Computing Laboratory (IMCLab), Department of Immersive Media Engineering, Sungkyunkwan University

![Status](https://img.shields.io/badge/status-documentation%20preview-orange)
![Views](https://img.shields.io/badge/views-up%20to%2044-blue)
![Modality](https://img.shields.io/badge/modality-RGB-green)
![License](https://img.shields.io/badge/license-TBA-lightgrey)

</div>

<!--
TEASER — uncomment after adding the file.
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

- **Real-world lecture, not a studio** — human motion during an actual classroom lecture, with furniture, occlusions, and a room-scale capture area.
- **Heterogeneous camera rig** — ceiling-mounted Basler industrial cameras and floor-level Intel RealSense cameras with different sensors, color responses, and resolutions.
- **Dense surrounding views** — up to 44 synchronized RGB views per scenario, covering the classroom from multiple heights and directions.
- **Built for 3D/4D Gaussian Splatting** — suited for dynamic reconstruction, free-viewpoint / novel-view synthesis, and cross-view appearance-consistency research.

---

## 🖼️ Visual Overview

### Capture Space
<p align="center"><img src="images/capture_space.jpg" width="85%" alt="Capture space"></p>
<p align="center"><em>The classroom used for capture, with ceiling-mounted Basler cameras installed on rails. Floor-level Intel RealSense cameras were mounted on tripods for each capture session (not shown).</em></p>

### Camera Layout
<p align="center"><img src="images/camera_layout_top.png" width="75%" alt="Camera layout (oblique view)"></p>
<p align="center"><img src="images/camera_layout_side.png" width="95%" alt="Camera layout (side view)"></p>
<p align="center"><em>Estimated camera poses of all views. Top: oblique view of the cameras surrounding the classroom. Bottom: side view showing the ceiling-mounted and floor-level camera rows.</em></p>

### Capture Environment
<p align="center"><img src="images/capture_environment.png" width="90%" alt="Capture environment"></p>
<p align="center"><em>Reconstructed classroom point cloud with estimated camera poses.</em></p>

### Multi-View Samples
<p align="center"><img src="images/multiview_grid.png" width="95%" alt="Multi-view samples"></p>
<p align="center"><em>Synchronized frames from all 44 views at the same timestamp. The first 19 views (row-major order) are ceiling-mounted Basler cameras; the remaining 25 are floor-level RealSense cameras.</em></p>

### Reconstruction
<p align="center"><img src="images/render.png" width="80%" alt="Render result"></p>
<p align="center"><em>Gaussian Splatting render of the lecture scene.</em></p>

---

## 🏫 Overview

**XR Classroom** is a real-world dynamic multi-view dataset captured during actual classroom lecture activity. It provides synchronized multi-view RGB sequences for evaluating multi-view reconstruction, free-viewpoint / novel-view synthesis, and 3D/4D Gaussian Splatting.

Many dynamic multi-view datasets are recorded in controlled studios with uniform backgrounds. XR Classroom instead captures a real lecture space with a **heterogeneous camera system**, so the views differ not only in position but also in sensor characteristics. This makes the dataset suitable for studying how reconstruction methods behave under practical, imperfect multi-view capture conditions — including cross-camera color and appearance inconsistency.

---

## 📷 Capture Setup

| Camera System | Model | Mounting | # Views | Image Resolution |
|---|---|---|:---:|:---:|
| Basler | acA2500-60uc | Ceiling-mounted | 19 | 1952 × 1088 |
| Intel RealSense | L515 | Floor-level | 25 | 1920 × 1080 |
| **Total** | | | **up to 44** | |

| Property | Description |
|---|---|
| Modality | RGB only (depth streams of the RealSense cameras are not included) |
| Frame Rate | TBA |
| Sequence Length | TBA |
| Synchronization | TBA |
| Camera Parameters | TBA |
| Environment | Indoor classroom, real lecture activity |

> The usable view count can differ across scenarios. Per-scenario view lists are provided in the metadata of each release.

---

## 📦 Dataset Availability

The image sequences are large and are distributed separately from this repository. Download links will be added here when each package is ready.

| Package | Description | # Views | Frames | Size | Download |
|---|---|:---:|:---:|:---:|:---:|
| TBA | | | | | Coming soon |

For early access or collaboration, please contact [josubin@skku.edu](mailto:josubin@skku.edu).

<!--
Planned directory structure — fill in once the release format is fixed.

```
XR-Classroom/
├── scenario_01/
│   ├── images/
│   │   ├── cam_00/  000000.png  000001.png  ...
│   │   └── ...
│   ├── cameras/              # intrinsics & extrinsics
│   └── metadata.json         # view list, camera types, sync info
└── scenario_02/
    └── ...
```
-->

---

## 🎬 Scene Characteristics

- **Heterogeneous sensors:** two camera families with different color responses and resolutions
- **Multi-height viewpoints:** ceiling-mounted and floor-level cameras surrounding the classroom
- **Real-world dynamics:** human motion during an actual lecture, not a staged studio capture
- **Indoor complexity:** furniture, occlusions, and a wide room-scale capture area
- **Cross-view inconsistency:** suitable for evaluating color correction and appearance-consistency methods

---

## 📄 Citation

If you use or refer to this dataset, please cite:

Soo-Been Jo, Yeongil Ryu, Isaac Yang, Reagan Koo, Seung Huk Ahn, Ye-Eun Yeom, Eun-Seok Ryu, "XR Classroom: A Multi-View Dataset for a 3D Neural Representation-based XR Education Platform," *2026 KACE Summer Conference (Korean Association of Computer Education)*, Aug. 2026. (in Korean)

```bibtex
@inproceedings{jo2026xrclassroom,
  author    = {Soo-Been Jo and Yeongil Ryu and Isaac Yang and Reagan Koo and Seung Huk Ahn and Ye-Eun Yeom and Eun-Seok Ryu},
  title     = {{XR Classroom}: A Multi-View Dataset for a {3D} Neural Representation-based {XR} Education Platform},
  booktitle = {Proceedings of the 2026 Summer Conference of the Korean Association of Computer Education (KACE)},
  year      = {2026},
  note      = {in Korean}
}
```

<!-- TODO: add volume/number/pages once the proceedings are published (KoreaScience / DBpia). -->

---

## 📜 License

Dataset usage terms will be stated with the release package. Until then, please contact the maintainer before using or redistributing any data.

<!--
Privacy & consent — confirm before publishing images that show people:
All individuals appearing in the dataset participated with informed consent.
-->

---

## 🙏 Acknowledgment

This dataset was produced as part of the project *"Development of XR Educational Platform by using 3D Neural Representation."*
<!-- TODO: funding statement (agency, program, grant number) — confirm wording with advisor. -->

We thank our IMCLab members Yeong-Gyu Kim, Priyanka Muthukumaran, Uijoon Jeong, Yuchan Cho, Yeong Hun Jeong, and Inseo Jang for participating in the recorded lecture scenarios and for their help with the capture setup.

---

## 🔗 Contact & Related Links

- **Contact:** Soo-Been Jo ([josubin@skku.edu](mailto:josubin@skku.edu))
- **IMCLab, Sungkyunkwan University:** https://imclab.skku.edu/
