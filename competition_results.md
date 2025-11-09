# MediaEval Medico 2025 – Final Results

This contains the final results for **Task 1** and **Task 2** from the official challenge leaderboard.

## Links
- **Main Competition Repository:** https://github.com/simula/MediaEval-Medico-2025   (has link to tasks, papers, etc)
- **YouTube Playlist (Workshop Recordings):** https://www.youtube.com/playlist?list=PLHr-k69ARa0jMZycp19Kefje3dPMG4znR

---

## 🏆 Task 1 — GI Question Answering  
### Challenge Leaderboard

| Rank | Team | Authors | BLEU | ROUGE-L | METEOR | Approach |
|-----:|------|---------|------|---------|--------|----------|
| 🥇 1 (Tie) | MM-SSNCE | Vishal S, Rajalakshmi Sivanaiah, Angel Deborah Suseelan | 0.47 | 0.67 | 0.67 | Q/LoRA-4-bit tuned PaliGemma-3B |
| 🥇 1 (Tie) | Team Nepal | Sujata Gaihre, Amir Thapa Magar | 0.47 | 0.67 | 0.67 | Self-probing PaliGemma-3B |
| 🥈 2 | CVG-IBA | Itbaan Safwan, Muhammad Annas Shaikh, Muhammad Haaris, Ramail Khan, Muhammad Atif Tahir | 0.45 | 0.65 | 0.65 | Florence-2 multi-task VQA |
| 🥉 3 | EndoVision | Sarath Chandran K R, Sivasriraman P, Vishnu Murugesh V, Vishwajith L K | 0.42 | 0.64 | 0.64 | PaliGemma-2 end-to-end, SigLIP vision encoder |
| 4 | SELab-HCMUS | Minh-Triet Bui, Nam-Tran Nguyen-Thuy, Hai-Dang Nguyen, Minh-Triet Tran | 0.40 | 0.63 | 0.61 | InstructBLIP (Flan-T5-XXL) encoder-decoder with LoRA (r=16, α=48) |
| — | *And 8 others…* | — | — | — | — | — |

---

## 🏆 Task 2 — Explainable Multimodal Reasoning  
### Challenge Leaderboard

| Rank | Team | Authors | Answer Correctness | Faithfulness | Clinical Relevance | Clarity | Completeness | Approach |
|-----:|------|---------|--------------------|-------------|--------------------|---------|--------------|----------|
| 🥇 1 | Team Nepal | Sujata Gaihre, Amir Thapa Magar | 0.86 | 0.74 | 0.76 | 0.90 | 0.61 | Self-probing PaliGemma-3B + LLM-synth (gpt-4o-mini); QLoRA 4-bit; 2-stage reasoning |
| 🥈 2 | CVG-IBA | Itbaan Safwan, Muhammad Annas Shaikh, Muhammad Haaris, Ramail Khan, Muhammad Atif Tahir | 0.74 | 0.52 | 0.57 | 0.82 | 0.45 | Florence-2 multi-task VQA + text explanations + ref-exp segmentation (CLIPSeg) |
| 🥉 3 | SSN-InnovateX | Lakshmi Priya S, Dhannya S M, Moogambigai A, Nikhil Karthik S, Pandiarajan D | 0.74 | 0.57 | 0.58 | 0.63 | 0.46 | BLIP-2 answer+explanation head; attention-rollout grounding & mask loss |
| 4 | IReL@IIT(BHU) | Krishna Tewari, Sukomal Pal | 0.59 | 0.27 | 0.38 | 0.82 | 0.25 | Dual-track (PaliGemma + Florence-2); artifact inpainting + token-prob confidence |


---

**Note:** The CVG-IBA team received a distinctive mention from MediaEval for their innovative approach and strong localisation performance.

---

# Registered Contributions

## 1. Team Nepal (task 1 {shared} and 2 winner)
**Authors:** Sujata Gaihre, Amir Thapa Magar  
**Paper Title:** *From Answers to Explanations: Self-Probing Efficiently Fine-Tuned Vision–Language Models for Medical VQA at Medico 2025*  
**Contact Emails:** sujatag391@gmail.com, amirthapa2019@gmail.com  

**Core Model & Strategy:** Self-probing PaliGemma-3B (QLoRA 4-bit)  
**Technical Details:** LoRA r=16, α=32; 2 epochs; affine + color augmentation; GPT-4o-mini LLM-synth explanations  

## 2. MM-SSNCE  (task 1 {shared} winner)
**Authors:** Vishal S, Rajalakshmi Sivanaiah, Angel Deborah Suseelan  
**Paper Title:** *Exploring Vision–Language Models for Medical VQA on Gastrointestinal Images: A LoRA Fine-Tuning Study*  
**Contact Emails:** vishal2310293@ssn.edu.in, rajalakshmis@ssn.edu.in, angeldeborahS@ssn.edu.in  

