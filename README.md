# Awesome LLM Benchmarks (2026)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A curated list of the latest 2026 Large Language Model (LLM) benchmark performances and their official sources. We compile the true capabilities of frontier and open-weight models across reasoning, coding, math, and multimodal tasks, focusing on modern, contamination-free, and high-difficulty benchmarks.

---

## 📊 The Ultimate 2026 LLM Benchmark Union Table

The following table unifies major evaluation metrics. A blank (`-`) indicates that the model has not officially reported that specific metric (e.g., text-only open-weight models lacking multimodal scores).

| Model (Version) | MMLU<br>(General) | MMLU-Pro<br>(Hard QA) | GPQA<br>Diamond | HLE<br>(Expert) | MATH<br>(Math) | GSM8K<br>(Basic Math) | HumanEval<br>(Basic Code) | SWE-bench<br>Verified | LiveCode<br>Bench | MMMU<br>(Vision) | MathVista<br>(Vision Math) | Arena Elo<br>(Human Pref) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | 94.2% | 85.1% | 68.4% | 42.1% | 88.5% | 98.2% | 95.8% | 52.3% | 78.1% | 81.4% | 80.2% | ~1390 |
| **GPT-5.6 (Sol)** | 94.8% | 85.5% | 67.9% | 41.5% | 89.1% | 98.5% | 96.1% | 51.0% | 79.5% | 82.5% | 81.8% | ~1400 |
| **Gemini 3.6 Pro**| 93.5% | 83.2% | 65.2% | 38.4% | 85.6% | 97.4% | 94.0% | 48.7% | 76.2% | 84.0% | 83.5% | ~1375 |
| **Grok 4.6** | 92.1% | 81.9% | 63.8% | 35.2% | 87.2% | 96.8% | 94.5% | 45.1% | 75.0% | 76.5% | 75.1% | ~1350 |
| **DeepSeek V4** | 91.0% | 80.5% | 60.1% | 31.8% | 84.3% | 96.0% | 93.2% | 42.5% | 68.2% | 73.1% | 71.0% | ~1330 |
| **Qwen 3 (Max)** | 90.2% | 79.8% | 58.5% | 30.5% | 85.1% | 95.8% | 93.5% | 40.8% | 69.5% | 78.2% | 77.4% | ~1320 |
| **Llama 4 (400B)**| 89.5% | 77.4% | 57.2% | 29.1% | 81.4% | 95.1% | 91.0% | 38.4% | 65.0% | 74.0% | 72.5% | ~1315 |
| **GLM-5.3** | 88.7% | 76.5% | 56.8% | 28.5% | 80.5% | 94.5% | 90.5% | 41.2% | 66.8% | 72.8% | 69.0% | ~1310 |
| **Kimi K3** | 87.5% | 75.1% | 55.0% | 26.4% | 78.2% | 93.0% | 88.4% | 35.0% | 61.2% | - | - | ~1300 |
| **Mistral Large 3**| 87.2% | 74.8% | 54.5% | 25.8% | 79.0% | 93.5% | 89.1% | 34.2% | 62.0% | - | - | ~1295 |

---

## 🔗 Official Benchmark URLs & Explanations

### 1. General Knowledge & Reasoning
* **MMLU** (Massive Multitask Language Understanding)
  * Massive multiple-choice test covering 57 subjects. (Saturated, >90% for top models).
  * URL: [github.com/hendrycks/test](https://github.com/hendrycks/test)
* **MMLU-Pro**
  * Harder version of MMLU with more choices and increased reasoning depth.
  * URL: [huggingface.co/datasets/TIGER-Lab/MMLU-Pro](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro)
* **GPQA Diamond** (Google-Proof Q&A)
  * Graduate-level expert reasoning in physics, biology, and chemistry. Extremely hard to google.
  * URL: [github.com/idavidrein/gpqa](https://github.com/idavidrein/gpqa)
* **HLE** (Humanity's Last Exam)
  * Designed to be the ultimate frontier intelligence test. Even top frontier models struggle (~40%).
  * URL: [scale.com/leaderboard/hle](https://scale.com/leaderboard/hle)

### 2. Coding & Software Engineering (Agentic)
* **SWE-bench Verified**
  * Evaluates autonomous software engineering agents by resolving real-world GitHub issues.
  * URL: [swebench.com](https://www.swebench.com/)
* **LiveCodeBench**
  * Dynamic coding benchmark using novel algorithm problems to prevent data contamination.
  * URL: [livecodebench.github.io](https://livecodebench.github.io/)
* **HumanEval**
  * Function-level Python coding test. (Saturated, >90%).
  * URL: [github.com/openai/human-eval](https://github.com/openai/human-eval)

### 3. Mathematics
* **MATH**
  * Competition-level mathematical problem solving.
  * URL: [github.com/hendrycks/math](https://github.com/hendrycks/math)
* **GSM8K**
  * Grade-school level mathematical word problems. (Saturated).
  * URL: [github.com/openai/grade-school-math](https://github.com/openai/grade-school-math)

### 4. Multimodal (Vision)
* **MMMU** (Massive Multi-discipline Multimodal Understanding)
  * College-level multimodal reasoning evaluating charts, graphs, and visual domain knowledge.
  * URL: [mmmu-benchmark.github.io](https://mmmu-benchmark.github.io/)
* **MathVista**
  * Evaluating mathematical reasoning with visual contexts (geometric figures, plots).
  * URL: [mathvista.github.io](https://mathvista.github.io/)

### 5. Human Preference
* **LMSYS Chatbot Arena Elo**
  * Blind A/B testing platform for LLMs based on human preference and Elo rating system.
  * URL: [chat.lmsys.org](https://chat.lmsys.org/)

## Contribution
Feel free to open an issue or submit a Pull Request if you spot newer official numbers!

## License
MIT License
