# 2026 Open-Weight Models (< 120B) Benchmarks

이 문서는 2026년에 출시된 **120B(1200억 개) 파라미터 미만**의 고성능 오픈웨이트(Open-Weight) 모델들을 집중 분석한 자료입니다. 단일 GPU(예: 80GB H100) 환경에서도 구동 가능하여 로컬 호스팅 및 실무 적용에 가장 많이 쓰이는 '실속형' 프론티어 모델들을 다룹니다.

---

## 🚀 1. 코딩 및 에이전트 성능 (Coding & Agentic Performance)

| 모델 (파라미터) | 출시일 | SWE-bench<br>Verified | GAIA | OSWorld | WebArena | Tau²-Bench | BFCL | LiveCode<br>Bench | HumanEval |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **gpt-oss-120b (117B)** | '26. 8월 | - | - | - | - | - | - | - | - |
| **Qwen 3 (72B)** | '26. 4월 | - | - | - | - | - | - | - | - |
| **Gemma 3 (27B)** | '26. 2월 | - | - | - | - | - | - | - | - |
| **Mistral Small 4 (24B)** | '26. 6월 | - | - | - | - | - | - | - | - |
| **Llama 4 Scout (17B)** | '26. 7월 | - | - | - | - | - | - | - | - |
| **Phi-4 (14B)** | '26. 1월 | - | - | - | - | - | - | - | - |
| **Qwen 3 (8B)** | '26. 4월 | - | - | - | - | - | - | - | - |

---

## 🧠 2. 지식 및 추론 성능 (Knowledge & Reasoning Performance)

| 모델 (파라미터) | GPQA<br>Diamond | HLE<br>(최고난이도) | MMLU | MMLU-Pro |
| :--- | :---: | :---: | :---: | :---: |
| **gpt-oss-120b (117B)** | - | - | - | - |
| **Qwen 3 (72B)** | - | - | - | - |
| **Gemma 3 (27B)** | - | - | - | - |
| **Mistral Small 4 (24B)**| - | - | - | - |
| **Llama 4 Scout (17B)** | - | - | - | - |
| **Phi-4 (14B)** | - | - | - | - |
| **Qwen 3 (8B)** | - | - | - | - |

---

## 📐 3. 수학 및 비전 성능 (Math & Vision Performance)

| 모델 (파라미터) | MATH | GSM8K | MMMU | MathVista |
| :--- | :---: | :---: | :---: | :---: |
| **gpt-oss-120b (117B)** | - | - | - | - |
| **Qwen 3 (72B)** | - | - | - | - |
| **Gemma 3 (27B)** | - | - | - | - |
| **Mistral Small 4 (24B)**| - | - | - | - |
| **Llama 4 Scout (17B)** | - | - | - | - |
| **Phi-4 (14B)** | - | - | - | - |
| **Qwen 3 (8B)** | - | - | - | - |

---

## 🏆 4. 체감 성능 (Human Preference)

| 모델 (파라미터) | LMSYS Chatbot Arena Elo (추정치) |
| :--- | :---: |
| **gpt-oss-120b (117B)** | - |
| **Qwen 3 (72B)** | - |
| **Gemma 3 (27B)** | - |
| **Mistral Small 4 (24B)**| - |
| **Llama 4 Scout (17B)** | - |
| **Phi-4 (14B)** | - |
| **Qwen 3 (8B)** | - |

---

## 📖 모델별 성능 데이터 출처 (Model Performance Sources)

각 셀에 기입된 벤치마크 수치들의 개별 출처(공식 기술 보고서, 리더보드 등)는 데이터 무결성을 위해 별도의 파일로 엄격하게 관리하고 있습니다. 상세한 출처 매핑 정보는 아래 문서를 참고해 주세요.

👉 **[SOURCES.md 문서 확인하기](./SOURCES.md)**

## 기여(Contribution)
새로운 벤치마크 수치가 발표되면 Issue나 Pull Request를 남겨주세요!

## 라이선스
MIT License
