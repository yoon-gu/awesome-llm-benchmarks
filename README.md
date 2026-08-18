# Awesome LLM Benchmarks (2025–2026 검증판)

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

공식 벤치마크 운영자 리더보드와 모델 제공사의 공식 시스템 카드·기술 보고서에서 직접 확인한 LLM 성능값을 정리합니다. **검증 기준일은 2026-08-18 (KST)** 입니다.

`-`는 0점이 아니라 동일한 모델·벤치마크·평가 설정의 공개 수치를 확인하지 못했다는 뜻입니다. 같은 열에서도 하네스, 도구 사용, 시행 횟수, 추론 강도가 다를 수 있으므로 셀의 짧은 설정 표기와 [SOURCES.md](./SOURCES.md)를 함께 확인해 주세요.

---

## 🚀 1. 코딩 및 에이전트 성능 (Coding & Agentic Performance)

| 모델 (정확한 버전) | 출시일 | SWE-bench<br>Verified | GAIA | OSWorld 2.0 | WebArena | τ²-Bench | BFCL V4 | LiveCodeBench | HumanEval |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | '26. 7월 | **96.0%**<br><sub>vendor · 5회 평균</sub> | - | **70.6%**<br><sub>success@1</sub> | - | - | - | - | - |
| **GPT-5.6 Sol** | '26. 7월 | - | - | **62.6%**<br><sub>Partial reward</sub> | - | - | - | - | - |
| **Gemini 3.1 Pro Preview** | '26. 2월 | **80.6%**<br><sub>Thinking High · 1회</sub> | - | - | - | **Retail 90.8%**<br>**Telecom 99.3%** | - | - | - |
| **Grok 4.6** | '26. 8월 | - | - | - | - | - | - | - | - |
| **DeepSeek-V4-Pro (Max)** | '26. 4월<sub> preview</sub> | **80.6%**<br><sub>vendor harness</sub> | - | - | - | - | - | **93.5%**<br><sub>v6 · pass@1-CoT</sub> | - |
| **GLM-5.3** | '26. 8월 | - | - | - | - | - | - | - | - |
| **Qwen3-Max-Thinking** | '26. 1월 | **75.3%**<br><sub>vendor harness</sub> | - | - | - | **82.1%**<br><sub>official setting</sub> | **67.7%**<br><sub>최대 100 turns</sub> | **85.9%**<br><sub>v6</sub> | - |
| **Llama 4 Maverick 17B-128E Instruct** | '25. 4월 | - | - | - | - | - | - | **43.4%**<br><sub>0-shot pass@1</sub> | - |
| **Kimi K3 (Max)** | '26. 7월 | - | - | - | - | - | - | - | - |
| **Mistral Large 3 Base (675B)** | '25. 12월 | - | - | - | - | - | - | - | - |
| **Mistral Large 3 Instruct (675B)** | '25. 12월 | - | - | - | - | - | - | - | - |

---

## 🧠 2. 지식 및 추론 성능 (Knowledge & Reasoning Performance)

HLE는 도구 사용 여부와 Full/Text subset을 셀에 표시합니다. 서로 다른 설정의 값은 직접 비교하면 안 됩니다.

| 모델 (정확한 버전) | GPQA Diamond | HLE | MMLU | MMLU-Pro |
| :--- | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | - | **56.3%** <sub>no tools</sub><br>**64.7%** <sub>tools</sub> | - | - |
| **GPT-5.6 Sol** | - | - | - | - |
| **Gemini 3.1 Pro Preview** | **94.3%**<br><sub>Thinking High · no tools</sub> | **44.4%** <sub>no tools</sub><br>**51.4%** <sub>Search+Code</sub> | - | - |
| **Grok 4.6** | - | - | - | - |
| **DeepSeek-V4-Pro (Max)** | **90.1%**<br><sub>pass@1</sub> | **37.7%** <sub>no tools</sub><br>**48.2%** <sub>tools</sub> | - | **87.5%**<br><sub>EM</sub> |
| **GLM-5.3** | - | **62.5%**<br><sub>with tools</sub> | - | - |
| **Qwen3-Max-Thinking** | - | **30.2%** <sub>text subset</sub><br>**49.8%** <sub>tools</sub> | - | **85.7%** |
| **Llama 4 Maverick 17B-128E Instruct** | **69.8%**<br><sub>0-shot</sub> | - | - | **80.5%**<br><sub>0-shot</sub> |
| **Kimi K3 (Max)** | **93.5%** | **43.5%** <sub>Full · no tools</sub><br>**56.0%** <sub>tools</sub> | - | - |
| **Mistral Large 3 Base (675B)** | **43.9%**<br><sub>5-shot · no CoT</sub> | - | - | - |
| **Mistral Large 3 Instruct (675B)** | - | - | - | - |

---

## 📐 3. 수학 및 비전 성능 (Math & Vision Performance)

