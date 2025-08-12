# 🌟 **MediaEval Medico 2025: Explainable VQA for GI Imaging** 🌟

📋 [**GitHub Repository**](https://github.com/SushantGautam/MediaEval-Medico-2025) | 🔗 [**MediaEval 2025**](https://multimediaeval.github.io/editions/2025/tasks/medico/)  

The **MediaEval Medico 2025 Challenge** 🔬 focuses on **Visual Question Answering (VQA)** for **Gastrointestinal (GI) imaging**, emphasizing **explainability** 🤔📖 to foster **trustworthy AI** for **clinical adoption** ⚕️.

This task is a continuation of the long-running **Medico series** at MediaEval, now leveraging the newly developed **Kvasir-VQA-x1 dataset**, designed to support **multimodal reasoning** and **interpretable clinical decision support** 📈.

---

## 🌟 **Task Descriptions**

### 🔍 **Subtask 1: GI Image Question Answering (VQA)**
📈 **Goal:** Develop AI models that can accurately answer clinical questions using **GI endoscopic images**.

🧠 The task uses **Kvasir-VQA-x1**, an advanced dataset comprising **159,549 QA pairs** from **6,500 original GI images** with:
- Multi-step reasoning questions
- Naturalized medical language
- Complexity scores for curriculum training

🔠 Question types include:
- Yes/No  
- Single-Choice  
- Multiple-Choice  
- Color-related  
- Location-related  
- Numerical Count  
- Merged reasoning-based questions

#### 💥 Example Training Notebook: 
Dont know where to start? See: [Training with ms-swift](https://github.com/MediaEval-Medico-2025/blob/main/Task_1_Sample_Notebook.ipynb)
<a target="_blank" href="https://colab.research.google.com/github/simula/MediaEval-Medico-2025/blob/main/Task_1_Sample_Notebook.ipynb">
    <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

### Subtask 2: Clinician-Oriented Multimodal Explanations in GI

The goal of Subtask 2 is to move beyond simply predicting an answer (Subtask 1) and generate **rich, multimodal explanations** that are **transparent, understandable, and trustworthy** for clinicians.  
Your system should **justify its own predictions** using **multiple complementary forms of reasoning**—e.g., combining a detailed textual clinical explanation with a visual localization and/or confidence measure.

This task is intentionally **open-ended** to encourage innovation, but your explanation must be:
- **Faithful** to the model’s own reasoning.
- **Clinically relevant** and medically sound.
- **Useful** for real-world decision-making.

#### Submission Format
Need a JSON file (or JSONL) where each entry corresponds to one test case:

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


####  Field-by-Field Requirements
- **`img_id` / `question` / `answer`**  
  - Must match the Subtask 1 data and predictions exactly.  

- **`textual_explanation` (Mandatory)**  
  - Detailed, clinician-oriented reasoning that goes beyond stating the answer.  
  - Reference visual cues (location, morphology, color, size, vascular pattern, etc.).  
  - Example: *"Sessile polyp in the lower-left quadrant with disrupted vascular pattern and smooth surface, consistent with adenoma."*

- **`visual_explanation` (Optional but Highly Encouraged)**  
  - Can be **heatmaps** (Grad-CAM, attention), **segmentation masks**, or **bounding boxes**.  
  - Must clearly link to the textual explanation and highlight the relevant region(s).  

- **`confidence_score` (Optional but Encouraged)**  
  - Float in [0, 1] indicating certainty in the `answer`.  
  - Can come from softmax, calibrated uncertainty, or Bayesian methods.  


#### Suggested Approaches
- **Idea 1: VLM Self-Probing for Explanations**  
  Use your Subtask 1 Visual-Language Model to ask auxiliary questions:  
  - *"What is the abnormality?"* → "Polyp"  
  - *"Where is it located?"* → "Ascending colon"  
  - *"Describe its morphology"* → "Sessile, smooth surface"  
  Combine these into a coherent `textual_explanation`.

- **Idea 2: Visual Grounding**  
  - Generate **heatmaps** (Grad-CAM, attention maps) showing influential regions.  
  - Provide these in `visual_explanation` to back up the textual claim.  

- **Idea 3: Segmentation / Detection**  
  - Produce pixel-level masks or bounding boxes around the pathology.  
  - Use them to support the narrative and strengthen clinician trust.


####  Evaluation Criteria
Expert reviewers will rate submissions based on:

1. **Answer correctness** (from Subtask 1).  
2. **Clarity & Clinical Relevance** of `textual_explanation`.  
3. **Visual Alignment** — does the visual correctly highlight the finding?  
4. **Confidence Calibration** — if provided, does confidence match actual correctness?
5. **Methodology and Novelty**



⚠️ **Note:** Participation in Subtask 2 requires completion of Subtask 1.

---

## 📂 **Dataset Overview: Kvasir-VQA-x1**

📁 Built on top of **HyperKvasir** and **Kvasir-Instrument**, the **Kvasir-VQA-x1** dataset introduces:
- 🧬 **159,549 QA pairs**
- 🖼️ **6,500 original GI images**
- ♻️ **10 weakly augmented images per original** (augmentation script provided)
- 🧠 **Question complexity levels (1–3)**
- 🧪 **Realistic medical question reformulations and merging using LLMs**

🛠️ Dataset available at: [**SimulaMet on Hugging Face**](https://huggingface.co/datasets/SimulaMet/Kvasir-VQA-x1)

---

## 🏆 **Submission System**  
🚀 [View Registered Submissions](https://simulamet-medico-2025.hf.space)

We use the [`medvqa`](https://pypi.org/project/medvqa/) Python package to **validate and submit** models to the official system.
The model that needs to be submiited is expected to be in a HuggingFace repository.

### 📦 Installation  
```bash
pip install -U medvqa
```
> The library is under **active development**. Always ensure you're using the **latest version**.

Your HuggingFace repo **must include** a standalone script named:
- [`submission_task1.py`](https://raw.githubusercontent.com/SushantGautam/MedVQA/refs/heads/main/medvqa/submission_samples/medico-2025/submission_task1.py) for Task 1  
- [`submission_task2.py`](https://raw.githubusercontent.com/SushantGautam/MedVQA/refs/heads/main/medvqa/submission_samples/medico-2025/submission_task2.py) for Task 2  

Use the provided **template script**, and make sure to:
- Modify all `TODO` sections  
- Add required information directly in the script

### ✅ Validate Before Submitting  
First make sure your submission script works fine in your working environment and it loads the model correctly from your submission repo and generates outputs in the required format.

```bash
python submission_task1.py
```

#### 📄 Additional Dependencies  
If your code requires extra packages, you must include a `requirements.txt` in the **root of the repo**. The system will install these automatically during validation/submission.
Else you will get package missing errors.

Next, you can validate the script to work independently. The .py script should now be in the root of the same HuggingFace repo as your model. You can try this in a new venv:
```bash
medvqa validate --competition=medico-2025 --task=1/2 --repo_id=<your_repo_id>
```
- `--competition`: Set to `medico-2025`
- `--task`: Use `1` for Task 1 or `2` for Task 2  
- `--repo_id`: Your **HuggingFace model repo ID** (e.g., `SushantGautam/XXModelCheckpoint`)

### 🚀 Submission Command  
If validation is okey, you can just run:
```bash
medvqa validate_and_submit --competition=medico-2025 --task=1/2 --repo_id=<your_repo_id>
```
This will make a submisision and your username, along with the task and time, should be visible on [the portal](https://simulamet-medico-2025.hf.space) for it to be considered officially submitted.
The submission library will make your Hugging Face repository public but gated, granting the organizers access to your repo.
It must remain unchanged at least until the results of the competition are announced. However, you are free to make your model fully public (non-gated). 

If you encounter any issues with submission, **don’t hesitate to contact us**.

---

## 🔮 **Evaluation Methodology**

### ✅ **Subtask 1: VQA Performance**
- **Metrics:** BLEU, ROUGE (1/2/L), METEOR
- **Settings:**  
  - **Original Setting:** Clean images only  
  - **Transformed Setting:** Augmented images for robustness testing  
- **Criteria:** Accuracy, relevance, and medical correctness

### 💬 **Subtask 2: Explainability Score**
- Expert-reviewed metrics:
  - Correctness
  - Medical relevance
  - Cross-modal coherence
  - Visual clarity, etc.
- Encourages **interpretable and safe model behavior**

---

## 🛠️ **Tools & Resources**
- 📦 Scripts for augmentation, splits, and baselines
- 🔗 Submission templates (coming soon)
- 🤖 LLM-based merging prompts and fine-tuned model configurations
- 🧠 Suggested frameworks: attention, saliency maps, probabilistic modeling

---

## 📊 **Research Questions for Exploration**
- How can we balance **performance and interpretability**?
- What role does **uncertainty** play in clinical explanation?
- Can we design a scoring mechanism for **explanation quality**?
- What helps **clinicians trust** model outputs?

---

## 👥 **Target Group**
🎓 Students, researchers, and professionals from:
- Medical Imaging  
- Multimedia AI  
- Computer Vision & NLP  
- Explainable AI  

💬 Student mentoring available!

---

## 🗓️ **Timeline (Preliminary)**

- 📦 **14 May 2025**: Development data release _(passed)_
- 🧪 **30 June 2025**: Validation data available  
- 📄 **12 September 2025**: Submission deadline  
- 🏆 **26 September 2025**: Results announced  
- 📝 **8 October 2025**: Working Notes deadline  
- 🏫 **25–26 October 2025**: MediaEval Workshop (Dublin + Online)

---

## 💼 **Organizers**  
✨ For any queries, contact our team:  
- 👨‍🔬 Steven A. Hicks: [steven@simula.no](mailto:steven@simula.no)  
- 🧑‍💻 Michael A. Riegler: [michael@simula.no](mailto:michael@simula.no)  
- 🧑‍🔬 Vajira Thambawita: [vajira@simula.no](mailto:vajira@simula.no)  
- 👨‍🏫 Pål Halvorsen: [paalh@simula.no](mailto:paalh@simula.no)  
- 🧑‍🎓 [Sushant Gautam](https://sushant.info.np): [sushant@simula.no](mailto:sushant@simula.no)  

---

## 🔗 **Join Us**  
Let’s build the future of **trustworthy, explainable medical AI**.  
🌟 GI diagnostics needs interpretable answers. Your model can help save lives.

📍 Register at [**MediaEval 2025**](https://multimediaeval.github.io/editions/2025/)  
📁 Challenge repo: [**GitHub**](https://github.com/SushantGautam/MediaEval-Medico-2025)

🚀 *Develop explainable AI. Help doctors. Improve lives.*
