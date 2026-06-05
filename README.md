<div align="center">

# 🚀 AIO-CV Flow Studio

[![Release](https://img.shields.io/badge/Release-v0.1.0-blue?style=for-the-badge&logo=github)](https://drive.google.com/drive/u/1/folders/1gsD-AgMVZtpA6H2kSHZNG493J93m9f1Z)
[![Platform Linux](https://img.shields.io/badge/Platform-Linux%20%2F%20Debian-orange?style=for-the-badge&logo=linux)](https://drive.google.com/drive/u/1/folders/1gsD-AgMVZtpA6H2kSHZNG493J93m9f1Z)
[![Engine](https://img.shields.io/badge/Engine-FastAPI%20%2B%20OpenCV-green?style=for-the-badge&logo=fastapi)](https://github.com)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](https://github.com)

**Industrial-grade real-time computer vision and metrology desktop application.**

[📥 Download deb Package](https://drive.google.com/drive/u/1/folders/1gsD-AgMVZtpA6H2kSHZNG493J93m9f1Z) | [📖 Wiki / Docs](https://github.com) | [🐛 Report Bug](https://github.com)

</div>

---

> [!NOTE]
> **AIO-CV Flow Studio** combines a fluid, drag-and-drop node-based graph editor with a supercharged sidecar running OpenCV, PyTorch, and geometric analysis engines.

---

## 💾 Installation & Setup

### 1. Download App
* 📥 **[Download the AIO-CV Flow Studio .deb installer](https://drive.google.com/drive/u/1/folders/1gsD-AgMVZtpA6H2kSHZNG493J93m9f1Z)**

### 2. Install Package (Debian / Ubuntu / Mint)
In your terminal, navigate to the folder where the `.deb` file was saved and run:
```bash
sudo dpkg -i AIO-CV_0.1.0_amd64.deb
```

> [!TIP]
> If there are any unresolved APT package requirements during installation, resolve them automatically with:
> ```bash
> sudo apt-get install -f
> ```

---

## ⚙️ System Requirements & Dependencies

> [!IMPORTANT]
> AIO-CV requires hardware-accelerated OpenGL and GLib thread control libraries to carry out real-time high-FPS frames streaming.

<details>
<summary><b>🔍 View Manual Package Installation Command for your Distro</b></summary>

Choose your Linux package manager:

#### 🔹 Debian / Ubuntu / Linux Mint
```bash
sudo apt-get update
sudo apt-get install -y libgl1 libglib2.0-0
```

#### 🔹 Fedora / Red Hat / CentOS
```bash
sudo dnf install -y mesa-libGL glib2
```

#### 🔹 Arch Linux / Manjaro
```bash
sudo pacman -Syu --noconfirm mesa libglvnd glib2
```
</details>

---

## 🔧 Automatic System Dependency Checker

> [!TIP]
> **No manual configuration is required!** On startup, AIO-CV Flow Studio automatically scans your host for crucial shared objects (like `libGL.so.1` and `libgthread-2.0.so.0`). If missing, it invokes a secure GUI agent (`pkexec`) to automatically install the required libraries using your native package manager.

---

## ⌨️ Canvas Navigation & Global Shortcuts

| Action | Shortcut / Control |
| :--- | :--- |
| **Undo Action** | `Ctrl + Z` |
| **Redo Action** | `Ctrl + Y` or `Ctrl + Shift + Z` |
| **Delete Node/Edge** | `Delete` or `Backspace` |
| **Pan Canvas** | Hold `Space` + Drag Mouse, or Left-Click & Drag background |
| **Zoom In / Out** | Mouse Wheel Scroll |
| **Select Node / Edge** | Left-Click |
| **Multi-Select** | Hold `Shift` + Drag Selection Box |

---

## 🛠️ Core Visual Nodes & Functions

Build vision graphs using the following industrial-grade processing nodes:

<details>
<summary><b>📷 1. Camera & Image Sources</b></summary>

* **Camera Source**: Connects to physical camera devices (webcams, USB cameras, industrial cameras).
  * `Camera Index`: Selects the system index (`Camera 0`, `Camera 1`, etc.).
  * `Target FPS`: Set acquisition speed (`30 FPS`, `60 FPS`, `120 FPS`).
* **Image Source**: Loads static reference images or template patterns for inspection matching.
</details>

<details>
<summary><b>🎨 2. Pre-Processing & Filters</b></summary>

* **Grayscale**: Converts raw BGR color images to high-contrast single-channel grayscale, optimizing them for processing speed.
* **Binarize (Threshold)**: Segment objects of interest by turning the image into black and white. Supports manual sliders for custom thresholds.
* **Morphology Ops**: Refines mask shapes using mathematical operations. Supports `Erosion`, `Dilation`, `Opening`, and `Closing` with `Rectangle`, `Ellipse`, and `Cross` kernels.
</details>

<details>
<summary><b>📐 3. Edge Detection & Metrology</b></summary>

* **Canny Edge**: Multi-stage mathematical edge detector with adjustable `Min/Max Threshold` sliders.
* **Caliper Tool**: Measures sub-pixel physical distances or dimensional profiles between detected edges.
  * `Direction`: Horizontal or Vertical profiling.
  * `Line Position`: Relative percentage offset on the image.
  * `Edge Threshold`: Sensitivity for edge detection.
</details>

<details>
<summary><b>📏 4. Calibration & Outputs</b></summary>

* **Calibration (px ➔ mm)**: Maps pixel measurements directly to real-world units.
  * `Calibration Ratio`: Maps unit per pixel (e.g. `0.06`).
  * `Physical Unit`: Outputs in `millimeters (mm)`, `centimeters (cm)`, or `inches (in)`.
* **Live Output**: Renders final processed image matrices with measurement annotations in real-time.
</details>