## 3. CVG-IBA (distinctive mention)
**Authors:** Itbaan Safwan, Muhammad Annas Shaikh, Muhammad Haaris, Ramail Khan, Muhammad Atif Tahir  
**Paper Title:** *Multi-Task Learning for Visually Grounded Reasoning in Gastrointestinal VQA*  
**Contact Emails:** i.safwan.26197@khi.iba.edu.pk, m.shaikh.26919@khi.iba.edu.pk, m.haaris.27083@khi.iba.edu.pk, r.khan.26924@khi.iba.edu.pk, atiftahir@iba.edu.pk  

**Core Model & Strategy:** Multi-task Florence-2 VQA + grounding  
**Technical Details:** LoRA r=128, α=256; CLIPSeg + Kvasir-SEG; task tokens for VQA/explanation  


**Core Model & Strategy:** LoRA-tuned PaliGemma-3B (benchmark study)  
**Technical Details:** Compared Florence, BLIP, PaliGemma; model-specific resizing; HF weights released  

## 4. SELab-HCMUS
**Authors:** Minh-Triet Bui, Nam-Tran Nguyen-Thuy, Hai-Dang Nguyen, Minh-Triet Tran  
**Paper Title:** *Enhancing Encoder-Decoder Architecture to Visual Question Answering Task for Gastrointestinal Images*  
**Contact Emails:** student240238@ptnk.edu.vn, student240237@ptnk.edu.vn, nhdang@selab.hcmus.edu.vn, tmtriet@hcmus.edu.vn  

**Core Model & Strategy:** InstructBLIP (Flan-T5-XXL encoder–decoder)  
**Technical Details:** LoRA r=16, α=48; batch size 64; lr=5e-5; 10 epochs (A100); no augmentation  


## 5. EndoVision
**Authors:** Sarath Chandran K R, Sivasriraman P, Vishnu Murugesh V, Vishwajith L K  
**Paper Title:** *PaliGemma 2 for Explainable Colonoscopy VQA: Bridging Visual Attention and Clinical Insight*  
**Contact Emails:** sarathchandran@ssn.edu.in, sivasriraman2370066@ssn.edu.in, vishnumurugesh2370054@ssn.edu.in, vishwajith2370033@ssn.edu.in  

**Core Model & Strategy:** PaliGemma-2 (end-to-end)  
**Technical Details:** SigLIP So400m/14 vision encoder; CE loss; Grad-CAM + confidence maps  


## 6. Aeolus
**Authors:** Prabhash Jha, Firoj Paudel, Debesh Jha  
**Paper Title:** *LoRA-Enhanced PaliGemma for Efficient Visual Question Answering in Gastrointestinal Imaging*  
**Contact Emails:** prabhashj07@gmail.com, debeshjha1@gmail.com, firoj7902@mbmcsit.edu.np  

**Core Model & Strategy:** LoRA PaliGemma-3B (quantized 630 MB)  
**Technical Details:** r=128, α=64; nf4 4-bit double quantization; Grad-CAM visual maps  


## 7. Lama4Vision
**Authors:** Mahdi Azmoodeh-Kalati, Mohammad Sadegh Maghareh, Saba Alavi, Reza Lashgari  
**Paper Title:** *Curriculum-Guided Fine-Tuning for Multimodal VQA in GI Endoscopy (Team Lama4Vision)*  
**Contact Emails:** m.azmudehkalati@alumni.sbu.ac.ir, maghareh@aut.ac.ir, sabaalavi13@gmail.com, r_lashgari@sbu.ac.ir  

**Core Model & Strategy:** Curriculum fine-tuning Qwen2-VL-2B  
**Technical Details:** 3-stage curriculum (Easy → Hard); LoRA r=16, α=16; Unsloth 8-bit AdamW; noted 59% image overlap  


## 8. SSN-InnovateX
**Authors:** Lakshmi Priya S, Dhannya S M, Moogambigai A, Nikhil Karthik S, Pandiarajan D  
**Paper Title:** *BLIP-2-based Visual Question Answering with Multimodal Explanations for Gastrointestinal Imaging*  
**Contact Emails:** lakshmipriyas@ssn.edu.in, dhannyasm@ssn.edu.in, moogambigai2370071@ssn.edu.in, nikhilkarthik2370024@ssn.edu.in, pandiarajan2370062@ssn.edu.in  

**Core Model & Strategy:** BLIP-2 fine-tuning with joint VQA + explanation head  
**Technical Details:** ViT-B/16 encoder; answer + mask loss; attention-rollout grounding; AdamW 3e-5  


## 9. IReL@IIT (BHU)
**Authors:** Krishna Tewari, Sukomal Pal  
**Paper Title:** *X-VQA for GI Diagnostics: Multimodal VQA with Confidence-Aware Explanations*  
**Contact Emails:** krishnatewari.rs.cse24@itbhu.ac.in, spal.cse@itbhu.ac.in  

**Core Model & Strategy:** Dual-track system (PaliGemma + Florence-2)  
**Technical Details:** Specular inpainting; Pali LoRA r=8 α=32; Florence LoRA r=4 α=16; token-probability–based confidence  

