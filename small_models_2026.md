# Open-Weight Models (≤120B Total Parameters, 2024–2026)

총 파라미터 120B 이하의 공개 가중치 모델을 정확한 체크포인트 기준으로 비교합니다. 원래 문서의 `Qwen 3 (72B)`는 공식 Qwen3 모델 목록에 존재하지 않아 제거했습니다. MoE 모델은 총 파라미터와 토큰당 활성 파라미터를 함께 표시합니다.

검증 기준일은 **2026-08-18 (KST)** 입니다. `-`는 0점이 아니라 동일 모델·지표·설정의 공신력 있는 수치를 확인하지 못했다는 뜻입니다.

---

## 🚀 1. 코딩 및 에이전트 성능 (Coding & Agentic Performance)

| 모델 (파라미터) | 출시일 | SWE-bench<br>Verified | GAIA | OSWorld 2.0 | WebArena | τ²-Bench | BFCL V4<br>Overall | LiveCodeBench | HumanEval |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **gpt-oss-120b**<br><sub>117B total / 5.1B active</sub> | '25. 8월 | **62.4%** <sub>vendor·high</sub><br>**26.0%** <sub>mini-SWE v1.7</sub> | - | - | - | - | - | - | - |
| **Gemma 3 27B-IT** | '25. 3월 | - | - | - | - | - | **29.47%**<br><sub>Prompt</sub> | - | **87.8%**<br><sub>0-shot pass@1</sub> |
| **Mistral Small 4**<br><sub>119B total / 6.5B active</sub> | '26. 3월 | - | - | - | - | - | - | - | - |
| **Llama 4 Scout 17B-16E Instruct**<br><sub>109B total / 17B active</sub> | '25. 4월 | **9.06%**<br><sub>mini-SWE v0.0.0</sub> | - | - | - | - | **28.13%**<br><sub>native FC</sub> | **32.8%**<br><sub>0-shot pass@1</sub> | - |
| **Phi-4 (14B)** | '24. 12월 | - | - | - | - | - | **28.79%**<br><sub>Prompt</sub> | - | **82.6%**<br><sub>pass@1</sub> |
| **Qwen3-8B (Thinking)** | '25. 4월 | - | - | - | - | - | **42.57%**<br><sub>native FC</sub> | **57.5%**<br><sub>v5 · Thinking</sub> | - |

---

## 🧠 2. 지식 및 추론 성능 (Knowledge & Reasoning Performance)

| 모델 (파라미터) | GPQA Diamond | HLE | MMLU | MMLU-Pro |
| :--- | :---: | :---: | :---: | :---: |
| **gpt-oss-120b** | **80.1%** <sub>no tools</sub><br>**80.9%** <sub>tools</sub> | **14.9%** <sub>no tools</sub><br>**19.0%** <sub>tools</sub> | **90.0%**<br><sub>high reasoning</sub> | - |
| **Gemma 3 27B-IT** | **42.4%**<br><sub>0-shot CoT</sub> | - | **76.9%**<br><sub>0-shot</sub> | **67.5%**<br><sub>0-shot CoT</sub> |
| **Mistral Small 4**<br><sub>119B total / 6.5B active</sub> | **71.2%**<br><sub>reasoning high</sub> | - | - | **78.0%**<br><sub>reasoning high</sub> |
| **Llama 4 Scout 17B-16E Instruct** | **57.2%**<br><sub>0-shot</sub> | - | - | **74.3%**<br><sub>0-shot</sub> |
| **Phi-4 (14B)** | **56.1%**<br><sub>simple-evals</sub> | - | **84.8%**<br><sub>simple-evals</sub> | **70.4%**<br><sub>internal eval</sub> |
| **Qwen3-8B (Thinking)** | **62.0%**<br><sub>10회 sample 평균</sub> | - | - | - |

---

## 📐 3. 수학 및 비전 성능 (Math & Vision Performance)

| 모델 (파라미터) | MATH | GSM8K | MMMU | MathVista |
| :--- | :---: | :---: | :---: | :---: |
| **gpt-oss-120b** | - | - | - | - |
| **Gemma 3 27B-IT** | **89.0%**<br><sub>0-shot</sub> | **95.9%**<br><sub>0-shot CoT</sub> | **64.9%**<br><sub>val</sub> | **67.6%**<br><sub>testmini</sub> |
| **Mistral Small 4**<br><sub>119B total / 6.5B active</sub> | - | - | - | - |
| **Llama 4 Scout 17B-16E Instruct** | - | - | **69.4%**<br><sub>0-shot</sub> | **70.7%**<br><sub>0-shot</sub> |
| **Phi-4 (14B)** | **80.4%**<br><sub>simple-evals</sub> | - | - | - |
| **Qwen3-8B (Thinking)** | - | - | - | - |

---

## 🏆 4. 인간 선호도 (Human Preference)

Arena **Text Overall / Style Control** 2026-08-12 스냅샷 rating을 반올림했습니다.

| 모델 (정확한 Arena key 기준) | Arena rating |
| :--- | :---: |
| **gpt-oss-120b** | **1352** |
| **Gemma 3 27B-IT** | **1366** |
| **Mistral Small 4**<br><sub>119B total / 6.5B active</sub> | - |
| **Llama 4 Scout 17B-16E Instruct** | **1322** |
| **Phi-4 (14B)** | **1256** |
| **Qwen3-8B (Thinking)** | - |

---

## 📖 모델별 성능 데이터 출처

각 숫자의 정확한 지표, 평가 설정, 공식 URL과 근거 유형은 [SOURCES.md](./SOURCES.md)에 기록합니다. 프론티어 모델 표는 [README.md](./README.md)에서 확인할 수 있습니다.

## 기여

새 수치를 추가할 때는 모델 변형, 벤치마크 버전, 평가 설정과 숫자가 함께 표시된 공식 URL을 포함해 주세요.

## 라이선스

MIT License
