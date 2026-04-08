<div align="center">

# UMSBench-v1: A Real-Synthetic Composited Multimodal Benchmark Dataset for Underground Mine Safety
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Dataset](https://img.shields.io/badge/Dataset-Release-green.svg)](#-dataset-download)
[![Status](https://img.shields.io/badge/Status-Under%20Review%20@%20ACM%20MM%202026-blue.svg)](#)
<!-- [![Paper](https://img.shields.io/badge/Paper-Arxiv-red.svg)](#) -->
**Feiteng Han**<sup>1*</sup> &nbsp; **Ming Xue**<sup>2*</sup> &nbsp; **Kaiyu Li**<sup>1</sup> &nbsp; **Tao Feng**<sup>2</sup> &nbsp; **Wei Shen**<sup>1</sup> <br>
**Hui Wang**<sup>1</sup> &nbsp; **Yudong Fang**<sup>2†</sup> &nbsp; **Yu Wang**<sup>1†</sup> &nbsp; **Xuecheng Tan**<sup>3</sup>

<sup>1</sup>*School of Information Technology, Beijing City University* <sup>2</sup>*Big Data Center, Ministry of Emergency Management* <sup>3</sup>*School of Software, Tsinghua University*

<sup>†</sup> Corresponding author &nbsp;&nbsp; <sup>*</sup> Equal contribution

`{hanfeiteng, kaiyuli, shen_0711, bcuwhui, wangyu}@bcu.edu.cn` <br>
`research.xue@gmail.com` | `ifengtaoi@outlook.com` <br>
`fangyudong9713@ustc.edu` | `tanxuecheng@tsinghua.edu.cn`

</div>

## 📑 Table of Contents

- [🔥 News](#-news)
- [✨ Highlights](#-highlights)
- [📖 Abstract](#-abstract)
- [🖼️ Dataset Overview & I2T2I Examples](#%EF%B8%8F-dataset-overview--i2t2i-examples)
- [📥 Dataset Download](#-dataset-download)
  - [1. Samples Subset (Publicly Available)](#1-samples-subset-publicly-available)
  - [2. Full Dataset Access Agreement](#2-full-dataset-access-agreement)
- [🙏 Acknowledgments](#-acknowledgments)
<!-- - [📝 Citation](#-citation) -->
<a id="news"></a>

## 🔥 News
* **[2026-04-02]** 📝 Our paper "UMSBench-v1" has been submitted to **ACM Multimedia (ACM MM) 2026** and is currently under review!
* **[2026-02-22]** 🚧 UMSBench project initialized. We successfully constructed 40k QA pairs covering 30+ underground mining site types.

<a id="highlights"></a>
## ✨ Highlights

| Feature | Description |
| :--- | :--- |
| 🥇 **First Mining VQA Benchmark** | The first multimodal dataset for underground mining safety. Contains **10k** real-synthetic images and **40k** QA pairs across **30+** site types, evaluating 4 cognitive levels: Scene, Object, Summarization, and Safety Reasoning. |
| 🔄 **Novel I2T2I Generation** | Introduces a physics-grounded **Image-to-Text-to-Image** pipeline, validated by an expert-in-the-loop mechanism, to successfully synthesize rare and long-tail safety risks. |
| ⚖️ **Standardized Evaluation** | Tasks are formalized as **Single-Choice Questions (SCQs)**. Features a robust dual-answer protocol combining heterogeneous machine-consensus voting with human-calibrated expert ground truth. |
| 🚀 **Proven Synthetic-to-Real Transfer** | Benchmarked on **14 SOTA VLMs**. Fine-tuning lightweight models (≤9B parameters) on our synthetic subset yields substantial real-world gains (e.g., up to **+25.38%** for GLM-4.6V-Flash). |

---

## 📖 Abstract
To fill the gap in benchmark datasets for vision-language models (VLM) research on underground mining safety analysis, we introduce **UMSBench-v1.0**. As the first multimodal VQA benchmark dataset and the first real-synthetic image dataset on mining safety, it consists of **10k real-synthetic underground images** and **40k question-answer pairs**, covering safety reasoning, captioning, understanding, and perception across 30 underground mining site types. 

The synthetic data is generated via a newly proposed **Image-to-Text-to-Image (I2T2I)** mechanism based on refined LLM-driven captioning capabilities, prompt engineering, and visual content generation models. Furthermore, benchmarking tasks are reformulated as Single-Choice Questions (SCQs) to achieve higher flexibility, scalability, and efficiency. State-of-the-art VLMs are benchmarked and fine-tuned to demonstrate the dataset’s effectiveness and potential applications. The dataset is officially released at [BCU-AILAB/UMSBench](https://github.com/BCU-AILAB/UMSBench).

---

## 🖼️ Dataset Overview & I2T2I Generation Pipeline

To overcome the long-tail issue of rare yet safety-critical underground events, we propose a novel two-stage **Image-to-Text-to-Image (I2T2I)** pipeline. This mechanism ensures our synthetic dataset is both physically plausible and highly relevant to mining safety.

### Stage 1: Image-to-Text (I2T) - Grounded Description
In the first stage, we leverage MLLMs (e.g., Gemini 3 Pro) to generate accurate, grounded descriptions of real mine scenes. Since real images often lack severe hazards, these descriptions primarily capture routine underground environments.

| Real Image | Grounded Description (Generated via I2T) |
| :---: | :--- |
| <img src="assets/real_belt.jpg" width="300"/> | **Description:** A routine underground coal mine tunnel. A heavy-duty conveyor belt is transporting coal in the center. The tunnel walls are supported by metal beams, and thick cables run along the right roof. The lighting is dim but sufficient for navigation. No obvious hazards are observed. |
| <img src="assets/real_tunnel.jpg" width="300"/> | **Description:** An underground excavation work area. A roadheader machine is positioned at the rock face. The ground is slightly damp, and ventilation pipes are hung on the upper left. The scene is static with no active operations or personnel present. |

### Stage 2: Text-to-Image (T2I) - Physics-grounded Synthesis
In the second stage, we use LLMs (e.g., ChatGPT) to inject logical "Location + Risk" combinations into the grounded descriptions, creating enriched prompts. These prompts guide visual generation models (e.g., Wan2.6-T2I) to synthesize high-risk, long-tail scenarios that maintain physical constraints, validated by an expert-in-the-loop mechanism.

| Enriched Prompt (Generated via I2T) | Synthetic Image (Generated via T2I) |
| :--- | :---: |
| **Prompt:** *Intersection (long-range camera at the end of the corridor facing the passage and equipment side, inner side of the corner): the frame covers the inner corner area and adjacent equipment zones, where a fire extinguisher, belt conveyor, motor, and warning sign are visible; the scene is accompanied by insufficient lighting and similar conditions; the belt conveyor is close to a poorly lit area, where the dim floor lighting creates irregular reflections; the fan is also near a poorly lit area, where the dim floor lighting creates irregular reflections. Attention should be paid to passage clearance and sign visibility, equipment guarding and line fixation with moisture protection, and the placement and accessibility of firefighting equipment, so as to prevent mechanical injury risks from rotating parts and risks of accidental entry and collision caused by poor visibility, ensuring safe production. Underground surveillance image, fixed camera position, real security-monitoring perspective, no text, no watermark.* | <img src="picture/893.png" width="100%"/> |
| **Prompt:** *Underground substation (high-mounted fixed corner camera overlooking the passage, beside the cable trench): the frame covers the area beside the cable trench and adjacent equipment zones, where warning signs, pipes, a fan, and valves are visible; the scene is accompanied by dust, water stains, and similar conditions; overhead valves span across the walkway, with some hanging down close to the damp floor. Attention should be paid to passage clearance and sign visibility, equipment guarding and line fixation with moisture protection, and the placement and accessibility of firefighting equipment, so as to prevent fire risks caused by dust accumulation and friction, as well as blocked passage, tripping, and collision risks, ensuring safe production. Underground surveillance image, fixed camera position, real security-monitoring perspective, no text, no watermark.* | <img src="picture/411.png" width="100%"/> |
| **Prompt:** *Underground power distribution room (high-mounted fixed corner camera overlooking the passage, corner maintenance area): the frame covers the corner maintenance area and adjacent equipment zones, where a control cabinet, fan, electrical cabinet, and cables are visible; the scene is accompanied by standing water, dust, and stacked items; the fire extinguisher is located at the edge of the doorway area, but access is partially blocked by surrounding dust. Attention should be paid to passage clearance and sign visibility, equipment guarding and line fixation with moisture protection, and the placement and accessibility of firefighting equipment, so as to prevent electric shock, short circuits, and electrical fire risks, slipping and electrical moisture exposure caused by wet standing water, and fire risks caused by dust accumulation and friction, ensuring safe production. Underground surveillance image, fixed camera position, real security-monitoring perspective, no text, no watermark.* | <img src="picture/794.png" width="100%"/> |
| **Prompt:** *Roadway/work area (high-mounted sidewall camera looking obliquely downward over the equipment area, beside the equipment): the frame covers the area beside the equipment and adjacent equipment zones, where a motor, guardrails, debris, and warning signs are visible; the scene is accompanied by reflections, dampness, and dim lighting; warning signs are placed beside the columns, but their visibility is affected by the darkness. Attention should be paid to passage clearance and sign visibility, equipment guarding and line fixation with moisture protection, and the placement and accessibility of firefighting equipment, so as to prevent slipping and electrical moisture exposure caused by damp standing water, blocked passage, tripping and collision risks, and accidental entry and collision caused by poor visibility, ensuring safe production. Underground surveillance image, fixed camera position, real security-monitoring perspective, no text, no watermark.* | <img src="picture/777.png" width="100%"/> |
| **Prompt:** *Inclined roadway (ceiling-mounted fixed camera looking downward over the work area, beside the handrail guardrail): the frame covers the area beside the handrail guardrail and adjacent equipment zones, where warning signs, cables, gravel, and guardrails are visible; the scene is accompanied by muddy water, reflections, clutter, and similar conditions; overhead guardrails span across the doorway area, with some hanging down near the cable trench. Attention should be paid to passage clearance and sign visibility, equipment guarding and line fixation with moisture protection, and the placement and accessibility of firefighting equipment, so as to prevent electric shock, short circuits, and electrical fire risks, fire risks caused by dust accumulation and friction, and accidental entry and collision caused by poor visibility, ensuring safe production. Underground surveillance image, fixed camera position, real security-monitoring perspective, no text, no watermark.* | <img src="picture/76.png" width="100%"/> |

> **Note for Users:** The above prompts are representative examples used during the synthesis phase. The full dataset includes diverse prompts covering 30+ site types.
---

## 📥 Dataset Download

### 1. Samples Subset (Publicly Available)
The data provided via the links below represents a **samples subset** of the complete dataset, intended for demonstration and initial exploration purposes. This subset contains two folders: `synthetic` and `real`.

* ☁️ **[Baidu Drive](https://pan.baidu.com/s/12nWnD3LAW3wsHNyktlrnLA?pwd=yed1)(Available)**
* ☁️ **[Google Drive](https://drive.google.com/file/d/1_5tVtb7M6QQ5XnCT63zenG1SUnPOXSdj/view?usp=sharing)(Available)**

### 2. Full Dataset Access Agreement
Due to the domain-specific and sensitive nature of underground mining safety data, the full **UMSBench-v1.0** dataset is available strictly for **non-commercial, academic research purposes**. To access the full dataset, please follow these steps:

1. Download the [Dataset Access Agreement Form (PDF)](/UMSBench-v1%20Dataset%20Access%20Agreement.pdf) *
2. Carefully read the terms. The form must be completely filled out and **hand-signed by a full-time faculty member or legal representative** (e.g., Professor, PI, or Lab Director) of your institution.
3. Send the scanned, signed copy of the agreement using your **official institutional email address** to: 
   📧 `hanfeiteng@bcu.edu.cn`.
   * **Email Subject Format:** `[UMSBench Full Dataset Application] - {Your Institution} - {Your Name}`
4. Upon approval (usually within 3-5 business days), we will reply with the download links and decryption passwords for the full dataset.

> **⚠️ Important:** Applications sent from personal email addresses (e.g., @gmail.com, @qq.com, @163.com) or lacking a proper authorized signature will **NOT** be processed.

---

## 🙏 Acknowledgments
This work was supported by the **National Key Research and Development Program of China** (2024YFC3015605, 2024YFC3015505). 

We appreciate Xihong Lin, Yijie Li, Runquan Shen, Zimeng Xin, Boyu Gao, Xinze He, Zitong Hui, Tianfei Xin, and Yuyan Wang at BCU for their hard work in data processing. We also appreciate the authors of previous SOTA works for their open-source codes, models, and datasets, and the anonymous reviewers for their helpful feedback.

---

<!-- ## 📝 Citation
If you find our dataset or paper useful in your research, please consider citing our work:

```bibtex
@inproceedings{han2024umsbench,
  title={UMSBench-v1: A Real-Synthetic Composited Multimodal Benchmark Dataset for Underground Mine Safety},
  author={Han, Feiteng and Xue, Ming and Li, Kaiyu and Feng, Tao and Shen, Wei and Wang, Hui and Fang, Yudong and Wang, Yu and Tan, Xuecheng},
  booktitle={Under Review}, 
  year={2024}
} -->
