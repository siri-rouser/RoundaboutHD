# RoundaboutHD

**RoundaboutHD** is a comprehensive, high-resolution multi-camera vehicle tracking (MCVT) dataset captured in a real-world roundabout scenario. It is designed to support the development and benchmarking of object detection, single-camera tracking (SCT), and multi-camera vehicle tracking (MCVT) algorithms in urban environments with nonlinear motion and frequent occlusions.

![RoundaboutHD Example](image.png)
---

## Dataset Description

RoundaboutHD provides **40 minutes of fully annotated video footage** recorded from **4 non-overlapping 4K cameras at 15 FPS**. Each camera covers 10 minutes of traffic under various conditions: normal, light, and heavy traffic. The roundabout layout introduces significant challenges such as:

- **Nonlinear vehicle trajectories**
- **Frequent occlusions** due to infrastructure (e.g., a central statue)
- **Multiple exits and intersections** between cameras

This makes RoundaboutHD a challenging yet realistic benchmark for evaluating vehicle tracking performance in smart city applications.



---

## Dataset Access

To request access to the dataset, please email your **full name** and **institutional affiliation** to:

**yl4300@bath.ac.uk**

The dataset is available for **non-commercial research purposes only**. It will also be published through the **University of Bath Research Data Archive** in the near future.

---

## Dataset Contents

The dataset includes:

- **Labeled video footage**
- **Object detection results**
- **Single-camera tracking (SCT) results**
- **Multi-camera tracking (MCVT) results**
- **Evaluation scripts and label format documentation**

---

## Evaluation

We provide tools for evaluating tracking performance in this repository:  
[Multi-Camera Tracking Labelling Tool](https://github.com/siri-rouser/multi_camera_tracking_labelling_tool.git)

### Multi-Camera Tracking Evaluation

Use the following command:

```bash
python eval_label.py <prediction_file> <ground_truth_file>
```

Each line in the prediction/ground-truth file should follow this format:

```
<camera_id> <obj_id> <frame_id> <xmin> <ymin> <width> <height> <xworld> <yworld>
```

**Descriptions:**

- `camera_id`: Integer identifier (1–4 in RoundaboutHD)
- `obj_id`: Object ID (positive integer, consistent across cameras)
- `frame_id`: Frame number (starting at 1)
- `xmin`, `ymin`, `width`, `height`: Bounding box coordinates (pixels)
- `xworld`, `yworld`: GPS/world coordinates of the object (optional)

> *Note: `xworld` and `yworld` are not required for evaluation, but including them is recommended for future extensions.*

---

### Single-Camera Tracking Evaluation

Use the following command:

```bash
python eval_sct.py <prediction_directory> <ground_truth_directory>
```

Each directory should contain multiple `.txt` files named by frame:

```
img000001.txt, img000002.txt, ...
```

Each file must contain object detections in the format:

```
<class_id> <xmin> <ymin> <xmax> <ymax>
```

---

## Citation

If you use **RoundaboutHD** in your research, please cite the following:

> **Yuqiang Lin**, **Li Gan**, **Mingxuan Sui**, and **Nick Hawes**  
> *RoundaboutHD: A High-Resolution Benchmark Dataset for Real-World Multi-Camera Vehicle Tracking*  
> arXiv preprint arXiv:XXXX.XXXXX, 2025.  
> [URL to be updated after arXiv submission]

---

## Contact

For questions or collaboration inquiries, feel free to reach out:  
**yl4300@bath.ac.uk**

