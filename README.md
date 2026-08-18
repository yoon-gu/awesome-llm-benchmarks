# Awesome LLM Benchmarks — Frontier Models

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Anthropic, OpenAI, Google, xAI의 최신 프론티어 모델 4개만 추적합니다. **2026-08-19 (KST)** 기준으로 공식 모델 카드·시스템 카드·기술 평가 문서·발표 페이지를 Browser에서 처음부터 다시 열어 확인했습니다.

`-`는 0점이 아니라, 조사한 공식 원문에서 **같은 모델·같은 benchmark variant**의 수치를 찾지 못했다는 뜻입니다. 서로 다른 버전, subset, 도구, agent scaffold, 추론 강도는 한 값으로 합치지 않습니다.

## 추적 모델과 공식 원문

| 제공사 | 정확한 모델 | 공개일 | Browser에서 확인한 1차 출처 |
| :--- | :--- | :---: | :--- |
| Anthropic | **Claude Opus 5** (`claude-opus-5`) | 2026-07-24 | [발표](https://www.anthropic.com/news/claude-opus-5) · [System Card](https://www.anthropic.com/claude-opus-5-system-card) |
| OpenAI | **GPT-5.6 Sol** (`gpt-5.6-sol`) | 2026-07-09<sup>1</sup> | [발표·평가표](https://openai.com/index/gpt-5-6/) · [System Card](https://deploymentsafety.openai.com/gpt-5-6) · [API 모델 문서](https://developers.openai.com/api/docs/models/gpt-5.6-sol) |
| Google | **Gemini 3.1 Pro Preview** (`gemini-3.1-pro-preview`) | 2026-02-19 | [Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) · [평가 방법론 PDF](https://storage.googleapis.com/deepmind-media/gemini/gemini_3-1_pro_model_evaluation.pdf) |
| xAI | **Grok 4.6** (`grok-4.6`) | 2026-08-12 | [공식 발표·평가표](https://x.ai/news/grok-4-6) · [모델 문서](https://docs.x.ai/developers/models/grok-4.6) |

<sup>1</sup> GPT-5.6 Sol은 [2026-06-26 limited preview](https://openai.com/index/previewing-gpt-5-6-sol/) 후 2026-07-09 GA 및 System Card 공개.

## 코딩·에이전트·컴퓨터 사용

Terminal-Bench는 모델별로 공식 보고된 버전이 다르므로 셀에 버전을 표시합니다. OpenAI 발표의 OSWorld 2.0 행은 Binary/Partial 등 세부 metric을 명시하지 않아 임의로 보충하지 않았습니다.

| 모델 | SWE-bench Verified | SWE-bench Pro | DeepSWE 1.1 | Terminal-Bench | OSWorld 2.0 | BrowseComp |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | **96.0%**<br><sub>5회 평균</sub> | **79.2%**<br><sub>5회 평균</sub> | **68.8%**<br><sub>5회 평균</sub> | - | **70.57%**<br><sub>success@1 · 5회</sub> | **90.8%**<br><sub>tools · 10M-token budget</sub> |
| **GPT-5.6 Sol** | - | **64.6%**<br><sub>설정 미공개</sub> | **72.7%**<br><sub>설정 미공개</sub> | **88.8%**<br><sub>v2.1 · 설정 미공개</sub> | **62.6%**<br><sub>metric·설정 미공개</sub> | **90.4%**<br><sub>설정 미공개</sub> |
| **Gemini 3.1 Pro Preview** | **80.6%**<br><sub>10회 · corrected harness</sub> | **54.2%**<br><sub>Public · 5회</sub> | - | **68.5%**<br><sub>v2.0 · Terminus-2</sub> | - | **85.9%**<br><sub>Search+Python+Browse</sub> |
| **Grok 4.6 High** | - | - | **65.9%**<br><sub>설정 미공개</sub> | **26.0%**<br><sub>v3.0 · 설정 미공개</sub> | - | - |

## 지식·추론·장문·전문 작업

| 모델 | GPQA Diamond | Humanity's Last Exam | MMMU-Pro | ARC-AGI-2 | GDPval-AA v2 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | - | **56.3%** <sub>no tools</sub><br>**64.7%** <sub>tools</sub> | - | **90.42%**<br><sub>max · ARC Prize verified</sub> | **1861 Elo**<br><sub>v2 · max</sub> |
| **GPT-5.6 Sol** | **94.6%**<br><sub>설정 미공개</sub> | - | **83.0%** <sub>no tools</sub><br>**84.6%** <sub>tools</sub> | - | **1747.8 Elo**<br><sub>v2</sub> |
| **Gemini 3.1 Pro Preview** | **94.3%**<br><sub>Thinking High · no tools</sub> | **44.4%** <sub>full text+MM · no tools</sub><br>**51.4%** <sub>full text+MM · Search+Code</sub> | **80.5%**<br><sub>no tools</sub> | **77.1%**<br><sub>ARC Prize verified</sub> | - |
| **Grok 4.6 High** | - | - | - | - | **1753 Elo**<br><sub>v2 · 설정 미공개</sub> |

## 모델 카드의 추가 공식 결과

공통 열에 억지로 맞추지 못하는 정확한 version·subset은 아래에 그대로 보존합니다. `%`가 없는 값은 원문 단위(Elo, index, IoU 등)를 유지했습니다.

| 모델 | 추가로 확인한 공식 결과 |
| :--- | :--- |
| **Claude Opus 5** | SWE-bench Multilingual **89.5%**; SWE-bench Multimodal **59.4%**; FrontierCode 1.1 Main **53.4%**; FrontierBench v0.1 **43.3%**; ARC-AGI-1 **97.50%**; ARC-AGI-3 high **30.16%**; HealthBench Professional length-adjusted **59.8%** / raw **73.4%**; AA-Briefcase **1720 Elo**; AutomationBench **26.0%**; MCP Atlas **85.8%**; Toolathlon-Verified Pass@1 **80.6%** / Pass@3 **87.0%** / Pass³ **73.1%**; Chartography no-tools **29.6%** / tools **83.0%**; BenchCAD Vision2Code voxel IoU no-tools **0.366** / tools **0.821**; Harvey open-source Legal Agent Benchmark all-pass **23.58%±0.48** / criterion **93.74%** <sub>production safeguards · Opus 4.8 fallback 가능</sub>. |
| **GPT-5.6 Sol** | Agents' Last Exam 표 **52.7%**<sup>2</sup>; AA Intelligence Index v4.1 **58.9**; AA Coding Agent Index v1.1 **80**; Management Consulting Tasks **43.2%**; Big Finance Bench **53%**; HealthBench Professional **60.5%** length-adjusted; GeneBench-Pro **28.7%**; LifeSciBench **59.9%**; MedChemBench internal **48.3%**; BenchCAD **70.6%** / Python tool **83.4%**; Capture-the-Flag **96.7%**; SEC-Bench Pro **71.2%**; ExploitBench **73.5%**; ExploitGym 6h **33.7%**; AutomationBench **18.1%**; Toolathlon **58%**; ARC-AGI-3 **7.78%**; FrontierMath T1–3 v2 **89%** / T4 v2 **83%**; gdp.pdf **30.7%**; Internal Research Debugging **68.3%**; KernelGen1P **61.1%**; NanoGPT **9.69%**; PostTrainBench Lite **50.3%**; RSI Index **57.9%**; OpenAI MRCR v2 8-needle 256K–512K **91.5%** / 512K–1M **73.8%**; GraphWalks BFS 256K F1 **90.7%** / 1M F1 **77.1%**. |
| **Gemini 3.1 Pro Preview** | GDPval-AA <sub>version 미표기</sub> **1317 Elo**; MMMLU **92.6%**; τ² Retail **90.8%** / Telecom **99.3%**; MCP Atlas **69.2%**; APEX-Agents **33.5%**; LiveCodeBench Pro **2887 Elo**; SciCode **59%**; MRCR v2 8-needle 128K cumulative average **84.9%** / 1M pointwise **26.3%**. |
| **Grok 4.6 High** | Artificial Analysis Intelligence Index **61**; CursorBench v3.2 **69.9%**; FrontierCode v1.1 Extended **61.3%**; APEX-Agents **57.5%**; APEX-SWE **56.4%**; AA-Briefcase **1577 Elo**. |

<sup>2</sup> OpenAI의 같은 발표 페이지는 본문에서 **53.6**, 비교표에서 **52.7%**를 표시하지만 설정 차이를 설명하지 않습니다. 구조화된 비교표의 Sol 열 값을 기록하고 충돌을 [SOURCES.md](./SOURCES.md)에 남겼습니다.

## 확인 통계

- 공식 모델 원문 Browser 접근: **4/4 모델 확인 가능**.
- 공통 비교 행렬: **27/44셀(61.36%) 확인**, **17/44셀(38.64%) 미확인**.
- 값이 하나도 없는 benchmark 열은 제거했습니다.
- 추가 결과는 version·subset이 달라 공통 행렬 통계에서 제외했습니다.

120B 이하 공개 가중치 모델 15개는 [small_models_2026.md](./small_models_2026.md), 각 수치의 고정 URL·설정·판정은 [SOURCES.md](./SOURCES.md)에서 확인할 수 있습니다.

## 기여

새 수치를 추가할 때는 정확한 모델 ID, benchmark version, metric, tools/scaffold, 시행 횟수와 모델 제공사 또는 benchmark 운영자의 공식 URL을 함께 남겨 주세요.

## 라이선스

MIT License
