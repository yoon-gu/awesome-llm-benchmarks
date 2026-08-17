# Awesome LLM Benchmarks (2026)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

2026년 최신 LLM(대형 언어 모델)의 벤치마크 성능과 공식 출처를 모아둔 저장소입니다. 최근 AI 업계에서 가장 중요시되는 **자율 에이전트(Agentic)** 성능을 필두로, 분야별(에이전트, 추론, 수학, 비전)로 프론티어(Frontier) 모델과 오픈웨이트(Open-Weight) 모델의 실질적인 성능을 오염 방지(Contamination-free) 및 고난도 지표 중심으로 간결하게 분리하여 정리했습니다.

---

## 🚀 1. 코딩 및 에이전트 성능 (Coding & Agentic Performance)

단순 코딩을 넘어 실제 웹 브라우징, 컴퓨터 OS 제어, 복잡한 툴 호출을 수행하는 최신 '자율 에이전트' 성능 지표들입니다. 빈칸(`-`)은 미발표/텍스트 전용 모델을 뜻합니다.

| 모델 (버전) | 출시일 | SWE-bench<br>Verified | GAIA<br>(범용비서) | OSWorld<br>(OS제어) | WebArena<br>(웹탐색) | Tau²-Bench<br>(규정준수) | BFCL<br>(툴호출) | LiveCode<br>Bench | HumanEval<br>(기본코딩) |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | '26. 7월 | **52.3%** | - | - | **61.8%** | - | - | - | - |
| **GPT-5.6 (Sol)** | '26. 6월 | - | **46.8%** | **36.5%** | - | **71.2%** | **93.8%** | **79.5%** | **96.1%** |
| **Gemini 3.6 Pro**| '26. 5월 | - | - | - | - | - | - | - | - |
| **Grok 4.6** | '26. 8월 | - | - | - | - | - | - | - | - |
| **DeepSeek V4** | '26. 3월 | - | - | - | - | - | - | - | - |
| **GLM-5.3** | '26. 7월 | - | - | - | - | - | - | - | - |
| **Qwen 3 (Max)** | '26. 4월 | - | - | - | - | - | - | - | - |
| **Llama 4 (400B)**| '26. 7월 | - | - | - | - | - | - | - | - |
| **Kimi K3** | '26. 5월 | - | - | - | - | - | - | - | - |
| **Mistral Large 3**| '26. 6월 | - | - | - | - | - | - | - | - |

---

## 🧠 2. 지식 및 추론 성능 (Knowledge & Reasoning Performance)

박사급 초고난도 추론 및 다방면의 일반 지식 평가입니다.

| 모델 (버전) | GPQA<br>Diamond | HLE<br>(최고난이도) | MMLU<br>(일반지식) | MMLU-Pro<br>(심화지식) |
| :--- | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | - | - | - | - |
| **GPT-5.6 (Sol)** | - | - | - | - |
| **Gemini 3.6 Pro**| - | - | - | - |
| **Grok 4.6** | - | - | - | - |
| **DeepSeek V4** | - | - | - | - |
| **Qwen 3 (Max)** | - | - | - | - |
| **Llama 4 (400B)**| - | - | - | - |
| **GLM-5.3** | - | - | - | - |
| **Kimi K3** | - | - | - | - |
| **Mistral Large 3**| - | - | - | - |

---

## 📐 3. 수학 및 비전 성능 (Math & Vision Performance)

심화 수학 문제 해결 능력과 대학 전공 수준의 시각(멀티모달) 이해도입니다. 빈칸(`-`)은 미발표/텍스트 전용 모델을 뜻합니다.

| 모델 (버전) | MATH<br>(심화수학) | GSM8K<br>(기본수학) | MMMU<br>(전공비전) | MathVista<br>(비전수학) |
| :--- | :---: | :---: | :---: | :---: |
| **GPT-5.6 (Sol)** | - | - | - | - |
| **Claude Opus 5** | - | - | - | - |
| **Grok 4.6** | - | - | - | - |
| **Gemini 3.6 Pro**| - | - | - | - |
| **Qwen 3 (Max)** | - | - | - | - |
| **DeepSeek V4** | - | - | - | - |
| **Llama 4 (400B)**| - | - | - | - |
| **GLM-5.3** | - | - | - | - |
| **Mistral Large 3**| - | - | - | - |
| **Kimi K3** | - | - | - | - |

---

## 🏆 4. 체감 성능 (Human Preference)

| 모델 (버전) | LMSYS Chatbot Arena Elo (추정치) |
| :--- | :---: |
| **GPT-5.6 (Sol)** | - |
| **Claude Opus 5** | - |
| **Gemini 3.6 Pro**| - |
| **Grok 4.6** | - |
| **DeepSeek V4** | - |
| **Qwen 3 (Max)** | - |
| **Llama 4 (400B)**| - |
| **GLM-5.3** | - |
| **Kimi K3** | - |
| **Mistral Large 3**| - |

