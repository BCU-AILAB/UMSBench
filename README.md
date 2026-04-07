<div align="center">

# UMSBench-v1: A Real-Synthetic Composited Multimodal Benchmark Dataset for Underground Mine Safety

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Dataset](https://img.shields.io/badge/Dataset-Release-green.svg)](#-dataset-download)
[![Paper](https://img.shields.io/badge/Paper-Arxiv-red.svg)](#)

**Feiteng Han**<sup>1*</sup> &nbsp; **Ming Xue**<sup>2*</sup> &nbsp; **Kaiyu Li**<sup>1</sup> &nbsp; **Tao Feng**<sup>2</sup> &nbsp; **Wei Shen**<sup>1</sup> <br>
**Hui Wang**<sup>1</sup> &nbsp; **Yudong Fang**<sup>2†</sup> &nbsp; **Yu Wang**<sup>1†</sup> &nbsp; **Xuecheng Tan**<sup>3</sup>

<sup>1</sup>*School of Information Technology, Beijing City University* <sup>2</sup>*Big Data Center, Ministry of Emergency Management* <sup>3</sup>*School of Software, Tsinghua University*

<sup>†</sup> Corresponding author &nbsp;&nbsp; <sup>*</sup> Equal contribution

`{hanfeiteng, kaiyuli, shen_0711, bcuwhui, wangyu}@bcu.edu.cn` <br>
`research.xue@gmail.com` | `ifengtaoi@outlook.com` <br>
`fangyudong9713@ustc.edu` | `tanxuecheng@tsinghua.edu.cn`

</div>

---

## 📖 Abstract
To fill the gap in benchmark datasets for vision-language models (VLM) research on underground mining safety analysis, we introduce **UMSBench-v1.0**. As the first multimodal VQA benchmark dataset and the first real-synthetic image dataset on mining safety, it consists of **10k real-synthetic underground images** and **40k question-answer pairs**, covering safety reasoning, captioning, understanding, and perception across 30 underground mining site types. 

The synthetic data is generated via a newly proposed **Image-to-Text-to-Image (I2T2I)** mechanism based on refined LLM-driven captioning capabilities, prompt engineering, and visual content generation models. Furthermore, benchmarking tasks are reformulated as Single-Choice Questions (SCQs) to achieve higher flexibility, scalability, and efficiency. State-of-the-art VLMs are benchmarked and fine-tuned to demonstrate the dataset’s effectiveness and potential applications. The dataset is officially released at [BCU-AILAB/UMSBench](https://github.com/BCU-AILAB/UMSBench).

---

## 🖼️ Dataset Overview & I2T2I Examples

Our dataset utilizes the proposed **I2T2I** pipeline to generate high-fidelity synthetic images that closely match the semantic distribution of real underground mining scenarios. Below are some examples of the generated images paired with their corresponding textual prompts.

| Synthetic Image | Generation Prompt|
| :---: | :--- |
| <img src="assets/syn_1.jpg" width="200"/> | **Prompt:** *A dimly lit underground coal mine tunnel. A miner wearing a yellow hard hat, reflective safety vest, and headlamp is inspecting a heavy-duty conveyor belt. The ground is slightly damp, and metal support beams line the tunnel walls. High realism, industrial lighting.* |
| <img src="assets/syn_2.jpg" width="200"/> | **Prompt:** *Safety hazard in a subterranean mine. Water is visibly leaking from the rocky roof, forming muddy puddles on the tracks. A yellow 'Caution: Slippery' warning sign is placed on the side. Gritty texture, high detail.* |
| <img src="assets/syn_3.jpg" width="200"/> | **Prompt:** *An automated tunnel boring machine operating at the rock face of an underground gold mine. Thick dust particles are suspended in the air, illuminated by bright artificial spotlights. No human workers are present in the immediate vicinity. Cinematic lighting, ultra-realistic.* |
| <img src="assets/syn_4.jpg" width="200"/> | **Prompt:** *A worker in an underground mine environment inappropriately operating machinery without safety gloves. The scene focuses on the worker's hands manipulating a control panel. Dark background, focal point on the control panel and hands, photorealistic.* |

> **Note for Users:** The above prompts are representative examples used during the synthesis phase. The full dataset includes diverse prompts covering 30+ site types.

---

## 📥 Dataset Download

### 1. Samples Subset (Publicly Available)
The data provided via the links below represents a **samples subset** of the complete dataset, intended for demonstration and initial exploration purposes. This subset contains two folders: `synthetic` and `real`.

* ☁️ **[Baidu Drive](https://pan.baidu.com/s/1g9zy5I0nT8RO64LsfrRpeQ?)**
* ☁️ **[Google Drive](https://drive.google.com/file/d/119AdLDWoQUtZY1LqiRR_SdxiJsRWRPjM/view?usp=sharing)**

### 2. Full Dataset Access Agreement
Due to the domain-specific and sensitive nature of underground mining safety data, the full **UMSBench-v1.0** dataset is available strictly for **non-commercial, academic research purposes**. To access the full dataset, please follow these steps:

1. Download the [Dataset Access Agreement Form (PDF)](#) *(TODO: Insert the link to your agreement PDF here)*.
2. Carefully read the terms. The form must be completely filled out and **hand-signed by a full-time faculty member or legal representative** (e.g., Professor, PI, or Lab Director) of your institution.
3. Send the scanned, signed copy of the agreement using your **official institutional email address** to: 
   📧 `hanfeiteng@bcu.edu.cn` and `wangyu@bcu.edu.cn`.
   * **Email Subject Format:** `[UMSBench Full Dataset Application] - {Your Institution} - {Your Name}`
4. Upon approval (usually within 3-5 business days), we will reply with the download links and decryption passwords for the full dataset.

> **⚠️ Important:** Applications sent from personal email addresses (e.g., @gmail.com, @qq.com, @163.com) or lacking a proper authorized signature will **NOT** be processed.

---

## 🙏 Acknowledgments
This work was supported by the **National Key Research and Development Program of China** (2024YFC3015605, 2024YFC3015505). 

We appreciate Xihong Lin, Yijie Li, Runquan Shen, Zimeng Xin, Boyu Gao, Xinze He, Zitong Hui, Tianfei Xin, and Yuyan Wang at BCU for their hard work in data processing. We also appreciate the authors of previous SOTA works for their open-source codes, models, and datasets, and the anonymous reviewers for their helpful feedback.

---

## 📝 Citation
If you find our dataset or paper useful in your research, please consider citing our work:

```bibtex
@inproceedings{han2024umsbench,
  title={UMSBench-v1: A Real-Synthetic Composited Multimodal Benchmark Dataset for Underground Mine Safety},
  author={Han, Feiteng and Xue, Ming and Li, Kaiyu and Feng, Tao and Shen, Wei and Wang, Hui and Fang, Yudong and Wang, Yu and Tan, Xuecheng},
  booktitle={Under Review}, 
  year={2024}
}
