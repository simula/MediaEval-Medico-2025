# MediaEval Medico 2025 – Final Results

This contains the final results for **Task 1** and **Task 2** from the official challenge leaderboard.

## Links
- **Main Competition Repository:** https://github.com/simula/MediaEval-Medico-2025   (has link to tasks, papers, etc)
- **YouTube Playlist (Workshop Recordings):** https://www.youtube.com/playlist?list=PLHr-k69ARa0jMZycp19Kefje3dPMG4znR

---

## 🏆 Task 1 — GI Question Answering  
### Challenge Leaderboard

| Rank | Team | BLEU | ROUGE-L | METEOR | Approach |
|-----:|------|------|---------|---------|----------|
| 🥇 1 (Tie) | MM-SSNCE & Team Nepal | 0.47 | 0.67 | 0.67 | Q/LoRA-4-bit tuned PaliGemma-3B |
| 🥈 2 | CVG-IBA | 0.45 | 0.65 | 0.65 | Florence-2 multi-task VQA |
| 🥉 3 | EndoVision | 0.42 | 0.64 | 0.64 | PaliGemma-2 end-to-end, SigLIP vision encoder |
| 4 | SELab-HCMUS | 0.40 | 0.63 | 0.61 | InstructBLIP (Flan-T5-XXL) encoder-decoder with LoRA (r=16, α=48) |
| — | *And 8 others…* | — | — | — | — |

---

## 🏆 Task 2 — Explainable Multimodal Reasoning  
### Challenge Leaderboard

| Rank | Team | Answer Correctness | Faithfulness | Clinical Relevance | Clarity | Completeness | Approach |
|-----:|------|--------------------|-------------|--------------------|---------|--------------|----------|
| 🥇 1 | Team Nepal | 0.86 | 0.74 | 0.76 | 0.90 | 0.61 | Self-probing PaliGemma-3B + LLM-synth (gpt-4o-mini); QLoRA 4-bit; 2-stage reasoning |
| 🥈 2 | CVG-IBA | 0.74 | 0.52 | 0.57 | 0.82 | 0.45 | Florence-2 multi-task VQA + text explanations + ref-exp segmentation (CLIPSeg) |
| 🥉 3 | SSN-InnovateX | 0.74 | 0.57 | 0.58 | 0.63 | 0.46 | BLIP-2 answer+explanation head; attention-rollout grounding & mask loss |
| 4 | IReL@IIT (BHU) | 0.59 | 0.27 | 0.38 | 0.82 | 0.25 | Dual-track (PaliGemma + Florence-2); artifact inpainting + token-prob confidence |

---

**Note:** The CVG-IBA team received a distinctive mention from MediaEval for their innovative approach and strong localisation performance.
