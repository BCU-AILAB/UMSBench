<div align="center">

# UMSBench-v1: A Real-Synthetic Composited Multimodal Benchmark Dataset for Underground Mine Safety

Feiteng Han<sup>1*</sup>, Ming Xue<sup>2*</sup>, Kaiyu Li<sup>1</sup>, Tao Feng<sup>2</sup>, Wei Shen<sup>1</sup>,  
Hui Wang<sup>1</sup>, Yudong Fang<sup>2†</sup>, Yu Wang<sup>1†</sup>, Xuecheng Tan<sup>3</sup>

<sup>1</sup>School of Information Technology, Beijing City University,  
<sup>2</sup>Big Data Center, Ministry of Emergency Management,  
<sup>3</sup>School of Software, Tsinghua University

<div>
<sup>†</sup> Equal contribution &nbsp;&nbsp; <sup>*</sup> Corresponding author
</div>

<div>
  {hanfeiteng, kaiyuli, shen_0711, bcuwhui, wangyu}@bcu.edu.cn, <br>
  research.xue@gmail.com, ifengtaoi@outlook.com, <br>
  fangyudong9713@ustc.edu, tanxuecheng@tsinghua.edu.cn
</div>

</div>

## Abstract
To fill the gap on benchmark datasets for vision language models (VLM) research on underground mining safety analysis, we introduce UMSBench-v1.0. As the first multimodal VQA benchmark dataset and also the first real-synthetic image dataset on mining safety, it consists of 10k real-synthetic underground images and 40k question-answer pairs correspondingly, and covers safety reasoning, captioning, understanding and perception over 30 underground mining site types. The synthetic data are generated with newly proposed Image-to-Text-to-Image（I2T2I）mechanism based on refined LLM-driven captioning capabilities, prompting engineering and visual content generation models. Moreover, benchmarking tasks are reformulized as Single-Choice Questions (SCQs) with advanced VLMs and human experts as references to archive
higher flexibility, scalability and efficiency. State-of-the-art vision language models are bench-marked and finetuned to demonstrate the dataset’s effectiveness and potential application. The dataset will be released at https://github.com/BCU-AILAB/UMSBench.
<!-- <div align="center">
  <img src="pictures/fig1_bluemask_0307v2.jpg">
</div> -->
## UMSBench-v1 Dataset (Samples Subset)

> **⚠️ Note:** The data provided via the links below represents a **samples subset** of the complete dataset, intended for demonstration and initial exploration purposes.This samples subset contains two folders: `synthetic` and `real`.
### 📥 Download Links
You can access the dataset samples subset through either of the following platforms:
* **[Baidu Drive](https://pan.baidu.com/s/1g9zy5I0nT8RO64LsfrRpeQ?)**
* **[Google Drive](https://drive.google.com/file/d/119AdLDWoQUtZY1LqiRR_SdxiJsRWRPjM/view?usp=sharing)**

### 🙏 Acknowledgments

This work was supported by the National Key Research and Development Program of China (2024YFC3015605, 2024YFC3015505). We appreciate Xihong Lin, Yijie Li, Runquan Shen, Zimeng Xin, Boyu Gao, Xinze He, Zitong Hui, Tianfei Xin, Yuyan Wang at BCU for their work of data processing. We also appreciate the authors of previous SOTA works for their open-source codes, models and datasets, and the anonymous reviewers for their helpful feedback.
<!-- ## Citation

```
@inproceedings{
song2024lsmadapter,
title={Urban Waterlogging Detection: A Challenging Benchmark and Large-Small Model Co-Adapter},
author={Suqi Song and Chenxu Zhang and Peng Zhang and Pengkun Li and Fenglong Song and Lei Zhang},
journal = {ECCV},
issue_date = {2024}
}
``` -->