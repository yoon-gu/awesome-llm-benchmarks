# Recent Open-Weight Models (≤120B, released since 2026-04-01)

아래 **15개 체크포인트만** 추적합니다. 총 파라미터 120B 이하, 2026-04-01 이후 공개, 현재 내려받을 수 있는 가중치라는 조건을 적용했습니다. **2026-08-19 (KST)** 기준으로 각 공식 모델 카드·기술 보고서·출시 문서를 Browser에서 다시 열어 대상 모델 열을 직접 판독했습니다.

`-`는 0점이 아니라 정확히 일치하는 공식 값이 없다는 뜻입니다. `partial config`는 모델·benchmark·값은 확인되지만 shot, tools, pass@k, trials 또는 harness 일부가 공개되지 않았다는 뜻입니다.

## 추적 체크포인트

| 정확한 체크포인트 | 공개일 | 공식/아티팩트 파라미터 | 라이선스 | 성격 |
| :--- | :---: | :--- | :--- | :--- |
| [**google/gemma-4-31B-it**](https://huggingface.co/google/gemma-4-31B-it) | 2026-04-02 | LM 30.7B + vision ~0.55B<br><sub>artifact 31,273,088,876</sub> | Apache-2.0 | multimodal IT · Thinking |
| [**LGAI-EXAONE/EXAONE-4.5-33B**](https://huggingface.co/LGAI-EXAONE/EXAONE-4.5-33B) | 2026-04-09 | LM 31.7B + vision 1.29B<br><sub>artifact 34,350,097,664</sub> | EXAONE 1.2-NC | multimodal · Reasoning |
| [**Qwen/Qwen3.6-35B-A3B**](https://huggingface.co/Qwen/Qwen3.6-35B-A3B) | 2026-04-15 | 35B total / 3B active<br><sub>artifact 35,951,822,704</sub> | Apache-2.0 | multimodal MoE |
| [**Qwen/Qwen3.6-27B**](https://huggingface.co/Qwen/Qwen3.6-27B) | 2026-04-22 | 27B dense<br><sub>artifact 27,781,427,952</sub> | Apache-2.0 | multimodal dense |
| [**nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16**](https://huggingface.co/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16) | 2026-04-28 | backbone 31B / ~3B active<br><sub>artifact 33,015,632,214</sub> | NVIDIA Open Model Agreement | omni-modal · Reasoning |
| [**ibm-granite/granite-4.1-30b**](https://huggingface.co/ibm-granite/granite-4.1-30b) | 2026-04-29 | 30B dense<br><sub>artifact 28,865,728,512</sub> | Apache-2.0 | general dense |
| [**openbmb/MiniCPM5-1B**](https://huggingface.co/openbmb/MiniCPM5-1B) | 2026-05-19 | 1,080,632,832<br><sub>679,552,512 non-embedding</sub> | Apache-2.0 | on-device · Thinking |
| [**tencent/Hy-MT2-30B-A3B**](https://huggingface.co/tencent/Hy-MT2-30B-A3B) | 2026-05-21 | 30B total / 3B active<br><sub>artifact 30,064,725,888</sub> | Apache-2.0 | translation MoE |
| [**CohereLabs/North-Mini-Code-1.0**](https://huggingface.co/CohereLabs/North-Mini-Code-1.0) | 2026-06-09 | 30B total / 3B active<br><sub>artifact 30,484,303,872</sub> | Apache-2.0 | coding MoE |
| [**google/diffusiongemma-26B-A4B-it**](https://huggingface.co/google/diffusiongemma-26B-A4B-it) | 2026-06-10 | 25.2B / 3.8B active + vision<br><sub>artifact 25,823,778,864</sub> | Apache-2.0 | diffusion multimodal IT |
| [**inclusionAI/LLaDA2.2-flash**](https://huggingface.co/inclusionAI/LLaDA2.2-flash) | 2026-07-16 | 100B non-embedding<br><sub>artifact 102,889,705,216; active 미공개</sub> | Apache-2.0 | diffusion MoE |
| [**LiquidAI/LFM2.5-2.6B**](https://huggingface.co/LiquidAI/LFM2.5-2.6B) | 2026-08-04 | 2,697,198,592 | LFM 1.0 | reasoning/agentic hybrid |
| [**inclusionAI/Ling-3.0-tiny**](https://huggingface.co/inclusionAI/Ling-3.0-tiny) | 2026-08-10 | 7.9B / 1.4B active<br><sub>artifact 7,893,392,800</sub> | MIT | Thinking MoE |
| [**nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16**](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16) | 2026-08-11 | 30B / 3B active<br><sub>artifact 31,577,937,344</sub> | OpenMDW-1.1 | general MoE |
| [**Qwen/Qwen3.8-27B**](https://huggingface.co/Qwen/Qwen3.8-27B) | 2026-08-13<sup>1</sup> | 27B dense<br><sub>artifact 27,781,427,952</sub> | Apache-2.0 | multimodal dense |

<sup>1</sup> 빈 저장소 생성일이 아니라 첫 전체 weight shard 공개 커밋 날짜.

## 공통 비교 — 코딩·에이전트

τ²는 전체 평균과 단일 domain을 셀에 구분합니다. LLaDA가 `τ²-Bench 80.33`으로 표기한 값은 인용 문헌이 2024 τ-bench를 가리켜 공통 τ² 열에서 제외하고 아래 보충표에 원문 라벨 그대로 남겼습니다.

| 모델 | SWE-bench Verified | τ²-Bench | BFCL V4 | LiveCodeBench v6 | IFBench |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Gemma 4 31B-IT** | - | **76.9%**<br><sub>3-domain average</sub> | - | **80.0%**<br><sub>Thinking</sub> | **76.0%**<br><sub>Thinking</sub> |
| **EXAONE 4.5 33B** | - | **72.0%**<br><sub>weighted aggregate · Reasoning</sub> | - | **81.4%**<br><sub>Reasoning · partial config</sub> | **62.6%**<br><sub>Reasoning · partial config</sub> |
| **Qwen3.6-35B-A3B** | **73.4%**<br><sub>internal bash+edit agent</sub> | - | - | **80.4%**<br><sub>partial config</sub> | - |
| **Qwen3.6-27B** | **77.2%**<br><sub>internal bash+edit agent</sub> | - | - | **83.9%**<br><sub>partial config</sub> | - |
| **Nemotron 3 Nano Omni** | - | - | - | - | **74.2%**<br><sub>prompt · 1회</sub> |
| **MiniCPM5-1B** | - | **79.53%**<br><sub>Telecom-AA only</sub> | **25.15%**<br><sub>Thinking · partial config</sub> | **33.52%**<br><sub>v6 · Avg3 · Thinking</sub> | **46.67%**<br><sub>Thinking · partial config</sub> |
| **Hy-MT2-30B-A3B** | - | - | - | - | **50.67%**<br><sub>non-thinking · partial config</sub> |
| **North-Mini-Code-1.0** | **67.6%**<br><sub>SWE-Agent v1.1 · 3 seeds</sub> | - | - | **70.3%**<br><sub>no tools · 3 seeds</sub> | - |
| **DiffusionGemma 26B-A4B-IT** | - | **56.2%**<br><sub>average over 3</sub> | - | **69.1%**<br><sub>partial config</sub> | - |
| **LLaDA2.2-flash** | **49.28%**<br><sub>Claude Code · 5회</sub> | - | **60.78%**<br><sub>5회 · subtype 미공개</sub> | - | **30.20%**<br><sub>5회 · partial config</sub> |
| **LFM2.5-2.6B** | - | - | **56.88%**<br><sub>subtype 미공개</sub> | **59.41%**<br><sub>partial config</sub> | **59.17%**<br><sub>partial config</sub> |
| **Ling-3.0-tiny** | - | - | **62.72%**<br><sub>FC · Thinking</sub> | - | **63.61%**<br><sub>Thinking · partial config</sub> |
| **Nemotron 3.5 Lightning** | **51.56%**<br><sub>OpenHands 1.17 · 500×5</sub> | - | - | - | **71.88%**<br><sub>loose · partial config</sub> |
| **Qwen3.8-27B** | - | - | - | **90.3%**<br><sub>partial config</sub> | **79.5%**<br><sub>partial config</sub> |

Granite 4.1은 이 다섯 열에 exact-version 값이 없어 행을 숨겼습니다.

## 공통 비교 — 지식·추론

| 모델 | GPQA Diamond | HLE | MMLU | MMLU-Pro | GSM8K | HumanEval |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Gemma 4 31B-IT** | **84.3%**<br><sub>Thinking</sub> | **19.5%** <sub>no tools</sub><br>**26.5%** <sub>search</sub> | - | **85.2%**<br><sub>Thinking</sub> | - | - |
| **EXAONE 4.5 33B** | **80.5%**<br><sub>Reasoning · partial config</sub> | - | - | **83.3%**<br><sub>Reasoning · partial config</sub> | - | - |
| **Qwen3.6-35B-A3B** | **86.0%**<br><sub>mode 미공개</sub> | **21.4%**<br><sub>tools·mode 미공개</sub> | - | **85.2%**<br><sub>mode 미공개</sub> | - | - |
| **Qwen3.6-27B** | **87.8%**<br><sub>mode 미공개</sub> | **24.0%**<br><sub>tools·mode 미공개</sub> | - | **86.2%**<br><sub>mode 미공개</sub> | - | - |
| **Nemotron 3 Nano Omni** | **72.2%**<br><sub>no tools · 4회</sub> | - | - | **77.3%**<br><sub>1회</sub> | - | - |
| **Granite 4.1 30B** | - | - | **80.16%**<br><sub>5-shot</sub> | **64.09%**<br><sub>5-shot CoT</sub> | **94.16%**<br><sub>8-shot</sub> | **88.41%**<br><sub>pass@1</sub> |
| **MiniCPM5-1B** | **26.26%**<br><sub>Thinking · partial config</sub> | - | - | **48.85%**<br><sub>Thinking · partial config</sub> | - | - |
| **DiffusionGemma 26B-A4B-IT** | **73.2%**<br><sub>partial config</sub> | **11.0%** <sub>no tools</sub><br>**11.9%** <sub>search</sub> | - | **77.6%**<br><sub>partial config</sub> | - | - |
| **LLaDA2.2-flash** | **48.67%**<br><sub>5회 · partial config</sub> | - | - | - | - | - |
| **Ling-3.0-tiny** | **73.40%**<br><sub>Thinking · partial config</sub> | **9.30%**<br><sub>Thinking · tools 미공개</sub> | - | - | - | - |
| **Nemotron 3.5 Lightning** | **75.44%**<br><sub>no tools · 198×8</sub> | **11.72%**<br><sub>text-only · no tools</sub> | - | **81.94%**<br><sub>partial config</sub> | - | - |
| **Qwen3.8-27B** | **89.2%**<br><sub>partial config</sub> | **30.8%**<br><sub>GPT-4o judge · tools 미공개</sub> | - | - | - | - |

Hy-MT2, North Mini Code, LFM2.5는 이 여섯 열에 exact 값이 없어 행을 숨겼습니다.

## 공통 비교 — 멀티모달

| 모델 | MMMU | MathVista mini |
| :--- | :---: | :---: |
| **EXAONE 4.5 33B** | **78.7%**<br><sub>Reasoning</sub> | **85.0%**<br><sub>Reasoning</sub> |
| **Qwen3.6-35B-A3B** | **81.7%**<br><sub>mode 미공개</sub> | **86.4%**<br><sub>mode 미공개</sub> |
| **Qwen3.6-27B** | **82.9%**<br><sub>mode 미공개</sub> | **87.4%**<br><sub>mode 미공개</sub> |
| **Nemotron 3 Nano Omni** | **70.8%**<br><sub>val · reasoning on</sub> | **82.8%**<br><sub>reasoning on</sub> |

나머지 11개 모델은 정확한 `MMMU` 또는 `MathVista mini` 값을 찾지 못해 이 표에서 숨겼습니다. `MMMU-Pro`, `MMMLU`, `MATH-Vision`은 다른 benchmark이므로 대체하지 않았습니다.

## 모델 카드의 추가 공식 결과

다음 값은 공통 13열과 version·subset·용도가 달라 공통 채움률에는 포함하지 않습니다. 원문 이름과 단위를 유지합니다.

| 모델 | 추가 텍스트·코딩·에이전트 결과 |
| :--- | :--- |
| **Gemma 4 31B-IT** | AIME 2026 no-tools **89.2%**; Codeforces **2150 Elo**; SciCode **43.0%**; BigBench Extra Hard **74.4%**; IFEval **98.9%**; Terminal-Bench Hard **36.0%**; τ² Airline **75.0%** / Retail **86.4%** / Telecom **69.3%**. |
| **EXAONE 4.5 33B** | AIME 2026 **92.6%**; IFEval **89.6%**; AA-LCR **50.6%**; KMMLU-Pro **67.6%**; KoBALT **52.1%**; MMMLU ko/de/es/ja **85.4%**; WMT24++ ko/de/es/ja/vi **91.5%**; τ² Retail **77.9%** / Airline **56.5%** / Telecom **73.0%**. |
| **Qwen3.6-35B-A3B** | SWE-bench Multilingual **67.2%**; SWE-bench Pro refined **49.5%**; Terminal-Bench 2.0 **51.5**; Claw-Eval Avg **68.7%** / Pass³ **50.0%**; SkillsBench Avg5 **28.7%**; QwenClawBench **52.6%**; NL2Repo **29.4%**; QwenWebBench **1397 Elo**; TAU3-Bench **67.2%**; VITA-Bench **35.6%**; DeepPlanning **25.9%**; Tool Decathlon **26.9%**; MCPMark **37.0%**; MCP Atlas **62.8%**; WideSearch **60.1%**; MMLU-Redux **93.3%**; SuperGPQA **64.7%**; C-Eval **90.0%**; HMMT Feb-25 **90.7%** / Nov-25 **89.1%** / Feb-26 **83.6%**; IMOAnswerBench **78.9%**; AIME 2026 I+II **92.7%**. |
| **Qwen3.6-27B** | SWE-bench Multilingual **71.3%**; SWE-bench Pro refined **53.5%**; Terminal-Bench 2.0 **59.3**; SkillsBench Avg5 **48.2%**; Claw-Eval Avg **72.4%** / Pass³ **60.6%**; QwenClawBench **53.4%**; QwenWebBench **1487 Elo**; NL2Repo **36.2%**; MMLU-Redux **93.5%**; SuperGPQA **66.0%**; C-Eval **91.4%**; HMMT Feb-25 **93.8%** / Nov-25 **90.7%** / Feb-26 **84.3%**; IMOAnswerBench **80.8%**; AIME 2026 I+II **94.1%**. |
| **Nemotron 3 Nano Omni** | LiveCodeBench v5 (2024-07–2025-05) **63.2%**; AIME 2025 no-tools **82.1%**; AA-LCR **41.0%**; SciCode **32.0%**; TauBench V2 (Telecom) **42.7%** <sub>τ² 식별 미공개</sub>; OSWorld generic **47.4%** <sub>OSWorld 2.0 아님</sub>. |
| **Granite 4.1 30B** | GPQA <sub>card label</sub> 0-shot CoT **45.76%**; BBH 3-shot CoT **83.74%**; AGIEval 0-shot CoT **77.80%**; SimpleQA **6.81%**; AlpacaEval 2.0 **56.16%**; IFEval Avg **89.65%**; ArenaHard **71.02%**; MTBench Avg **8.61**; GSM Symbolic **75.70%**; MinervaMath **81.32%**; DeepMindMath **81.93%**; HumanEval+ **85.37%**; MBPP **85.45%**; MBPP+ **73.54%**; CRUXEval-O pass@1 **55.75%**; BigCodeBench **38.77%**; MULTIPLE **62.31%**; Eval+ Avg pass@1 **82.66%**; BFCL v3 **73.68%**. |
| **MiniCPM5-1B** | Average Score **42.57**; MMLU-Redux **70.06%**; SuperGPQA **23.14%**; LCB-Pro 25Q2 Easy **22.68%**; OJBench **7.33%**; IFEval **80.41%**; Multi-IF **43.54%**; MultiChallenge **19.48%**; AIME 2025 Avg16 **40.42%**; AIME 2026 Avg16 **40.42%**; HMMT Feb-2026 Avg16 **25.76%**; MATH-500 **91.60%**; BBH **71.89%**; BBEH **12.14%**. |
| **Hy-MT2-30B-A3B** | IFEval **89.80%**; MaXIFE loose **80.46%** / strict **74.31%** / overall **77.39%**; Multi-IF turn1 **90.10%** / turn2 **72.73%** / turn3 **66.66%**; IFMTBench simple **90.20%** / complex **75.94%** / total **84.69%**. |
| **North-Mini-Code-1.0** | Terminal-Bench v2 **36.0**; Terminal-Bench Hard **31.1**; SWE-bench Pro **40.2%**; SciCode **38.2%**. |
| **DiffusionGemma 26B-A4B-IT** | AIME 2026 no-tools **69.1%**; Codeforces **1429 Elo**; BigBench Extra Hard **47.6%**; MMMLU **81.5%**; MMMU-Pro **54.3%**; OmniDocBench 1.5 AED **0.319** ↓; MATH-Vision **70.5%**; MedXPertQA-MM **49.0%**; MRCR v2 8-needle 128K **32.0%**. |
| **LLaDA2.2-flash** | Agentic Avg **53.83%**; General Avg **56.81%**; SWE-bench Pro **30.10%**; SWE-bench Multilingual **25.00%**; vendor-labelled τ²-Bench **80.33%**<sup>2</sup>; Claw-Eval **64.22%**; PinchBench **81.66%**; MCP-Atlas **46.21%**; BFCL v3 **67.17%**; AIME 2026 **62.24%**; OlympiadBench **74.48%**; LiveCodeBench version 미공개 **44.77%**; Multi-IF **73.67%**; KOR-Bench **60.96%**; LongBench v2 **45.13%**. |
| **LFM2.5-2.6B** | AA-Omni-Public Index **−29.50** / Accuracy **8.13%** / Non-hallu **59.04%**; AIME25 **51.87%**; Multi-IF **80.07%**; IFStruct **85.49%**; ToolSandbox **77.83%**; τ³ Banking **5.67%**; Claw-Eval avg EN **62.85%**; PinchBench **68.22%**; BrowseComp+ OpenClaw **26.89%**. |
| **Ling-3.0-tiny** | GDPval v2-AA **772.00**; τ³ Banking-AA **20.80%**; Terminal-Bench 2.1 **27.70**; ArtifactsBench **47.93%**; SciCode **24.20%**; AA-LCR **58.70%**; AA-Omniscience Accuracy **8.52%** / Non-Hallucination **69.54%**; HMMT-Feb26 **70.31%**; IMO-AnswerBench **71.03%**; LIFEBench **62.30%**; Multi-IF **83.15%**. |
| **Nemotron 3.5 Lightning** | AA-Omniscience **17.50%**; SciCode **32.60%**; SWE-bench Multilingual **39.33%**; Terminal-Bench 2.1 **24.58**; PinchBench **85.37%**; BrowseComp **36.97%**; τ³ Banking **9.28%**; GDPval-AA-v2 **832**; AA-LCR **52.00%**. |
| **Qwen3.8-27B** | Terminal-Bench 2.1 **73.0**; SWE-bench Pro refined **61.7%**; NL2Repo-Bench **42.3%**; DeepSWE 1.1 **42.2%**; QwenSWEBench **79.0%**; CoWorkBench **70.7%**; JobBench **33.4%**; Agents' Last Exam Pass@1 **20.4%** / Score **42.9**. |

| 모델 | 추가 멀티모달·전문화 결과 |
| :--- | :--- |
| **Gemma 4 31B-IT** | MMMLU **88.4%**; MMMU-Pro **76.9%**; OmniDocBench 1.5 AED **0.131** ↓; MATH-Vision **85.6%**; MedXPertQA-MM **61.3%**; MRCR v2 8-needle 128K **66.4%**. |
| **EXAONE 4.5 33B** | MMMU-Pro **68.6%**; MedXpertQA-MM **42.1%**; MATH-Vision **75.2%**; We-Math **79.1%**; LogicVista **73.8%**; BabyVision **18.8%**; AI2D **89.0%**; ChartQAPro **62.2%**; CharXiv **71.7%**; OCRBench v2 **63.2%**; OmniDocBench 1.5 **81.2%**; MMStar **74.9%**; BLINK **68.8%**; HallusionBench **63.7%**; KMMMU **42.7%**; K-Viscuit **80.1%**; KRETA **91.9%**. |
| **Qwen3.6-35B-A3B** | MMMU-Pro **75.3%**; ZEROBench **34.4%**; RealWorldQA **85.3%**; MMBench-EN **92.8%**; SimpleVQA **58.9%**; HallusionBench **69.8%**; OmniDocBench 1.5 **89.9%**; CharXiv RQ **78.0%**; CC-OCR **81.9%**; AI2D **92.7%**; RefCOCO **92.0%**; ODinW13 **50.8%**; EmbSpatial **84.3%**; RefSpatial **64.3%**; VideoMME subtitles **86.6%** / no subtitles **82.5%**; VideoMMMU **83.7%**; MLVU **86.2%**; MVBench **74.6%**; LVBench **71.4%**. |
| **Qwen3.6-27B** | MMMU-Pro **75.8%**; DynaMath **85.6%**; VLMsAreBlind **97.0%**; RealWorldQA **84.1%**; MMStar **81.4%**; MMBench-EN **92.3%**; SimpleVQA **56.1%**; CharXiv RQ **78.4%**; CC-OCR **81.2%**; OCRBench **89.4%**; ERQA **62.5%**; CountBench **97.8%**; RefCOCO **92.5%**; EmbSpatial **84.6%**; RefSpatial **70.0%**; VideoMME subtitles **87.7%**; VideoMMMU **84.4%**; MLVU **86.6%**; MVBench **75.5%**; V* **94.7%**; AndroidWorld **70.3%**. |
| **Nemotron 3 Nano Omni** | CVBench2D **83.95%**; OCRBenchV2 (EN) **67.04%**; MMMU-val reasoning off/on **55.2% / 70.8%**; MathVista-mini off/on **71.9% / 82.8%**; MMLongBench-Doc **46.1% / 57.5%**; ChartQA Test **89.9% / 90.3%**; DocVQA Test **93.3% / 95.6%**; OCR-Reasoning **22.2% / 54.14%**; CharXiv RQ **49.1% / 63.6%**; ScreenSpot v2 **93.4% / 92.8%**; VideoMME (w/o sub) **70.8% / 72.2%**; Voice interaction **89.39%**; Daily Omni **74.52%**; World Sense **55.4%**. |
| **Granite 4.1 30B** | MMMLU **73.71%**; INCLUDE **67.26%**; MGSM **71.12%**; SALAD **96.41%**; AttaQ **85.76%**; Tulu3Safety Avg **78.19%**. |
| **Hy-MT2-30B-A3B** | FLORES ZH↔XX XCOMET/CometKiwi/GEMBA **89.83/79.03/90.26**; EN↔XX **93.85/88.23/90.89**; XX↔XX **87.47/76.34/88.79**; WMT25 **62.89/71.08/84.34**; DomainMTBench XCOMET/GEMBA avg **95.04/93.73**; WildMTBench **89.87/89.25**. |
| **Qwen3.8-27B** | OSWorld-Verified **84.3%**; WebArena-Verified **64.8%**; AndroidWorld **81.9%**; RecreationBench **47.1%**; ClawEval-MM Pass@3 **57.4%** / avg **56.9%**; SWE-MM **38.6%**; Vision2Web **62.9%**; MathVision without/with CI **90.0% / 94.6%**; BabyVision **65.7% / 85.6%**; CharXiv RQ **83.7% / 90.2%**; OmniDocBench 1.5 **91.1%**; RealWorldQA **85.9%**; ERQA **65.5%**. |

<sup>2</sup> LLaDA 보고서는 이름을 `τ²-Bench`로 쓰지만 참고문헌이 Sierra의 τ²가 아니라 2024년 원 τ-bench 논문을 가리킵니다. 따라서 원문 주장으로만 보존하고 공통 τ² 값으로 채택하지 않았습니다.

## 확인 통계

- 공식 원문 Browser 접근: **15/15 모델 확인 가능**.
- 각 모델에서 공식 benchmark score 1개 이상 확인: **15/15**.
- 공통 비교 행렬: **70/195셀(35.90%) 확인**, **125/195셀(64.10%) 미확인**.
- 15개 모델 전체에서 값이 하나도 없는 benchmark 열은 제거했습니다.
- 위 추가 결과는 정확한 version·subset을 보존하기 위해 공통 행렬 통계에서 제외했습니다.

고정 카드 URL, 평가 설정, Browser 확인 상태와 benchmark 정의 URL은 [SOURCES.md](./SOURCES.md)에 기록합니다. 프론티어 4개 모델은 [README.md](./README.md)에서 확인할 수 있습니다.

## 라이선스

MIT License
