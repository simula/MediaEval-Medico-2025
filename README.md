
# 🌟 **MediaEval Medico 2025: Explainable VQA for GI Imaging** 🌟

📋 [**GitHub Repository**](https://github.com/SushantGautam/MediaEval-Medico-2025) | 🔗 [**MediaEval 2025**](https://multimediaeval.github.io/editions/2025/tasks/medico/) | 📝 [**Registration Form**](https://forms.gle/y7v1VLP7D9vsbuqv5) | 🏆 [**Leaderboard / Registered Submissions**](https://simulamet-medico-2025.hf.space)

---

The **MediaEval Medico 2025 Challenge** 🔬 focuses on **Visual Question Answering (VQA)** for **Gastrointestinal (GI) imaging**, emphasizing **explainability** 🤔📖 to foster **trustworthy AI** for **clinical adoption** ⚕️.

This task continues the long-running **Medico series** at MediaEval, now leveraging the newly developed **Kvasir-VQA-x1 dataset**, designed to support **multimodal reasoning** and **interpretable clinical decision support** 📈.

---

## 🌟 **Task Descriptions**

### 🔍 **Subtask 1: GI Image Question Answering (VQA)**

📈 **Goal:** Develop AI models that can accurately answer clinical questions using **GI endoscopic images**.

🧠 The task uses **Kvasir-VQA-x1**, an advanced dataset comprising **159,549 QA pairs** from **6,500 original GI images**, featuring:
- Multi-step reasoning questions  
- Naturalized medical language  
- Complexity scores for curriculum training  

🔠 **Question Types** include:
- Yes/No  
- Single-Choice  
- Multiple-Choice  
- Color-related  
- Location-related  
- Numerical Count  
- Merged reasoning-based questions  

💡 **Example Training Notebook:**  
Not sure where to start? Check out: [Training with ms-swift](https://github.com/simula/MediaEval-Medico-2025/blob/main/Task_1_Sample_Notebook.ipynb)  
<a target="_blank" href="https://colab.research.google.com/github/simula/MediaEval-Medico-2025/blob/main/Task_1_Sample_Notebook.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

⚠️ **Note:** You can only submit work for **Task 1** if you wish to participate.

---

### 💬 **Subtask 2: Clinician-Oriented Multimodal Explanations in GI**

📌 **Goal:** Move beyond simply predicting an answer (Subtask 1) and generate **rich, multimodal explanations** that are **transparent, understandable, and trustworthy** for clinicians.  

Your system should **justify its predictions** using **multiple complementary reasoning forms**—e.g., combining a detailed textual clinical explanation with a visual localization and/or a confidence measure.

**Requirements:**
- **Faithful** to the model’s reasoning.  
- **Clinically relevant** and medically sound.  
- **Useful** for real-world decision-making.  


#### 📄 Submission Format

A JSON/JSONL file where each entry corresponds to one test case:

```json
{
  "img_id": "UNIQUE_IMAGE_IDENTIFIER",
  "question": "Original question posed to the model.",
  "answer": "Model's prediction from Subtask 1.",
  "textual_explanation": "Detailed narrative in clinical language justifying the answer.",
  "visual_explanation": {
    "type": "heatmap | segmentation_mask | bounding_box | etc.",
    "format": "path/to/visual.png | base64_string | [[x1,y1,x2,y2]]",
    "description": "Brief description of what the visual shows."
  },
  "confidence_score": 0.92
}
```

**Field-by-Field Requirements:**
- **`img_id` / `question` / `answer`** → Must match Subtask 1 data and predictions exactly.  
- **`textual_explanation`** (Mandatory) → Clinician-oriented reasoning referencing visual cues (location, morphology, color, size, vascular pattern, etc.).  
- **`visual_explanation`** (Optional but encouraged) → Heatmaps, segmentation masks, or bounding boxes linked to the textual explanation.  
- **`confidence_score`** (Optional but encouraged) → Float in [0, 1], from model confidence or uncertainty estimation.  


#### 💡 Suggested Approaches
1. **VLM Self-Probing for Explanations** — Ask auxiliary questions (e.g., *"What is the abnormality?"*, *"Where is it located?"*, *"Describe its morphology"*) and combine answers into the `textual_explanation`.
2. **Visual Grounding** — Generate **heatmaps** or attention maps showing influential regions and link them to textual descriptions.
3. **Segmentation / Detection** — Produce masks or bounding boxes highlighting relevant pathology, reinforcing clinician trust.

⚠️ **Participation in Subtask 2 requires completion of Subtask 1.**

---

## 📂 **Dataset Overview: Kvasir-VQA-x1**

Built on **HyperKvasir** and **Kvasir-Instrument**, the **Kvasir-VQA-x1** dataset includes:
- 🧬 **159,549 QA pairs**
- 🖼️ **6,500 original GI images**
- ♻️ **10 weakly augmented images per original** (augmentation script provided)
- 🧠 **Complexity levels 1–3**
- 🧪 **Realistic medical question reformulations using LLMs**

📥 Dataset: [**Kvasir-VQA-x1 @ SimulaMet on Hugging Face**](https://huggingface.co/datasets/SimulaMet/Kvasir-VQA-x1)
 
---

## 🏆 **Submission System**

📌 [View Registered Submissions](https://simulamet-medico-2025.hf.space)

We use the [`medvqa`](https://pypi.org/project/medvqa/) Python package to **validate and submit** models.  
Your Hugging Face repo **must include**:
- [`submission_task1.py`](https://raw.githubusercontent.com/SushantGautam/MedVQA/refs/heads/main/medvqa/submission_samples/medico-2025/submission_task1.py)  
- [`submission_task2.py`](https://raw.githubusercontent.com/SushantGautam/MedVQA/refs/heads/main/medvqa/submission_samples/medico-2025/submission_task2.py)  


### 📦 Install
```bash
pip install -U medvqa
```
📌 Always use the latest version.


### ✅ Validate Before Submitting
```bash
medvqa validate --competition=medico-2025 --task=1/2 --repo_id=<your_repo_id>
```


### 🚀 Submit
```bash
medvqa validate_and_submit --competition=medico-2025 --task=1/2 --repo_id=<your_repo_id>
```

Your submission will appear on the [leaderboard](https://simulamet-medico-2025.hf.space).

---

## 🔍 **Evaluation Methodology**

**Subtask 1 (VQA Performance)**  
- Metrics: BLEU, ROUGE (1/2/L), METEOR  
- Settings: Original & augmented images  
- Criteria: Accuracy, relevance, medical correctness  

**Subtask 2 (Explainability)**  
Rated by experts on:
1. Answer correctness  
2. Clarity & clinical relevance  
3. Visual alignment  
4. Confidence calibration  
5. Methodology & novelty  

---

## 🛠️ **Tools & Resources**
- Scripts for augmentation, splits, and baselines  
- Submission templates  
- Fine-tuned model configs  
- Attention & saliency visualization methods  

---

## 📅 **Timeline (Preliminary)**

- 📦 **14 May 2025** — Development data release ✅  
- 🧪 **30 June 2025** — Validation data release  ✅  
- 📄 **12 September 2025** — Submission deadline  
- 🏆 **26 September 2025** — Results announced  
- 📝 **8 October 2025** — Working Notes deadline  
- 🏫 **25–26 October 2025** — MediaEval Workshop (Dublin + Online)  

---

## 💼 **Organizers**
- 👨‍🔬 Steven A. Hicks — [steven@simula.no](mailto:steven@simula.no)  
- 🧑‍💻 Michael A. Riegler — [michael@simula.no](mailto:michael@simula.no)  
- 🧑‍🔬 Vajira Thambawita — [vajira@simula.no](mailto:vajira@simula.no)  
- 👨‍🏫 Pål Halvorsen — [paalh@simula.no](mailto:paalh@simula.no)  
- 🧑‍🎓 [Sushant Gautam](https://sushant.info.np) — [sushant@simula.no](mailto:sushant@simula.no)  

---

## 🔗 **Join Us**
Let’s build the future of **trustworthy, explainable medical AI**.  
🌟 GI diagnostics needs interpretable answers. Your model can help save lives.

📍 Register: [**MediaEval 2025**](https://multimediaeval.github.io/editions/2025/)  
📁 Repo: [**GitHub**](https://github.com/SushantGautam/MediaEval-Medico-2025)  

🚀 *Develop explainable AI. Help doctors. Improve lives.*  
