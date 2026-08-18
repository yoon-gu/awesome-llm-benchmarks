# 성능 수치 출처 (Performance Result Provenance)

검증 기준일: **2026-08-18 (KST)**

이 문서는 `README.md`와 `small_models_2026.md`의 숫자 셀을 역추적합니다. 모델 소개 페이지를 여러 지표의 포괄 출처로 간주하지 않고, 모델명·벤치마크·수치가 함께 표시된 1차 자료만 채택합니다.

## 채택 기준과 근거 등급

- **operator-collected**: 벤치마크 운영자가 직접 수집한 블라인드 투표 또는 공식 제출 결과입니다.
- **operator-evaluated**: 운영자가 공개 하네스로 실행·채점한 결과입니다.
- **vendor-reported**: 모델 제공사가 공식 시스템 카드·모델 카드·기술 보고서에 공개한 자체 평가입니다.
- `-`는 0점이나 기능 부재가 아니라, 동일 모델·지표·설정의 채택 가능한 공개 수치를 찾지 못했다는 뜻입니다.
- 개발사 평가와 운영자 평가는 하네스, 도구, 샘플링, 추론 강도, 시행 횟수가 다를 수 있으므로 같은 열의 숫자도 자동으로 직접 비교하지 않습니다.

## 확인 통계

| 구분 | 채운 셀 | 빈 셀 | 전체 셀 | 채움률 |
| :--- | ---: | ---: | ---: | ---: |
| 프론티어 모델 (`README.md`, 11×17) | **35** | 152 | 187 | **18.72%** |
| 120B 이하 오픈웨이트 (`small_models_2026.md`, 6×17) | **35** | 67 | 102 | **34.31%** |
| **합계** | **70** | **219** | **289** | **24.22%** |

한 셀에 도구 사용 여부나 서로 다른 공식 하네스 결과를 함께 표시한 경우가 있어, 70개 셀에는 **80개의 숫자 주장**이 들어 있습니다. 운영자 근거가 포함된 것은 **17셀 / 18개 주장**이고, `vendor-reported` 주장은 **62개**입니다. 53개 셀은 개발사 근거만 가지며, gpt-oss SWE 셀 하나는 vendor와 operator 결과를 함께 표시합니다. 조사 전 채움률은 2/289셀(0.69%)이었습니다.

## 모델명·출시일 교정

