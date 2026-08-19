# Awesome LLM Benchmarks

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

최신 프론티어 모델 4개와 2026-04-01 이후 recent open-weight 모델 5개를 한 문서에서 추적합니다. gpt-oss-120b/20b는 출시 기간 밖의 참고 기준선으로 분리합니다. **2026-08-19 (KST)** 기준으로 공식 모델 카드·시스템 카드·기술 평가 문서·발표 페이지를 Browser에서 처음부터 다시 열어 확인했습니다.

`-`는 0점이 아니라, 조사한 공식 원문에서 **같은 모델·같은 benchmark variant**의 수치를 찾지 못했다는 뜻입니다. 서로 다른 버전, subset, 도구, agent scaffold, 추론 강도는 한 값으로 합치지 않습니다. `partial config`는 모델·benchmark·값은 확인되지만 shot, tools, pass@k, trials 또는 harness 일부가 공개되지 않았다는 뜻입니다.

<a id="frontier-models"></a>

## Frontier Models

### 추적 모델과 공식 원문

| 제공사 | 정확한 모델 | 공개일 | Browser에서 확인한 1차 출처 |
| :--- | :--- | :---: | :--- |
| Anthropic | **Claude Opus 5** (`claude-opus-5`) | 2026-07-24 | [발표](https://www.anthropic.com/news/claude-opus-5) · [System Card](https://www.anthropic.com/claude-opus-5-system-card) |
| OpenAI | **GPT-5.6 Sol** (`gpt-5.6-sol`) | 2026-07-09<sup>1</sup> | [발표·평가표](https://openai.com/index/gpt-5-6/) · [System Card](https://deploymentsafety.openai.com/gpt-5-6) · [API 모델 문서](https://developers.openai.com/api/docs/models/gpt-5.6-sol) |
| Google | **Gemini 3.1 Pro Preview** (`gemini-3.1-pro-preview`) | 2026-02-19 | [Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) · [평가 방법론 PDF](https://storage.googleapis.com/deepmind-media/gemini/gemini_3-1_pro_model_evaluation.pdf) |
| xAI | **Grok 4.6** (`grok-4.6`) | 2026-08-12 | [공식 발표·평가표](https://x.ai/news/grok-4-6) · [모델 문서](https://docs.x.ai/developers/models/grok-4.6) |

<sup>1</sup> GPT-5.6 Sol은 [2026-06-26 limited preview](https://openai.com/index/previewing-gpt-5-6-sol/) 후 2026-07-09 GA 및 System Card 공개.

### 공통 비교 — 코딩·에이전트·컴퓨터 사용

Terminal-Bench는 모델별로 공식 보고된 버전이 다르므로 셀에 버전을 표시합니다. OpenAI 발표의 OSWorld 2.0 행은 Binary/Partial 등 세부 metric을 명시하지 않아 임의로 보충하지 않았습니다.

| 모델 | SWE-bench Verified | SWE-bench Pro | DeepSWE 1.1 | Terminal-Bench | OSWorld 2.0 | BrowseComp |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | **96.0%**<br><sub>5회 평균</sub> | **79.2%**<br><sub>5회 평균</sub> | **68.8%**<br><sub>5회 평균</sub> | - | **70.57%**<br><sub>success@1 · 5회</sub> | **90.8%**<br><sub>tools · 10M-token budget</sub> |
| **GPT-5.6 Sol** | - | **64.6%**<br><sub>설정 미공개</sub> | **72.7%**<br><sub>설정 미공개</sub> | **88.8%**<br><sub>v2.1 · 설정 미공개</sub> | **62.6%**<br><sub>metric·설정 미공개</sub> | **90.4%**<br><sub>설정 미공개</sub> |
| **Gemini 3.1 Pro Preview** | **80.6%**<br><sub>10회 · corrected harness</sub> | **54.2%**<br><sub>Public · 5회</sub> | - | **68.5%**<br><sub>v2.0 · Terminus-2</sub> | - | **85.9%**<br><sub>Search+Python+Browse</sub> |
| **Grok 4.6 High** | - | - | **65.9%**<br><sub>설정 미공개</sub> | **26.0%**<br><sub>v3.0 · 설정 미공개</sub> | - | - |

### 공통 비교 — 지식·추론·장문·전문 작업

| 모델 | GPQA Diamond | Humanity's Last Exam | MMMU-Pro | ARC-AGI-2 | GDPval-AA v2 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Claude Opus 5** | - | **56.3%** <sub>no tools</sub><br>**64.7%** <sub>tools</sub> | - | **90.42%**<br><sub>max · ARC Prize verified</sub> | **1861 Elo**<br><sub>v2 · max</sub> |
| **GPT-5.6 Sol** | **94.6%**<br><sub>설정 미공개</sub> | - | **83.0%** <sub>no tools</sub><br>**84.6%** <sub>tools</sub> | - | **1747.8 Elo**<br><sub>v2</sub> |
| **Gemini 3.1 Pro Preview** | **94.3%**<br><sub>Thinking High · no tools</sub> | **44.4%** <sub>full text+MM · no tools</sub><br>**51.4%** <sub>full text+MM · Search+Code</sub> | **80.5%**<br><sub>no tools</sub> | **77.1%**<br><sub>ARC Prize verified</sub> | - |
| **Grok 4.6 High** | - | - | - | - | **1753 Elo**<br><sub>v2 · 설정 미공개</sub> |

### Frontier 추가 공식 결과

공통 열에 억지로 맞추지 못하는 정확한 version·subset은 아래에 그대로 보존합니다. `%`가 없는 값은 원문 단위(Elo, index, IoU 등)를 유지했습니다.

| 모델 | 추가로 확인한 공식 결과 |
| :--- | :--- |
| **Claude Opus 5** | SWE-bench Multilingual **89.5%**; SWE-bench Multimodal **59.4%**; FrontierCode 1.1 Main **53.4%**; FrontierBench v0.1 **43.3%**; ARC-AGI-1 **97.50%**; ARC-AGI-3 high **30.16%**; HealthBench Professional length-adjusted **59.8%** / raw **73.4%**; AA-Briefcase **1720 Elo**; AutomationBench **26.0%**; MCP Atlas **85.8%**; Toolathlon-Verified Pass@1 **80.6%** / Pass@3 **87.0%** / Pass³ **73.1%**; Chartography no-tools **29.6%** / tools **83.0%**; BenchCAD Vision2Code voxel IoU no-tools **0.366** / tools **0.821**; Harvey open-source Legal Agent Benchmark all-pass **23.58%±0.48** / criterion **93.74%** <sub>production safeguards · Opus 4.8 fallback 가능</sub>. |
| **GPT-5.6 Sol** | Agents' Last Exam 표 **52.7%**<sup>2</sup>; AA Intelligence Index v4.1 **58.9**; AA Coding Agent Index v1.1 **80**; Management Consulting Tasks **43.2%**; Big Finance Bench **53%**; HealthBench Professional **60.5%** length-adjusted; GeneBench-Pro **28.7%**; LifeSciBench **59.9%**; MedChemBench internal **48.3%**; BenchCAD **70.6%** / Python tool **83.4%**; Capture-the-Flag **96.7%**; SEC-Bench Pro **71.2%**; ExploitBench **73.5%**; ExploitGym 6h **33.7%**; AutomationBench **18.1%**; Toolathlon **58%**; ARC-AGI-3 **7.78%**; FrontierMath T1–3 v2 **89%** / T4 v2 **83%**; gdp.pdf **30.7%**; Internal Research Debugging **68.3%**; KernelGen1P **61.1%**; NanoGPT **9.69%**; PostTrainBench Lite **50.3%**; RSI Index **57.9%**; OpenAI MRCR v2 8-needle 256K–512K **91.5%** / 512K–1M **73.8%**; GraphWalks BFS 256K F1 **90.7%** / 1M F1 **77.1%**. |
| **Gemini 3.1 Pro Preview** | GDPval-AA <sub>version 미표기</sub> **1317 Elo**; MMMLU **92.6%**; τ² Retail **90.8%** / Telecom **99.3%**; MCP Atlas **69.2%**; APEX-Agents **33.5%**; LiveCodeBench Pro **2887 Elo**; SciCode **59%**; MRCR v2 8-needle 128K cumulative average **84.9%** / 1M pointwise **26.3%**. |
| **Grok 4.6 High** | Artificial Analysis Intelligence Index **61**; CursorBench v3.2 **69.9%**; FrontierCode v1.1 Extended **61.3%**; APEX-Agents **57.5%**; APEX-SWE **56.4%**; AA-Briefcase **1577 Elo**. |

<sup>2</sup> OpenAI의 같은 발표 페이지는 본문에서 **53.6**, 비교표에서 **52.7%**를 표시하지만 설정 차이를 설명하지 않습니다. 구조화된 비교표의 Sol 열 값을 기록하고 충돌을 [SOURCES.md](./SOURCES.md)에 남겼습니다.

<a id="recent-open-weight"></a>

## Recent Open-Weight Models

아래 **5개 체크포인트만** 추적합니다. 기본 기준은 총 파라미터 120B 이하, 2026-04-01 이후 공개, 현재 내려받을 수 있는 가중치입니다. 최신 EXAONE은 토큰당 활성 규모를 강조해 `K-EXAONE 2.0 A37B`로 표시합니다. 다만 A37B는 별도 37B 체크포인트가 아니라 총 750B MoE의 약 37B active 구성이므로 크기 기준에서는 명시적 예외입니다.

### 추적 체크포인트

| 정확한 체크포인트 | 공개일 | 공식/아티팩트 파라미터 | 라이선스 | 성격 |
| :--- | :---: | :--- | :--- | :--- |
| [**google/gemma-4-31B-it**](https://huggingface.co/google/gemma-4-31B-it) | 2026-04-02 | LM 30.7B + vision ~0.55B<br><sub>artifact 31,273,088,876</sub> | Apache-2.0 | multimodal IT · Thinking |
| [**google/diffusiongemma-26B-A4B-it**](https://huggingface.co/google/diffusiongemma-26B-A4B-it) | 2026-06-10 | 25.2B / 3.8B active + vision<br><sub>artifact 25,823,778,864</sub> | Apache-2.0 | diffusion multimodal IT |
| [**inclusionAI/LLaDA2.2-flash**](https://huggingface.co/inclusionAI/LLaDA2.2-flash) | 2026-07-16 | 100B non-embedding<br><sub>artifact 102,889,705,216; active 미공개</sub> | Apache-2.0 | diffusion MoE |
| [**LGAI-EXAONE/K-EXAONE-2.0-750B-A37B**](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B) | 2026-07-31<sup>3</sup> | **37B active** / 750B total<br><sub>artifact 749,357,484,800</sub> | Apache-2.0 | multilingual MoE · **A37B tracked** |
| [**Qwen/Qwen3.8-27B**](https://huggingface.co/Qwen/Qwen3.8-27B) | 2026-08-13<sup>4</sup> | 27B dense<br><sub>artifact 27,781,427,952</sub> | Apache-2.0 | multimodal dense |

<sup>3</sup> A37B는 토큰당 약 37B active parameter를 뜻하며 standalone·total size가 아닙니다. 실제 total은 750B이므로 ≤120B 기본 기준의 사용자 지정 예외입니다. 16개 BF16 weight shard를 포함한 첫 전체 커밋 날짜는 2026-07-31이고, 기술 보고서는 2026-08-05 공개됐습니다.

<sup>4</sup> 빈 저장소 생성일이 아니라 첫 전체 weight shard 공개 커밋 날짜.

### 공통 비교 — 코딩·에이전트

τ²는 전체 평균만 공통값으로 사용합니다. LLaDA가 `τ²-Bench 80.33`으로 표기한 값은 인용 문헌이 2024 τ-bench를 가리켜 공통 τ² 열에서 제외하고 아래 보충표에 원문 라벨 그대로 남겼습니다.

| 모델 | SWE-bench Verified | τ²-Bench | BFCL V4 | LiveCodeBench v6 | IFBench |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Gemma 4 31B-IT** | - | **76.9%**<br><sub>3-domain average</sub> | - | **80.0%**<br><sub>Thinking</sub> | **76.0%**<br><sub>Thinking</sub> |
| **DiffusionGemma 26B-A4B-IT** | - | **56.2%**<br><sub>average over 3</sub> | - | **69.1%**<br><sub>partial config</sub> | - |
| **LLaDA2.2-flash** | **49.28%**<br><sub>Claude Code · 5회</sub> | - | **60.78%**<br><sub>5회 · subtype 미공개</sub> | - | **30.20%**<br><sub>5회 · partial config</sub> |
| **K-EXAONE 2.0 A37B** | **68.2%**<br><sub>Reasoning · mini-SWE-agent · partial config</sub> | - | - | - | **72.6%**<br><sub>Reasoning · official setup · partial config</sub> |
| **Qwen3.8-27B** | - | - | - | **90.3%**<br><sub>partial config</sub> | **79.5%**<br><sub>partial config</sub> |

### 공통 비교 — 지식·추론

| 모델 | GPQA Diamond | HLE | MMLU-Pro |
| :--- | :---: | :---: | :---: |
| **Gemma 4 31B-IT** | **84.3%**<br><sub>Thinking</sub> | **19.5%** <sub>no tools</sub><br>**26.5%** <sub>search</sub> | **85.2%**<br><sub>Thinking</sub> |
| **DiffusionGemma 26B-A4B-IT** | **73.2%**<br><sub>partial config</sub> | **11.0%** <sub>no tools</sub><br>**11.9%** <sub>search</sub> | **77.6%**<br><sub>partial config</sub> |
| **LLaDA2.2-flash** | **48.67%**<br><sub>5회 · partial config</sub> | - | - |
| **K-EXAONE 2.0 A37B** | **82.2%**<br><sub>Reasoning · official setup · partial config</sub> | **18.3%**<br><sub>Reasoning · text-only · partial config</sub> | **83.5%**<br><sub>Reasoning · official setup · partial config</sub> |
| **Qwen3.8-27B** | **89.2%**<br><sub>partial config</sub> | **30.8%**<br><sub>GPT-4o judge · tools 미공개</sub> | - |

### Recent 추가 공식 결과

다음 값은 공식 모델 카드·기술 보고서에서 확인했지만 공통 8열과 version·subset·용도가 달라 공통 채움률에는 포함하지 않습니다. 원문 이름과 단위를 유지하며, 두 공식 원문이 충돌하면 양쪽 값을 함께 표시합니다.

| 모델 | 추가 텍스트·코딩·에이전트 결과 |
| :--- | :--- |
| **Gemma 4 31B-IT** | AIME 2026 no-tools **89.2%**; Codeforces **2150 Elo**; SciCode **43.0%**; BigBench Extra Hard **74.4%**; IFEval **98.9%**; Terminal-Bench Hard **36.0%**; τ² Airline **75.0%** / Retail **86.4%** / Telecom **69.3%**. |
| **DiffusionGemma 26B-A4B-IT** | AIME 2026 no-tools **69.1%**; Codeforces **1429 Elo**; BigBench Extra Hard **47.6%**. |
| **LLaDA2.2-flash** | Agentic Avg **53.83%**; General Avg **56.81%**; SWE-bench Pro **30.10%**; SWE-bench Multilingual **25.00%**; vendor-labelled τ²-Bench **80.33%**<sup>5</sup>; Claw-Eval **64.22%**; PinchBench **81.66%**; MCP-Atlas **46.21%**; BFCL v3 **67.17%**; AIME 2026 **62.24%**; OlympiadBench **74.48%**; LiveCodeBench version 미공개 **44.77%**; Multi-IF **73.67%**; KOR-Bench **60.96%**; LongBench v2 **45.13%**. |
| **K-EXAONE 2.0 A37B** | <sub>report 값=Reasoning; card 충돌값=BF16·mode 미공개</sub><br>AIME 2026 **92.3%**; HMMT Feb 2026 **78.4%**; IMO-AnswerBench **78.6%**; SciCode **40.1%** <sub>report</sub> / **37.4%** <sub>card, 충돌</sub>; Terminal-Bench 2.1 **43.8%** <sub>Terminus-2</sub>; τ³-Banking **14.2%**; Claw-Eval (general) **80.0%** <sub>report</sub> / generic Claw-Eval **77.7%** <sub>card, label·값 충돌</sub>; IFEval **92.4%**; OpenAI-MRCR ≤128K macro-average **94.4%**; AA-LCR **56.2%**; Ko-LongBench **89.6%**; KMMLU-Pro **69.1%**; CLIcK **84.2%**; HRM8K-KSM **91.1%**; MMMLU **86.6%**; GlobalMMLU-Lite **86.6%**; PolyMath **71.3%**; KGC-Safety (in-house) **99.8%**; ROK-Fortress **89.5%**. |
| **Qwen3.8-27B** | Terminal-Bench 2.1 **73.0**; SWE-bench Pro refined **61.7%**; NL2Repo-Bench **42.3%**; DeepSWE 1.1 **42.2%**; QwenSWEBench **79.0%**; CoWorkBench **70.7%**; JobBench **33.4%**; Agents' Last Exam Pass@1 **20.4%** / Score **42.9**. |

| 모델 | 추가 멀티모달·전문화 결과 |
| :--- | :--- |
| **Gemma 4 31B-IT** | MMMLU **88.4%**; MMMU-Pro **76.9%**; OmniDocBench 1.5 AED **0.131** ↓; MATH-Vision **85.6%**; MedXPertQA-MM **61.3%**; MRCR v2 8-needle 128K **66.4%**. |
| **DiffusionGemma 26B-A4B-IT** | MMMLU **81.5%**; MMMU-Pro **54.3%**; OmniDocBench 1.5 AED **0.319** ↓; MATH-Vision **70.5%**; MedXPertQA-MM **49.0%**; MRCR v2 8-needle 128K **32.0%**. |
| **Qwen3.8-27B** | OSWorld-Verified **84.3%**; WebArena-Verified **64.8%**; AndroidWorld **81.9%**; RecreationBench **47.1%**; ClawEval-MM Pass@3 **57.4%** / avg **56.9%**; SWE-MM **38.6%**; Vision2Web **62.9%**; MathVision without/with CI **90.0% / 94.6%**; BabyVision **65.7% / 85.6%**; CharXiv RQ **83.7% / 90.2%**; OmniDocBench 1.5 **91.1%**; RealWorldQA **85.9%**; ERQA **65.5%**. |

<sup>5</sup> LLaDA 보고서는 이름을 `τ²-Bench`로 쓰지만 참고문헌이 Sierra의 τ²가 아니라 2024년 원 τ-bench 논문을 가리킵니다. 따라서 원문 주장으로만 보존하고 공통 τ² 값으로 채택하지 않았습니다.

<a id="gpt-oss-reference"></a>

## Reference Baselines

### OpenAI gpt-oss (2025-08-05)

두 모델은 2026-04-01 이전 공개이므로 추적 로스터와 채움률에서 제외합니다. 모델 카드의 평가는 두 모델 모두 **MXFP4 양자화 체크포인트**로 수행됐습니다. 첫 비교표와 아래 추가값 중 AIME·Tau-Bench·Aider·MMMLU·HealthBench·Codeforces는 Table 3의 **high reasoning effort** 결과입니다. Table 9·10의 SimpleQA·PersonQA·BBQ는 reasoning effort가 공개되지 않아 별도로 표시했습니다. 카드가 `with tools`의 정확한 도구 구성을 다시 밝히지는 않으므로 도구 유무만 원문대로 구분했습니다.

| 모델 | 총 / active 파라미터 | 체크포인트 크기 | 공식 문서 |
| :--- | :---: | :---: | :--- |
| **gpt-oss-120b** | 116.83B / 5.13B | 60.8 GiB | [OpenAI 모델 문서](https://developers.openai.com/api/docs/models/gpt-oss-120b) · [Hugging Face](https://huggingface.co/openai/gpt-oss-120b) |
| **gpt-oss-20b** | 20.91B / 3.61B | 12.8 GiB | [OpenAI 모델 문서](https://developers.openai.com/api/docs/models/gpt-oss-20b) · [Hugging Face](https://huggingface.co/openai/gpt-oss-20b) |

| 모델 | SWE-bench Verified | GPQA Diamond | HLE | MMLU | AIME 2025 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **gpt-oss-120b** | **62.4%** | **80.1%** <sub>no tools</sub><br>**80.9%** <sub>tools</sub> | **14.9%** <sub>no tools</sub><br>**19.0%** <sub>tools</sub> | **90.0%** | **92.5%** <sub>no tools</sub><br>**97.9%** <sub>tools</sub> |
| **gpt-oss-20b** | **60.7%** | **71.5%** <sub>no tools</sub><br>**74.2%** <sub>tools</sub> | **10.9%** <sub>no tools</sub><br>**17.3%** <sub>tools</sub> | **85.3%** | **91.7%** <sub>no tools</sub><br>**98.7%** <sub>tools</sub> |

| 모델 | 그 밖의 공식 결과 |
| :--- | :--- |
| **gpt-oss-120b** | AIME 2024 no-tools **95.8%** / tools **96.6%**; Tau-Bench Retail **67.8%** / Airline **49.2%** <sub>원 τ-bench, τ² 아님</sub>; Aider Polyglot **44.4%**; MMMLU Avg **81.3%**; HealthBench **57.6%** / Hard **30.0%** / Consensus **89.9%**; Codeforces no-tools **2463 Elo** / tools **2622 Elo**.<br><sub>Table 9·10 · effort 미공개 · 원문 proportion을 ×100 환산; SimpleQA/PersonQA는 no browsing</sub><br>SimpleQA accuracy **16.8%** / hallucination rate **78.2%** ↓; PersonQA accuracy **29.8%** / hallucination rate **49.1%** ↓; BBQ ambiguous/disambiguated accuracy **87% / 90%**. |
| **gpt-oss-20b** | AIME 2024 no-tools **92.1%** / tools **96.0%**; Tau-Bench Retail **54.8%** / Airline **38.0%** <sub>원 τ-bench, τ² 아님</sub>; Aider Polyglot **34.2%**; MMMLU Avg **75.7%**; HealthBench **42.5%** / Hard **10.8%** / Consensus **82.6%**; Codeforces no-tools **2230 Elo** / tools **2516 Elo**.<br><sub>Table 9·10 · effort 미공개 · 원문 proportion을 ×100 환산; SimpleQA/PersonQA는 no browsing</sub><br>SimpleQA accuracy **6.7%** / hallucination rate **91.4%** ↓; PersonQA accuracy **15.5%** / hallucination rate **53.2%** ↓; BBQ ambiguous/disambiguated accuracy **79% / 89%**. |

공식 근거: [OpenAI 오픈 모델 성능표](https://openai.com/open-models/) · [OpenAI 모델 카드 안내](https://openai.com/index/gpt-oss-model-card/) · [고정 모델 카드 HTML](https://arxiv.org/html/2508.10925v1).

## 확인 통계

| 범위 | Browser에서 공식 원문 확인 | 공통 비교 채움 | 공통 비교 미확인 | 채움률 |
| :--- | ---: | ---: | ---: | ---: |
| Frontier 4개 모델, 11개 열 | **4/4** | **27/44** | 17/44 | **61.36%** |
| Recent open-weight 5개, 8개 열 | **5/5** | **24/40** | 16/40 | **60.00%** |
| **추적 모델 합계** | **9/9** | **51/84** | **33/84** | **60.71%** |
| 참고용 gpt-oss 2개 | **2/2** | 통계 제외 | 통계 제외 | — |

추적 대상에서 모든 행이 빈 benchmark 열은 제거했습니다. 추가·전문화 표와 gpt-oss 참고표는 정확한 version·subset·출시 기간을 보존하기 위해 공통 행렬 통계에서 제외했습니다.

고정 카드 URL, 평가 설정, Browser 확인 상태와 benchmark 정의 URL은 [SOURCES.md](./SOURCES.md)에 기록합니다.

## 기여

새 수치를 추가할 때는 정확한 모델 ID, benchmark version, metric, tools/scaffold, 시행 횟수와 모델 제공사 또는 benchmark 운영자의 공식 URL을 함께 남겨 주세요.

## 라이선스

MIT License
