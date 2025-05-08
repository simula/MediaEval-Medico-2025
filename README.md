# 🌟 **MediaEval Medico 2025: Explainable VQA for GI Imaging** 🌟

📋 [**GitHub Repository**](https://github.com/SushantGautam/MediaEval-Medico-2025) | 🔗 [**MediaEval 2025**](https://multimediaeval.github.io/editions/2025/tasks/medico/)  

The **MediaEval Medico 2025 Challenge** 🔬 focuses on **Visual Question Answering (VQA)** for **Gastrointestinal (GI) imaging**, emphasizing **explainability** 🤔📖 to foster **trustworthy AI** for **clinical adoption** ⚕️.

This task is a continuation of the long-running **Medico series** at MediaEval, but now introduces **multimodal explanations** 🎨💬 to ensure **interpretable clinical decision support** 📈.

---

## 🌟 **Task Descriptions**

### 🔍 **Subtask 1: GI Image Question Answering (VQA)**
📈 **Goal:** Build AI models to answer clinical questions based on **6,500 annotated GI images** from the **Kvasir-VQA dataset**. These span diseases, tools, and procedures. 

❗ Question types include:
- Yes/No
- Single-Choice
- Multiple-Choice
- Color-Related
- Location-Related
- Numerical Count

🌍 **Focus:** Combine **visual** and **textual** understanding to provide accurate answers. 

#### 🔹 Example Questions
- ❓ How many polyps are visible?
- ✅ Is there a biopsy tool in use?
- 💊 What abnormality is observed?

### 🖌️ **Subtask 2: Multimodal Explainability for Clinicians**

📈 **Goal:** Go beyond answer accuracy. Provide **multimodal explanations** that:
- Highlight **relevant image regions** 🖼️
- Include **textual justifications** 📖
- Present **confidence scores** or uncertainty estimates

✨ These explanations must align with **clinical reasoning**, improving **interpretability and trust** ⚕️.

🔸 **Note:** Subtask 2 builds on Subtask 1 — completing Subtask 1 is a prerequisite.

---

## 📂 **Dataset Overview**

We use the [**Kvasir-VQA dataset**](https://datasets.simula.no/kvasir-vqa/) — an extension of **HyperKvasir** and **Kvasir-Instrument**, enriched with VQA annotations.

📷 **6,500 GI Images** with annotated Q&A across key diagnostic features, validated by medical professionals.

📄 Question Types:
- Yes/No
- Single/Multiple Choice
- Color, Location, Count-based questions

---

## 🔮 **Evaluation Methodology**

### ✅ **Subtask 1: Accuracy & Explainability**
- 📊 **Metrics:** 📘 **METEOR**, 📖 **ROUGE** (1/2/L), and 🧠 **BLEU**.  
- 📜 **Evaluation:** Based on **correctness** ✅ and **relevance** 📝 of answers using the provided **questions** 💬 and **images** 🖼️.

### 💬 **Subtask 2: Multimodal Explanation Quality**
- **Explainability Score** (expert reviewed):
  - Clarity 
  - Medical relevance
  - Coherence across modalities

🗓️ Explanations should assist clinicians in **understanding AI decisions**.

---

## 🔧 **Tools & Resources**
- 🔗 sample scripts, submission templates, and baseline models coming soon, stay tuned!
- 🌐 HuggingFace-ready formats
- 🔍 Multimodal fusion models encouraged (attention, heatmaps, uncertainty estimation)

---

## 📊 **Research Questions for Exploration**
- ❓ What types of explanations best support clinician trust?
- 🔍 How can uncertainty or attention improve interpretability?
- ✏️ Can we balance high accuracy and clear reasoning?
- 📊 How should we evaluate explainability fairly?

---

## 👥 **Target Group**
📆 Undergraduate and graduate students, researchers in:
- Multimedia analysis
- Computer vision + NLP
- Medical imaging
- Explainable AI

💡 Mentoring available for students! 

---

## 📅 **Schedule (Preliminary)**

- 🗓️ **14 May 2025**: Development data release
- 🗓️ **30 June 2025**: Validation set available
- 🗓️ **12 September 2025**: Submission deadline
- 🗓️ **26 September 2025**: Results announced
- 🗓️ **8 October 2025**: Working Notes paper due
- 🏛️ **25-26 October 2025**: MediaEval Workshop, Dublin + Online

---

## 💼 **Organizers**  
✨ For any queries, feel free to reach out to our amazing team:  
- 👨‍🔬 **Steven A. Hicks** 📧 [steven@simula.no](mailto:steven@simula.no)  
- 🧑‍💻 **Michael A. Riegler** 📧 [michael@simula.no](mailto:michael@simula.no)  
- 🧑‍🔬 **Vajira Thambawita** 📧 [vajira@simula.no](mailto:vajira@simula.no)  
- 👨‍🏫 **Pål Halvorsen** 📧 [paalh@simula.no](mailto:paalh@simula.no)  
- 🧑‍🎓 **[Sushant Gautam](http://sushant.info.np)** 📧 [sushant@simula.no](mailto:sushant@simula.no)  

---

## 🔗 **Join Us**  
Let’s develop interpretable, powerful AI for GI diagnostics. 🪠🌍 

📅 Registration and participation info at: [**MediaEval 2025**](https://multimediaeval.github.io/editions/2025/)  
📃 Challenge Repo: [**GitHub**](https://github.com/SushantGautam/MediaEval-Medico-2025)

🚀 *Build explainable AI. Help doctors. Improve lives.*