| 기존 표기 | 교정 결과 | 1차 근거 |
| :--- | :--- | :--- |
| Claude Opus 5 | 공식 출시 모델, 2026-07 | [Anthropic 공식 발표](https://www.anthropic.com/news/claude-opus-5) · [System Card](https://www.anthropic.com/claude-opus-5-system-card) |
| GPT-5.6 Sol | 공식 출시 모델, 2026-07 | [OpenAI 공식 발표](https://openai.com/index/gpt-5-6/) · [Developers 모델 페이지](https://developers.openai.com/api/docs/models/gpt-5.6-sol) |
| Gemini 3.6 Pro | 공식 모델이 없어 **Gemini 3.1 Pro Preview**로 교체 | [Google DeepMind 모델 카드 목록](https://deepmind.google/models/model-cards/) · [Gemini 3.1 Pro 모델 카드](https://deepmind.google/models/model-cards/gemini-3-1-pro/) |
| Grok 4.6 | 공식 출시 모델, 2026-08-12 | [xAI 공식 발표](https://x.ai/news/grok-4-6) |
| DeepSeek V4 | **DeepSeek-V4-Pro (Max)**로 변형 고정 | [DeepSeek 공식 발표](https://api-docs.deepseek.com/news/news260424/) · [공식 모델 카드](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro) |
| GLM-5.3 | 공식 출시 모델, 2026-08-14 | [Z.ai 공식 발표](https://z.ai/blog/glm-5.3) |
| Qwen 3 (Max) | **Qwen3-Max-Thinking**으로 변형 고정 | [Qwen 공식 발표](https://qwen.ai/blog?id=qwen3-max-thinking) |
| Llama 4 (400B) | **Llama 4 Maverick 17B-128E Instruct**, 400B total / 17B active, 2025-04 | [Meta 공식 모델 카드](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E-Instruct) |
| Kimi K3, 2026-05 | **Kimi K3**, 2026-07 | [Kimi 공식 발표](https://www.kimi.com/en/blog/kimi-k3) |
| Mistral Large 3, 2026-06 | **Base / Instruct 행 분리**, 2025-12 | [Mistral 공식 발표](https://mistral.ai/news/mistral-3) · [공식 모델 카드](https://huggingface.co/mistralai/Mistral-Large-3-675B-Instruct-2512) |
| Qwen 3 (72B) | **행 삭제** — 공식 Qwen3 크기 목록에 72B가 없음 | [Qwen3 공식 발표](https://qwenlm.github.io/blog/qwen3/) |
| Mistral Small 4 (24B) | **119B total / 6.5B active**, 2026-03 | [Mistral 공식 발표](https://mistral.ai/news/mistral-small-4/) · [공식 모델 카드](https://huggingface.co/mistralai/Mistral-Small-4-119B-2603) |
| Llama 4 Scout (17B) | **109B total / 17B active**, 2025-04 | [Meta 공식 모델 카드](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E-Instruct) |
| gpt-oss / Gemma 3 / Phi-4 / Qwen3의 2026 출시 표기 | 각각 2025-08 / 2025-03 / 2024-12 / 2025-04로 교정 | [gpt-oss](https://openai.com/index/introducing-gpt-oss/) · [Gemma 3](https://blog.google/innovation-and-ai/technology/developers-tools/gemma-3/) · [Phi-4](https://huggingface.co/microsoft/phi-4) · [Qwen3](https://qwenlm.github.io/blog/qwen3/) |

## 프론티어 모델 — 채택한 성능값

| ID | 모델 | 벤치마크와 채택값 | 결과 근거 | 근거 유형 / 핵심 설정 |
| :--- | :--- | :--- | :--- | :--- |
| `frontier-claude-opus-5` | Claude Opus 5 | SWE-bench Verified **96.0%**<br>HLE **56.3%** no-tools / **64.7%** tools<br>OSWorld 2.0 **70.6%** success@1 | [Anthropic System Card §8.2, p.149](https://www.anthropic.com/claude-opus-5-system-card#page=149) · [§8.1, p.148](https://www.anthropic.com/claude-opus-5-system-card#page=148) · [§8.12.3, p.173](https://www.anthropic.com/claude-opus-5-system-card#page=173) | vendor-reported. SWE 500문항·5회 평균·adaptive thinking/max effort. HLE no-tools/tools 분리. OSWorld first-attempt success, 5회 평균, 최대 500 actions. |
| `frontier-gpt-5-6-sol` | GPT-5.6 Sol | OSWorld 2.0 Partial **62.6%** | [OpenAI GPT-5.6 공식 발표, Computer use 표](https://openai.com/index/gpt-5-6/) | vendor-reported. 공개 표가 전체 하네스 설정을 제공하지 않음. 비교 모델 값과 운영자 표를 대조해 Partial reward로 식별. |
| `frontier-gemini-3-1-pro` | Gemini 3.1 Pro Preview | SWE-bench Verified **80.6%**<br>τ² Retail **90.8%** / Telecom **99.3%**<br>GPQA Diamond **94.3%**<br>HLE **44.4%** no-tools / **51.4%** Search+Code | [Google DeepMind Gemini 3.1 Pro Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) | vendor-reported, Thinking High. SWE single attempt. τ²는 domain별 값이며 종합 점수가 아님. HLE 도구 설정 분리. |
| `frontier-deepseek-v4-pro-max` | DeepSeek-V4-Pro (Max) | SWE-bench Verified **80.6%**<br>LiveCodeBench v6 **93.5%**<br>GPQA Diamond **90.1%**<br>HLE **37.7%** no-tools / **48.2%** tools<br>MMLU-Pro **87.5%** | [DeepSeek 공식 모델 카드](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro) · [공식 기술 보고서](https://arxiv.org/abs/2606.19348) | vendor-reported, Max effort. LCB pass@1-CoT. SWE는 in-house bash/file-edit harness, 500 steps. Base 체크포인트 값과 혼합하지 않음. |
| `frontier-glm-5-3` | GLM-5.3 | HLE with tools **62.5%** | [Z.ai GLM-5.3 공식 발표](https://z.ai/blog/glm-5.3) | vendor-reported. temp 1.0, top-p .95, max generation 163,840, context management 사용. no-tools HLE와 비교 금지. |
| `frontier-qwen3-max-thinking` | Qwen3-Max-Thinking | SWE-bench Verified **75.3%**<br>τ²-Bench **82.1%**<br>BFCL V4 **67.7%**<br>LiveCodeBench v6 **85.9%**<br>HLE text **30.2%** / tools **49.8%**<br>MMLU-Pro **85.7%** | [Qwen3-Max-Thinking 공식 발표](https://qwen.ai/blog?id=qwen3-max-thinking) | vendor-reported. τ² 공식 setting/no custom scaffold. BFCL 최대 100 interaction turns. HLE 30.2는 text subset. SWE scaffold·시행 횟수는 미공개. |
| `frontier-llama-4-maverick-it` | Llama 4 Maverick 17B-128E Instruct | LiveCodeBench **43.4%**<br>GPQA Diamond **69.8%**<br>MMLU-Pro **80.5%**<br>MMMU **73.4%**<br>MathVista **73.7%** | [Meta 공식 모델 카드](https://huggingface.co/meta-llama/Llama-4-Maverick-17B-128E-Instruct) | vendor-reported, bf16 instruct checkpoint. 모두 0-shot. LCB pass@1, 2024-10-01–2025-02-01. Base checkpoint의 MMLU/MATH와 혼합하지 않음. |
| `frontier-kimi-k3-max` | Kimi K3 (Max) | GPQA Diamond **93.5%**<br>HLE Full **43.5%** no-tools / **56.0%** general tools | [Moonshot AI 공식 모델 카드](https://huggingface.co/moonshotai/Kimi-K3/blob/main/README.md) | vendor-reported, effort=max, temp 1.0. no-tools는 single-step/top-p .95, tools는 agentic/top-p 1.0. |
| `frontier-mistral-large-3-base` | Mistral Large 3 Base (675B) | GPQA Diamond **43.9%** | [Mistral 공식 모델 카드의 Base Model Benchmark Comparison](https://huggingface.co/mistralai/Mistral-Large-3-675B-Instruct-2512) | vendor-reported, Base checkpoint, 5-shot, no CoT. Instruct 행에 옮기지 않음. |

### Arena Text Overall 운영자 스냅샷

공식 [Arena Text 리더보드](https://arena.ai/leaderboard/text)의 **Overall / Style Control ON**, 화면 스냅샷 날짜 2026-08-12, 확인일 2026-08-18 기준입니다. README는 아래 rating을 정수로 반올림합니다.

| 문서 모델 | exact Arena model key | rating | README 표시 | 95% CI | 근거 유형 |
| :--- | :--- | ---: | ---: | :---: | :--- |
| Claude Opus 5 | `claude-opus-5-high` | 1493.2301 | **1493** | 1487.9256–1498.5346 | operator-collected, 20,030 votes |
| Claude Opus 5 | `claude-opus-5-max` | 1489.4036 | **1489** | 1482.4536–1496.3536 | operator-collected, 9,679 votes |
| GPT-5.6 Sol | `gpt-5.6-sol-xhigh` | 1481.0972 | **1481** | 1475.3718–1486.8227 | operator-collected, 15,558 votes |
| Gemini 3.1 Pro Preview | `gemini-3.1-pro-preview` | 1486.4669 | **1486** | 1483.1338–1489.8000 | operator-collected, 95,107 votes |
| Grok 4.6 | `grok-4.6-high` | 1463.6171 | **1464** | 1453.4137–1473.8205 | operator-collected, 3,396 votes |
| Llama 4 Maverick Instruct | `llama-4-maverick-17b-128e-instruct` | 1326.9917 | **1327** | 동적 UI 참조 | operator-collected |
| Kimi K3 (Max) | `kimi-k3-max` | 1488.7811 | **1489** | 1482.5812–1494.9811 | operator-collected, 11,969 votes |
| Mistral Large 3 Instruct | `mistral-large-3` | 1414.6894 | **1415** | 1411.5201–1417.8587 | operator-collected, 59,309 votes |

## 120B 이하 오픈웨이트 — 채택한 개발사 결과

| ID | 모델 | 벤치마크와 채택값 | 결과 근거 | 근거 유형 / 핵심 설정 |
| :--- | :--- | :--- | :--- | :--- |
| `small-gpt-oss-120b-vendor` | gpt-oss-120b | SWE-bench Verified **62.4%**<br>GPQA Diamond **80.1%** no-tools / **80.9%** tools<br>HLE **14.9%** no-tools / **19.0%** tools<br>MMLU **90.0%** | [OpenAI gpt-oss Model Card, Table 3](https://cdn.openai.com/pdf/419b6906-9da6-406c-a19d-1bb078ac7637/oai_gpt-oss_model_card.pdf) · [공식 모델 메타데이터](https://developers.openai.com/api/docs/models/gpt-oss-120b) | vendor-reported, high reasoning. 모든 eval은 공개 MXFP4 체크포인트. SWE agent scaffold는 카드에 미공개. |
| `small-gemma-3-27b-it` | Gemma 3 27B-IT | HumanEval **87.8%**<br>GPQA Diamond **42.4%**<br>MMLU **76.9%**<br>MMLU-Pro **67.5%**<br>MATH **89.0%**<br>GSM8K **95.9%**<br>MMMU val **64.9%**<br>MathVista testmini **67.6%** | [Google Gemma 3 Model Card](https://ai.google.dev/gemma/docs/core/model_card_3) · [Gemma 3 Technical Report](https://arxiv.org/abs/2503.19786) | vendor-reported, 27B instruction-tuned. HumanEval pass@1. text 지표 0-shot, GPQA/MMLU-Pro/GSM8K CoT. |
| `small-mistral-small-4` | Mistral Small 4 119B-A6.5B | GPQA Diamond **71.2%**<br>MMLU-Pro **78.0%** | [Mistral 공식 모델 카드](https://huggingface.co/mistralai/Mistral-Small-4-119B-2603) · [고정 benchmark chart](https://huggingface.co/mistralai/Mistral-Small-4-119B-2603/resolve/a11f36bebf709121056b1dbcc943d1c6afbe494d/images/image2.png) | vendor-reported, `reasoning_effort=high`, 권장 temp .7. shot 수는 미공개. |
| `small-llama-4-scout-vendor` | Llama 4 Scout 17B-16E Instruct | LiveCodeBench **32.8%**<br>GPQA Diamond **57.2%**<br>MMLU-Pro **74.3%**<br>MMMU **69.4%**<br>MathVista **70.7%** | [Meta 공식 모델 카드](https://huggingface.co/meta-llama/Llama-4-Scout-17B-16E-Instruct) | vendor-reported, bf16 instruct checkpoint, 0-shot. LCB pass@1, 2024-10-01–2025-02-01. |
| `small-phi-4-vendor` | Phi-4 | HumanEval **82.6%**<br>GPQA Diamond **56.1%**<br>MMLU **84.8%**<br>MMLU-Pro **70.4%**<br>MATH **80.4%** | [Microsoft 공식 모델 카드](https://huggingface.co/microsoft/phi-4) · [Phi-4 Technical Report](https://arxiv.org/abs/2412.08905) | vendor-reported. HumanEval/GPQA/MMLU/MATH는 simple-evals, temp .5. MMLU-Pro는 Microsoft 내부 eval 설정. |
| `small-qwen3-8b-thinking` | Qwen3-8B (Thinking) | LiveCodeBench v5 **57.5%**<br>GPQA Diamond **62.0%** | [Qwen3 Technical Report, Table 17](https://arxiv.org/abs/2505.09388) | vendor-reported. Thinking mode, temp .6/top-p .95/top-k 20, max output 32,768. GPQA는 문항당 10회 sampling 평균. |

## 120B 이하 오픈웨이트 — 운영자 결과

### SWE-bench Verified

| 모델·시스템 | 채택값 | 고정 결과 근거 | 근거 유형 / 설정 |
| :--- | ---: | :--- | :--- |
| `mini-SWE-agent + gpt-oss-120b` | **26.0%** | [SWE-bench experiments metadata, commit `1faa91c`](https://github.com/swe-bench/experiments/blob/1faa91cade0562ba62b66c1c99e71f7b72d96f13/evaluation/bash-only/20250807_mini-v1.7.0_gpt-oss-120b/metadata.yaml) · [공식 generated leaderboard data](https://github.com/swe-bench/swe-bench.github.io/blob/f42505b21a0eb31a9cc1204caafcbe0da6c1a259/data/leaderboards.json) | operator-evaluated, mini-SWE-agent v1.7.0, 1 attempt, checked=true |
| `mini-SWE-agent + Llama 4 Scout Instruct` | **9.06%** | [SWE-bench experiments metadata, commit `1faa91c`](https://github.com/swe-bench/experiments/blob/1faa91cade0562ba62b66c1c99e71f7b72d96f13/evaluation/bash-only/20250720_mini-v0.0.0-Llama-4-Scout-17B-Instruct/metadata.yaml) · [공식 generated leaderboard data](https://github.com/swe-bench/swe-bench.github.io/blob/f42505b21a0eb31a9cc1204caafcbe0da6c1a259/data/leaderboards.json) | operator-evaluated, mini-SWE-agent v0.0.0, 1 attempt, checked=true |

### BFCL V4 Overall Accuracy

[BFCL 공식 리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html)와 [공식 결과 CSV](https://gorilla.cs.berkeley.edu/data_overall.csv), 운영자 commit [`f7cf735`](https://github.com/ShishirPatil/gorilla/commit/f7cf7359b7ac615a0b294831c5ba2bc95ee4a000), `bfcl-eval` 2025.12.17 기준입니다.

| exact BFCL row | 형식 | Overall Accuracy | 근거 유형 |
| :--- | :---: | ---: | :--- |
| `Gemma-3-27b-it (Prompt)` | Prompt | **29.47%** | operator-evaluated |
| `Llama-4-Scout-17B-16E-Instruct (FC)` | native FC | **28.13%** | operator-evaluated |
| `Phi-4 (Prompt)` | Prompt | **28.79%** | operator-evaluated |
| `Qwen3-8B (FC)` | native FC | **42.57%** | operator-evaluated. Prompt 대안은 40.43%이며 표에는 FC만 채택. |

### Arena Text Overall

동일한 [공식 Arena 스냅샷](https://arena.ai/leaderboard/text) 기준입니다.

| 모델 | exact Arena model key | rating | 문서 표시 | 95% CI | 근거 유형 |
| :--- | :--- | ---: | ---: | :---: | :--- |
| gpt-oss-120b | `gpt-oss-120b` | 1352.2256 | **1352** | 1347.8827–1356.5686 | operator-collected, 30,775 votes |
| Gemma 3 27B-IT | `gemma-3-27b-it` | 1365.8657 | **1366** | 1362.1899–1369.5415 | operator-collected, 47,585 votes |
| Llama 4 Scout Instruct | `llama-4-scout-17b-16e-instruct` | 1322.4888 | **1322** | 1317.7824–1327.1953 | operator-collected, 30,402 votes |
| Phi-4 | `phi-4` | 1256.1473 | **1256** | 1251.5468–1260.7478 | operator-collected, 24,126 votes |

## 제거·제외한 대표 주장

| 기존 또는 후보 주장 | 처리 | 1차 출처 확인 결과 |
| :--- | :---: | :--- |
| Claude Opus 5 · SWE-bench **52.3%** | **96.0%로 교정** | [Anthropic System Card](https://www.anthropic.com/claude-opus-5-system-card#page=149)가 500문항·5회 평균 96.0%를 명시. |
| Claude Opus 5 · WebArena **61.8%** | **제거** | [WebArena 공식 리더보드](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ/edit?usp=sharing)와 Anthropic 자료에 해당 결과가 없음. |
| GPT-5.6 Sol · GAIA **46.8%** | **제거** | [GAIA 공식 결과](https://huggingface.co/datasets/gaia-benchmark/results_public)에 model-only exact row가 없음. agent/scaffold 제출은 모델 고유 점수로 사용하지 않음. |
| GPT-5.6 Sol · OSWorld **36.5%** | **62.6% Partial로 교정** | [OpenAI 공식 발표](https://openai.com/index/gpt-5-6/)의 실제 OSWorld 2.0 값. |
| GPT-5.6 Sol · τ² **71.2%** | **제거** | 71.2는 OpenAI 발표의 SEC-Bench Pro. [Sierra 공식 제출](https://github.com/sierra-research/tau2-bench/blob/main/web/leaderboard/public/submissions/gpt-5-6-sol_sierra_2026-08-04/submission.json)은 τ² core가 null이고 τ³ Banking만 제공. |
| GPT-5.6 Sol · BFCL **93.8%** | **제거** | [BFCL V4 공식 결과](https://gorilla.cs.berkeley.edu/data_overall.csv)에 해당 행이 없음. |
| GPT-5.6 Sol · LiveCodeBench **79.5%** | **제거** | 79.5는 OpenAI 발표에서 GPT-5.6 Luna의 MMMU Pro 값이며 [LCB 공식 데이터](https://livecodebench.github.io/performances_generation.json)에 GPT-5.6이 없음. |
| GPT-5.6 Sol · HumanEval **96.1%** | **제거** | 공식 GPT-5.6 자료에 직접 결과가 없고 HumanEval은 중앙 운영자 리더보드가 없음. |
| Qwen3-Max · GPQA **87.4%** | **제외** | Qwen 출처 표의 label이 `GPQA`일 뿐 Diamond subset을 명시하지 않아 GPQA Diamond 열에 넣지 않음. |
| GLM-5.3 · HLE **62.5%** | **도구 설정을 붙여 채택** | 공식값은 plain HLE가 아니라 `HLE w/ Tools`; README에 이를 명시. |
| Gemma 3 · LiveCodeBench | **제외** | 같은 공식 자료 안에 29.7과 39.0이 공존하고 평가 기간·버전을 확정할 수 없음. |
| Mistral Small 4 · LiveCodeBench **63.6%** | **제외** | 공식 chart에 기간·버전·pass@k가 없음. |
| Qwen3-8B · MATH-500 **97.4%** | **제외** | MATH-500은 문서의 MATH 열과 다른 benchmark. |
| gpt-oss · Tau-Bench Retail/Airline | **제외** | OpenAI 카드의 값은 원래 τ-bench이며 τ²가 아님. |
| Claude/GPT/Kimi · τ³ Banking | **제외** | τ³ Banking은 τ² core와 다른 벤치마크이므로 τ² 열에 옮기지 않음. |
| DeepSeek V4 Pro Base의 MMLU/MATH/GSM8K | **제외** | 표는 Max post-trained 변형으로 고정했으므로 Base 체크포인트 수치를 혼합하지 않음. |
| Llama 4 Base의 MMLU/MATH | **제외** | 표는 Instruct 체크포인트로 고정. |
| Mistral Large 3 LiveCodeBench **34.4%** | **제외** | vendor chart가 release window와 pass@k를 공개하지 않음. |

## 벤치마크 정의·결과 URL

아래 링크는 벤치마크와 평가 조건을 정의하거나 운영자 결과를 게시합니다. 링크 자체만으로 특정 모델 점수를 증명하지는 않습니다.

| 벤치마크 | 공식 정의 / 결과 | 기록 시 필수 한정자 |
| :--- | :--- | :--- |
| SWE-bench Verified | [공식 사이트](https://www.swebench.com/) · [experiments](https://github.com/swe-bench/experiments) | variant, agent/scaffold, 시행 횟수, 추론 설정 |
| GAIA | [리더보드](https://huggingface.co/spaces/gaia-benchmark/leaderboard) · [공개 결과](https://huggingface.co/datasets/gaia-benchmark/results_public) | test/dev, agent·tool·router 구성, 제출자 신원 |
| OSWorld 2.0 | [프로젝트](https://osworld-v2.xlang.ai/) · [공식 결과 JSON](https://osworld-v2.xlang.ai/static/data/leaderboard/official-results.json) · [`v2026.06.24`](https://github.com/xlang-ai/OSWorld-V2/releases/tag/v2026.06.24) | task version, step budget, Binary/Partial/success@1 |
| WebArena | [원 benchmark](https://webarena.dev/og/) · [공식 리더보드](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ/edit?usp=sharing) | WebArena/VisualWebArena, harness, trajectory |
| τ² / τ³ | [τ² core](https://taubench.com/leaderboard?benchmark=core) · [τ³ knowledge](https://taubench.com/leaderboard?benchmark=knowledge) · [저장소](https://github.com/sierra-research/tau2-bench) | 세대, domain, Pass^k, user simulator, task version |
| BFCL V4 | [리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html) · [CSV](https://gorilla.cs.berkeley.edu/data_overall.csv) | V4/commit, Overall/세부 범주, FC/Prompt |
| LiveCodeBench | [리더보드](https://livecodebench.github.io/leaderboard.html) · [결과 JSON](https://livecodebench.github.io/performances_generation.json) | version/date window, scenario, pass@k |
| HumanEval | [OpenAI 저장소](https://github.com/openai/human-eval) | pass@k, sample 수, temperature; 공식 중앙 leaderboard 없음 |
| GPQA Diamond | [공식 저장소](https://github.com/idavidrein/gpqa) | Diamond/Main/Extended subset, shot, sampling |
| HLE | [공식 프로젝트](https://lastexam.ai/) | Full/Text subset, tools, browsing blocklist, token budget |
| MMLU | [공식 저장소](https://github.com/hendrycks/test) | shot 수, accuracy/EM, checkpoint |
| MMLU-Pro | [공식 dataset](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro) | shot, CoT, macro average/EM |
| MATH | [공식 저장소](https://github.com/hendrycks/math) | MATH vs MATH-500, shot, answer extraction |
| GSM8K | [OpenAI 저장소](https://github.com/openai/grade-school-math) | GSM8K vs MGSM, shot, CoT |
| MMMU | [공식 프로젝트](https://mmmu-benchmark.github.io/) | MMMU/MMMU-Pro, val/test, vision setting |
| MathVista | [공식 프로젝트](https://mathvista.github.io/) | test/testmini, shot, answer extraction |
| Arena Text | [공식 리더보드](https://arena.ai/leaderboard/text) | exact model key, category, Style Control, snapshot date, CI/votes |

## 비교 주의사항

- README의 표는 “가장 높은 숫자” 순위표가 아니라 공개 출처 지도입니다. 설정이 다르면 숫자 크기만 비교하지 않습니다.
- SWE-bench의 vendor score와 `mini-SWE-agent` 운영자 score는 같은 모델이라도 서로 다른 시스템 결과입니다.
- Arena는 동적 데이터입니다. 위 값은 스냅샷 날짜와 exact model key를 보존했으며 이후 달라질 수 있습니다.
- HLE, OSWorld, τ, BFCL, LiveCodeBench는 설정 차이가 결과에 크게 영향을 줍니다. 셀의 짧은 표기보다 이 문서의 상세 조건이 우선합니다.
- 동적 리더보드에는 조회일을, 고정 결과에는 가능하면 commit/tag를 기록합니다.