---

## 🔗 벤치마크 공식 URL 및 설명

### 1. 코딩 & 에이전트 (Coding & Agentic)
* **SWE-bench Verified**: 실제 GitHub 버그와 이슈를 자율 에이전트가 완벽히 수정하는지 평가. [swebench.com](https://www.swebench.com/)
* **GAIA (General AI Assistants)**: 웹 브라우징, 도구 사용, 파일 분석 등 범용 AI 비서의 다단계 추론 및 문제 해결 평가. [huggingface.co/spaces/gaia-benchmark/leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)
* **OSWorld**: 멀티모달 에이전트가 실제 컴퓨터 운영체제(OS) 데스크톱 환경에서 마우스/키보드로 얼마나 태스크를 잘 수행하는지 평가. [osworld.github.io](https://osworld.github.io/)
* **WebArena**: 웹 브라우저 내비게이션, 폼 작성, 정보 검색 등 웹 기반 자율 에이전트 성능 평가. [webarena.dev](https://webarena.dev/)
* **Tau²-Bench**: 모의 사용자와 상호작용하며 특정 도메인(예: 리테일, 항공)의 규정과 정책(Policy)을 에이전트가 얼마나 엄격히 준수하는지 평가하는 최신 벤치마크. [github.com/sierra-research/tau-bench](https://github.com/sierra-research/tau-bench)
* **BFCL (Berkeley Function Calling Leaderboard)**: 에이전트의 핵심인 도구 호출(Function Calling/Tool Use) 정확도 종합 평가. [gorilla.cs.berkeley.edu/leaderboard.html](https://gorilla.cs.berkeley.edu/leaderboard.html)
* **LiveCodeBench**: 최신 알고리즘 출제로 데이터 오염을 차단한 동적 코딩 벤치마크. [livecodebench.github.io](https://livecodebench.github.io/)
* **HumanEval**: 함수 단위의 기초 파이썬 코딩 능력 평가. [github.com/openai/human-eval](https://github.com/openai/human-eval)

### 2. 지식 & 추론 (Knowledge & Reasoning)
* **GPQA Diamond**: 물리/화학/생물 등 박사급 초고난도 객관식 추론 평가. [github.com/idavidrein/gpqa](https://github.com/idavidrein/gpqa)
* **HLE (Humanity's Last Exam)**: 가장 까다롭게 설계된 최상위 지능 테스트. [scale.com/leaderboard/hle](https://scale.com/leaderboard/hle)
* **MMLU**: 57개 학문 분야 객관식 지식 평가 (최상위 90% 돌파로 변별력 감소). [github.com/hendrycks/test](https://github.com/hendrycks/test)
* **MMLU-Pro**: 선택지가 10개로 늘어나고 난이도가 높아진 심화 추론 지식 테스트. [huggingface.co/datasets/TIGER-Lab/MMLU-Pro](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro)

### 3. 수학 & 비전 (Math & Vision)
* **MATH**: 경시대회 수준의 중고급 수학 문제 해결력 평가. [github.com/hendrycks/math](https://github.com/hendrycks/math)
* **GSM8K**: 초등학교 수준의 다단계 수학 문장제. [github.com/openai/grade-school-math](https://github.com/openai/grade-school-math)
* **MMMU**: 도표, 악보 등 대학 전공 수준의 시각 자료 이해도 평가. [mmmu-benchmark.github.io](https://mmmu-benchmark.github.io/)
* **MathVista**: 기하학 도형, 그래프 등 시각적 수학 추론 문제 평가. [mathvista.github.io](https://mathvista.github.io/)

### 4. 인간 선호도 (Human Preference)
* **LMSYS Chatbot Arena Elo**: 실제 사용자들의 블라인드 투표로 랭킹을 매기는 체감 성능 지표. [chat.lmsys.org](https://chat.lmsys.org/)

---

---

## 📖 모델별 성능 데이터 출처 (Model Performance Sources)

각 셀에 기입된 벤치마크 수치들의 개별 출처(공식 기술 보고서, 리더보드 등)는 데이터 무결성을 위해 별도의 파일로 엄격하게 관리하고 있습니다. 상세한 출처 매핑 정보는 아래 문서를 참고해 주세요.

👉 **[SOURCES.md 문서 확인하기](./SOURCES.md)**

## 기여(Contribution)
새로운 벤치마크 수치가 발표되면 Issue나 Pull Request를 남겨주세요!

## 라이선스
MIT License
