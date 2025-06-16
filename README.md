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

---

### 🖌️ **Subtask 2: Multimodal Explainability for Clinicians**

📈 **Goal:** Move beyond prediction — provide **interpretable, multimodal explanations** that support:
- Region-based visual highlights 🖼️
- Textual clinical justifications 📖
- Confidence or uncertainty estimates 📉

🔄 Each explanation should reflect **clinical reasoning** to assist human experts in understanding AI output.

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

## 🔮 **Evaluation Methodology**

### ✅ **Subtask 1: VQA Performance**
- **Metrics:** BLEU, ROUGE (1/2/L), METEOR
- **Settings:**  
  - **Original Setting:** Clean images only  
  - **Transformed Setting:** Augmented images for robustness testing  
- **Criteria:** Accuracy, relevance, and medical correctness

### 💬 **Subtask 2: Explainability Score**
- Expert-reviewed metrics:
  - Visual clarity
  - Medical relevance
  - Cross-modal coherence
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
