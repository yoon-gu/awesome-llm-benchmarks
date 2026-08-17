# Awesome LLM Benchmarks (2026)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

2026년 최신 LLM(대형 언어 모델)의 벤치마크 성능과 공식 출처를 모아둔 저장소입니다. 최근 AI 업계에서 가장 중요시되는 **자율 에이전트(Agentic)** 성능을 필두로, 추론, 코딩, 수학, 비전 등 전 분야에 걸쳐 프론티어(Frontier) 모델과 오픈웨이트(Open-Weight) 모델의 실질적인 성능을 오염 방지(Contamination-free) 및 고난도 지표 중심으로 간결하게 정리했습니다.

---

## 📊 2026 통합 LLM 벤치마크 표

빈칸(`-`)은 텍스트 전용 모델이거나 해당 지표를 공식 발표하지 않았음을 의미합니다.

| 모델 (버전) | 출시일 | SWE-bench<br>Verified | LiveCode<br>Bench | HumanEval<br>(기본코딩) | GPQA<br>Diamond | HLE<br>(최고난이도) | MMLU<br>(일반지식) | MMLU-Pro<br>(심화지식) | MATH<br>(심화수학) | GSM8K<br>(기본수학) | MMMU<br>(전공비전) | MathVista<br>(비전수학) | Arena Elo<br>(인간선호) |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | '26. 7월 | **52.3%** | 78.1% | 95.8% | 68.4% | 42.1% | 94.2% | 85.1% | 88.5% | 98.2% | 81.4% | 80.2% | ~1390 |
| **GPT-5.6 (Sol)** | '26. 6월 | 51.0% | **79.5%** | **96.1%** | 67.9% | 41.5% | **94.8%** | **85.5%** | **89.1%** | **98.5%** | 82.5% | 81.8% | **~1400** |
| **Gemini 3.6 Pro**| '26. 5월 | 48.7% | 76.2% | 94.0% | 65.2% | 38.4% | 93.5% | 83.2% | 85.6% | 97.4% | **84.0%** | **83.5%** | ~1375 |
| **Grok 4.6** | '26. 8월 | 45.1% | 75.0% | 94.5% | 63.8% | 35.2% | 92.1% | 81.9% | 87.2% | 96.8% | 76.5% | 75.1% | ~1350 |
| **DeepSeek V4** | '26. 3월 | 42.5% | 68.2% | 93.2% | 60.1% | 31.8% | 91.0% | 80.5% | 84.3% | 96.0% | 73.1% | 71.0% | ~1330 |
| **Qwen 3 (Max)** | '26. 4월 | 40.8% | 69.5% | 93.5% | 58.5% | 30.5% | 90.2% | 79.8% | 85.1% | 95.8% | 78.2% | 77.4% | ~1320 |
| **Llama 4 (400B)**| '26. 7월 | 38.4% | 65.0% | 91.0% | 57.2% | 29.1% | 89.5% | 77.4% | 81.4% | 95.1% | 74.0% | 72.5% | ~1315 |
| **GLM-5.3** | '26. 7월 | 41.2% | 66.8% | 90.5% | 56.8% | 28.5% | 88.7% | 76.5% | 80.5% | 94.5% | 72.8% | 69.0% | ~1310 |
| **Kimi K3** | '26. 5월 | 35.0% | 61.2% | 88.4% | 55.0% | 26.4% | 87.5% | 75.1% | 78.2% | 93.0% | - | - | ~1300 |
| **Mistral Large 3**| '26. 6월 | 34.2% | 62.0% | 89.1% | 54.5% | 25.8% | 87.2% | 74.8% | 79.0% | 93.5% | - | - | ~1295 |

---

## 🔗 벤치마크 공식 URL 및 설명

### 1. 코딩 & 에이전트 (Coding & Agentic) - 🔥 핵심 지표
* **SWE-bench Verified**: 실제 GitHub 버그와 이슈를 자율 에이전트가 완벽히 수정하는지 평가. [swebench.com](https://www.swebench.com/)
* **LiveCodeBench**: 최신 알고리즘 출제로 데이터 오염을 차단한 동적 코딩 벤치마크. [livecodebench.github.io](https://livecodebench.github.io/)
* **HumanEval**: 함수 단위의 기초 파이썬 코딩 능력 평가. [github.com/openai/human-eval](https://github.com/openai/human-eval)

### 2. 지식 & 추론 (Knowledge & Reasoning)
* **GPQA Diamond**: 물리/화학/생물 등 박사급 초고난도 객관식 추론 평가. [github.com/idavidrein/gpqa](https://github.com/idavidrein/gpqa)
* **HLE (Humanity's Last Exam)**: 가장 까다롭게 설계된 최상위 지능 테스트. [scale.com/leaderboard/hle](https://scale.com/leaderboard/hle)
* **MMLU**: 57개 학문 분야 객관식 지식 평가 (최상위 90% 돌파로 변별력 감소). [github.com/hendrycks/test](https://github.com/hendrycks/test)
* **MMLU-Pro**: 선택지가 10개로 늘어나고 난이도가 높아진 심화 추론 지식 테스트. [huggingface.co/datasets/TIGER-Lab/MMLU-Pro](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro)

### 3. 수학 (Mathematics)
* **MATH**: 경시대회 수준의 중고급 수학 문제 해결력 평가. [github.com/hendrycks/math](https://github.com/hendrycks/math)
* **GSM8K**: 초등학교 수준의 다단계 수학 문장제. [github.com/openai/grade-school-math](https://github.com/openai/grade-school-math)

### 4. 멀티모달 (비전)
* **MMMU**: 도표, 악보 등 대학 전공 수준의 시각 자료 이해도 평가. [mmmu-benchmark.github.io](https://mmmu-benchmark.github.io/)
* **MathVista**: 기하학 도형, 그래프 등 시각적 수학 추론 문제 평가. [mathvista.github.io](https://mathvista.github.io/)

### 5. 체감 성능 (Human Preference)
* **LMSYS Chatbot Arena Elo**: 실제 사용자들의 블라인드 투표로 랭킹을 매기는 체감 성능 지표. [chat.lmsys.org](https://chat.lmsys.org/)

## 기여(Contribution)
새로운 벤치마크 수치가 발표되면 Issue나 Pull Request를 남겨주세요!

## 라이선스
MIT License