| 모델 (정확한 버전) | MATH | GSM8K | MMMU | MathVista |
| :--- | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | - | - | - | - |
| **GPT-5.6 Sol** | - | - | - | - |
| **Gemini 3.1 Pro Preview** | - | - | - | - |
| **Grok 4.6** | - | - | - | - |
| **DeepSeek-V4-Pro (Max)** | - | - | - | - |
| **GLM-5.3** | - | - | - | - |
| **Qwen3-Max-Thinking** | - | - | - | - |
| **Llama 4 Maverick 17B-128E Instruct** | - | - | **73.4%**<br><sub>0-shot</sub> | **73.7%**<br><sub>0-shot</sub> |
| **Kimi K3 (Max)** | - | - | - | - |
| **Mistral Large 3 Base (675B)** | - | - | - | - |
| **Mistral Large 3 Instruct (675B)** | - | - | - | - |

---

## 🏆 4. 인간 선호도 (Human Preference)

아래 값은 Arena의 **Text Overall / Style Control** 2026-08-12 스냅샷 rating을 반올림한 값입니다. 고전적인 단일 “LMSYS Elo”로 해석하지 않습니다.

| 모델 (정확한 Arena key 기준) | Arena rating |
| :--- | :---: |
| **Claude Opus 5** | **1493** <sub>high</sub><br>**1489** <sub>max</sub> |
| **GPT-5.6 Sol** | **1481** <sub>xhigh</sub> |
| **Gemini 3.1 Pro Preview** | **1486** |
| **Grok 4.6** | **1464** <sub>high</sub> |
| **DeepSeek-V4-Pro (Max)** | - |
| **GLM-5.3** | - |
| **Qwen3-Max-Thinking** | - |
| **Llama 4 Maverick 17B-128E Instruct** | **1327** |
| **Kimi K3 (Max)** | **1489** |
| **Mistral Large 3 Base (675B)** | - |
| **Mistral Large 3 Instruct (675B)** | **1415** |

---

## 🔗 벤치마크 공식 URL 및 설명

### 코딩 & 에이전트

* **SWE-bench Verified**: 실제 GitHub 이슈 수정 평가. [공식 사이트](https://www.swebench.com/) · [운영자 실험 저장소](https://github.com/swe-bench/experiments)
* **GAIA**: 웹 탐색·도구 사용·파일 분석을 포함한 범용 비서 평가. [공식 리더보드](https://huggingface.co/spaces/gaia-benchmark/leaderboard) · [공개 결과 데이터](https://huggingface.co/datasets/gaia-benchmark/results_public)
* **OSWorld 2.0**: 실제 컴퓨터 작업 수행 평가. [공식 프로젝트](https://osworld-v2.xlang.ai/) · [공식 결과 JSON](https://osworld-v2.xlang.ai/static/data/leaderboard/official-results.json)
* **WebArena**: 실제 웹사이트 환경의 자율 에이전트 평가. [원 벤치마크](https://webarena.dev/og/) · [공식 리더보드](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ/edit?usp=sharing)
* **τ²-Bench**: 도메인 정책을 지키며 사용자와 상호작용하는 에이전트 평가. [공식 리더보드](https://taubench.com/leaderboard?benchmark=core) · [공식 저장소](https://github.com/sierra-research/tau2-bench)
* **BFCL V4**: 함수·도구 호출 정확도 평가. [공식 리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html) · [공식 결과 CSV](https://gorilla.cs.berkeley.edu/data_overall.csv)
* **LiveCodeBench**: 시간 순서로 오염을 줄인 동적 코딩 평가. [공식 리더보드](https://livecodebench.github.io/leaderboard.html) · [공식 결과 JSON](https://livecodebench.github.io/performances_generation.json)
* **HumanEval**: 함수 단위 Python 코딩 평가. [OpenAI 공식 저장소](https://github.com/openai/human-eval) — 공식 중앙 리더보드는 없습니다.

### 지식·추론·수학·비전

* **GPQA Diamond**: 박사급 과학 객관식 추론 평가. [공식 저장소](https://github.com/idavidrein/gpqa)
* **HLE (Humanity's Last Exam)**: 고난도 종합 지능 평가. [공식 프로젝트](https://lastexam.ai/)
* **MMLU / MMLU-Pro**: 다학문 일반 지식 및 심화 추론 평가. [MMLU](https://github.com/hendrycks/test) · [MMLU-Pro](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro)
* **MATH / GSM8K**: 수학 문제 해결 평가. [MATH](https://github.com/hendrycks/math) · [GSM8K](https://github.com/openai/grade-school-math)
* **MMMU / MathVista**: 대학 전공 시각 이해 및 시각 수학 추론 평가. [MMMU](https://mmmu-benchmark.github.io/) · [MathVista](https://mathvista.github.io/)
* **Arena Text Overall**: 사용자 블라인드 투표 기반 선호도 평가. [공식 Text 리더보드](https://arena.ai/leaderboard/text)

---

## 📖 모델별 성능 데이터 출처

각 숫자의 모델 변형, 지표, 도구 설정, 출처 유형과 확인 상태는 [SOURCES.md](./SOURCES.md)에 기록합니다. 120B 이하 오픈웨이트 모델 표는 [small_models_2026.md](./small_models_2026.md)에서 확인할 수 있습니다.

## 기여

새로운 수치를 추가할 때는 모델명과 점수가 함께 표시된 공식 URL, 벤치마크 버전, 평가 설정을 포함해 Issue 또는 Pull Request를 남겨 주세요.

## 라이선스

MIT License
