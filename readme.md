Here’s an improved version of your GitHub README in Markdown, incorporating better structure, formatting, and clarity.

⸻

🚀 CIS5300 Final Project: From BART to Edge

Fine-tuning Large Language Models (LLMs) for Chinese-to-English translation in the education domain, with a comparison of mBART and M2M100, utilizing LoRA and Layer Freezing techniques to optimize performance and efficiency.

⸻

📌 Project Overview

🔹 Objective: Identify the most effective and resource-efficient fine-tuning technique for domain-specific Chinese-to-English translation.
🔹 Models Compared:
	•	mBART-50 (Multilingual BART)
	•	M2M100 (Many-to-Many Multilingual Model)
🔹 Techniques Implemented:
	•	LoRA (Low-Rank Adaptation)
	•	Layer Freezing
	•	Quantization (LLaMA & Marian MT)

📁 Project Structure

The repository contains two main Jupyter notebooks:
	•	Education_Translation.ipynb → Fine-tuning in the education domain
	•	Science_Translation.ipynb → Fine-tuning in the science domain

Pipeline Overview

1️⃣ Load & Preprocess: Import libraries, load datasets, initialize models, define evaluation metrics.
2️⃣ Baseline Evaluation: Evaluate pre-trained models (mBART & M2M100) on a 50,000-sample dataset.
3️⃣ Hyperparameter Tuning: Grid search on a smaller 10,000-sample dataset to find optimal settings.
4️⃣ Fine-Tuning: Apply best parameters for LoRA and Layer Freezing on the full dataset.
5️⃣ Evaluation & Analysis: Compare BLEU scores, perform error analysis, and measure GPU usage.
6️⃣ Extensions: Explore quantization using LLaMA and Marian MT for low-resource scenarios.

⸻

🔧 Setup & Installation

1️⃣ Install Dependencies

Ensure the following libraries are installed:

pip install datasets optimum auto-gptq sentencepiece bitsandbytes sacremoses sacrebleu transformers peft nltk tqdm pandas torch

2️⃣ Download Dataset

Place the dataset in the working directory and update file paths accordingly.

Dataset File	Domain
Bi-Education.txt	Education
Bi-Science.txt	Science



⸻

📊 Results & Findings

Baseline BLEU Scores (Before Fine-Tuning)

Model	Science	Education
mBART	0.1223	0.1169
M2M100	0.0231	0.0347

Fine-Tuned BLEU Scores

Model	Science	Education	Improvement (%)
mBART	0.1997	0.1192	+63.28% (Sci)
M2M100	0.1200	0.0809	+419.48% (Sci)

LoRA vs Layer Freezing Performance

Model	Domain	Fine-Tuned BLEU	LoRA BLEU	Layer Freezing BLEU
mBART	Science	0.1997	0.1352	0.1597
mBART	Education	0.1192	0.1153	0.1178
M2M100	Science	0.1200	0.0976	0.1118
M2M100	Education	0.0809	0.0782	N/A

Key Insights:
✅ Fine-tuning achieved the highest BLEU scores.
✅ Layer Freezing performed better than LoRA across models.
✅ LoRA is more efficient, but sacrifices some translation quality.

⸻

⚡ GPU Usage Analysis

Memory consumption on NVIDIA A100 (40GB VRAM)

Method	mBART (GB)	M2M100 (GB)
Fine-Tuning	7.0	5.5
LoRA	2.0	2.0
Layer Freezing	4.5	3.5

Key Observations:
✔ LoRA is the most memory-efficient, making it ideal for low-resource scenarios.
✔ Layer Freezing reduces memory usage while maintaining decent BLEU scores.
✔ Fine-Tuning achieves the best results but is computationally expensive.

⸻

❗ Error Analysis

We categorized errors into Word-Level, Structural, and Other Errors.

Common Issues Identified

Model	Word-Level Errors	Structural Errors
M2M100 (LoRA)	3,960	2,057
M2M100 (Fine-Tuned)	3,884	2,085
mBART (LoRA)	~3,250	~1,300
mBART (Fine-Tuned)	~3,250	~1,300



⸻

🏆 Conclusion & Recommendations

✅ Best Overall Performance: Fine-Tuned mBART (Highest BLEU Score)
⚡ Best Resource-Efficient Model: LoRA M2M100 (Low GPU Usage, Competitive BLEU)
🔬 Best Balance of Efficiency & Quality: Layer Freezing

Final Takeaways:
	•	For high-quality translation: Use fully fine-tuned models.
	•	For low-resource deployment: LoRA is highly efficient, but may sacrifice some translation accuracy.
	•	For an optimal trade-off: Layer Freezing provides a good balance between performance and efficiency.

Future Work
	•	Hybrid techniques: Combining LoRA with Layer Freezing.
	•	Improved quantization methods: Exploring 8-bit and 4-bit models.
	•	Dataset expansion: Using out-of-domain data to enhance robustness.

⸻

🎓 Contributors & Acknowledgments

This project was developed as part of CIS5300 at University of Pennsylvania.
📖 Authors: Xuanyou Liu, Prekshi Vyas, Raksha Ramesh, Manurag Khullar.

Special thanks to:
👨‍🏫 Professor Mark Yatskar (Instructor)
🧑‍🏫 Ugurcan Vurgun (TA & Mentor)

⸻

📜 References

📌 Main Papers & Resources:
	•	Hu et al. “LoRA: Low-Rank Adaptation of Large Language Models” (ICLR 2022)
	•	Papineni et al. “BLEU: Automatic Evaluation of Machine Translation” (ACL 2002)
	•	Tian et al. “UM-Corpus: A Large English-Chinese Parallel Corpus” (LREC 2014)

⸻

💡 If you found this helpful, give it a ⭐ on GitHub! 🚀
Let us know your thoughts and suggestions in the Issues section.

⸻

This improved Markdown enhances readability, introduces tables, sections, and highlights key findings effectively. Let me know if you need further tweaks! 🚀
