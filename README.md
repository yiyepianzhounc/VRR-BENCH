# See Beyond: Benchmarking MLLMs’ Visual Relational Reasoning Ability

Welcome to the official repository for our paper **“See Beyond: Benchmarking MLLMs’ Visual Relational Reasoning Ability”**!

We introduce **VRR-BENCH**, a comprehensive benchmark designed to evaluate Multimodal Large Language Models (MLLMs) on their capacity to reason about visual relationships. VRR-BENCH consists of:

* **OriginalDataset**: 280 image–question pairs covering both non-relational (single-object) and relational (inter-object) tasks at three difficulty levels.
* **SoMDataset**: 420 “Set-of-Mark” images derived from original images, enabling targeted in-context adaptation.
* **SpecialDataset**: 40 Stress-testing images including occlusion and size-comparison challenges.

Our benchmark reveals that, while MLLMs perform well on simple attribute queries, their accuracy drops by an average of 22.01 % on relational reasoning tasks—highlighting a critical gap in current multimodal capabilities.

This repository contains all data, model-calling notebooks. Dive in to explore VRR-BENCH, run your favorite MLLM, and help push the frontier of visual reasoning!

🤗 **Note**
Due to GitHub’s file count limits, the full VRR-BENCH image set is hosted on Hugging Face. You can download it here: [VRR-BENCH](https://huggingface.co/datasets/Ivy0529/VRR-BENCH)

---

## 📊 Dataset Overview

We collected ~280 CAPTCHA-style images from major providers (e.g., Geetest), each paired with a carefully designed question requiring either single-object attribute reasoning or explicit inter-object relational reasoning.

| Subset          | Task Type        | Levels (L1/L2/L3) | # Images | # Q\&A Pairs |
| --------------- | ---------------- | ----------------- | -------- | ------------ |
| OriginalDataset | Non-Relational   | 1 / 2 / 3         | 140      | 140          |
| OriginalDataset | Relational       | 1 / 2 / 3         | 140      | 140          |
| SoMDataset      | Auxiliary-R      | 1 / 2 / 3         | 140      | 140          |
| SoMDataset      | Non-Relational   | 1 / 2 / 3         | 140      | 140          |
| SoMDataset      | Relational       | 1 / 2 / 3         | 140      | 140          |
| SpecialDataset  | Occlusion        | –                 | 20       | 20           |
| SpecialDataset  | Size\_Comparison | –                 | 20       | 20           |

*Levels (L1/L2/L3) correspond to the number of attributes per question (e.g., color; color+shape; color+shape+size).*

---

## 📈 Benchmark Structure
![structure](https://github.com/user-attachments/assets/330a4d6d-a78c-440a-b618-6f78bb134b70)


1. **Attribute Values & Sets**
2. **Arrangement (Spatial) Relationships**
3. **Question Text** → “Please locate the large red cube.”
4. **Reasoning Procedure** → step-by-step filtering and verification

---

## 📊 Evaluation Results


  ![level_final](https://github.com/user-attachments/assets/07a284f5-9ade-4f70-8279-cdef502b338e)
  Figure:</i> Accuracy (%) of six MLLMs on Non-Relational (a) vs. Relational (b) tasks across three difficulty levels.


Key observations after experiments:

* Relational tasks are more challenging than Non-Relational ones, both task types perform poorly in size-related sub-tasks.
* Simplicity in scenes does not equate to simplicity in reasoning: Relational objects increase reasoning difficulty.

---

## ⚙️ How to Use

**1. Clone & install dependencies**

```bash
git clone https://github.com/yiyepianzhounc/VRR-BENCH.git
```

**2. Prepare data**
Ensure your folder layout matches:

```
VRR-BENCH/
├── dataset/
│   ├── OriginalDataset/
│   ├── SoMDataset/
│   └── SpecialDataset/
└── models/
    └── *.ipynb
```

**3. Run model inference**
Open the notebook in `models/` for your target MLLM, fill in your API key, and execute all cells.

---

## 📬 Contact

For questions or collaboration, please reach out to:

* **Haizhou Wang** ([haizhou.wang@scu.edu.cn](mailto:haizhou.wang@scu.edu.cn))
* **Yifan Wang** ([sanqin@stu.scu.edu.cn](mailto:sanqin@stu.scu.edu.cn))

---

*This work is licensed under the MIT License.*

