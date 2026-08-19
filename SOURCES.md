# Benchmark Result Provenance

검증 기준일: **2026-08-19 (KST)**

프론티어 4개와 recent open-weight 5개의 공식 원문을 Browser에서 확인했습니다. recent 로스터의 기본 크기 기준은 총 120B 이하이지만, 사용자가 요청한 최신 `K-EXAONE 2.0 A37B`는 활성 규모를 대표 이름으로 쓰는 명시적 size exception으로 포함했습니다. A37B는 토큰당 약 37B active parameter이며 실제 total은 750B입니다. gpt-oss-120b/20b도 별도 참고 기준선으로 조사했지만, 두 모델은 2025-08-05 공개라 2026-04-01 이후 로스터와 채움률 통계에서는 제외했습니다.

## 검증 규칙

- **vendor-reported**: 모델 제공사의 공식 모델 카드, 시스템 카드, 기술 보고서 또는 공식 평가 발표에 실린 값.
- **vendor-reported / reproducible**: 위 조건에 더해 공식 실행 recipe·harness·반복 설정이 공개된 값.
- **partial config**: 모델과 정확한 benchmark 이름·값은 확인했지만 shot, tools, pass@k, trials, decoding 또는 scaffold 일부가 미공개.
- `Verified`, `Pro`, `Multilingual`, `v3/v4/v5/v6`, `MMMU/MMMU-Pro`, `τ-bench/τ²/τ³`처럼 이름이 다르면 별도 benchmark로 취급.
- agent scaffold가 있으면 bare-model 결과로 바꾸지 않고 `model + scaffold`로 기록.
- 모델 카드의 경쟁 모델 비교열은 사용하지 않고 **해당 카드 소유자의 정확한 모델 열**만 추출.
- 일반 권장 sampling 값을 개별 benchmark 설정으로 소급하지 않음.
- total-parameter 기준 예외는 모델별로 명시하며, active parameter나 양자화 저장 형식으로 total parameter를 낮춰 쓰지 않음.

## 확인 통계

| 범위 | Browser에서 공식 원문 확인 | 공통 비교 채움 | 공통 비교 미확인 | 채움률 |
| :--- | ---: | ---: | ---: | ---: |
| 프론티어 4개 모델, 11개 열 | **4/4** | **27/44** | 17/44 | **61.36%** |
| recent open-weight 5개, 8개 열 | **5/5** | **24/40** | 16/40 | **60.00%** |
| **추적 모델 합계** | **9/9** | **51/84** | **33/84** | **60.71%** |
| 참고용 gpt-oss 2개 | **2/2** | 통계 제외 | 통계 제외 | — |

추가·전문화 표와 gpt-oss 참고표의 수치는 version, subset 또는 출시 기간이 달라 공통 행렬 분모에서 제외했습니다. 추적 대상에서 모든 행이 빈 benchmark 열은 제거했습니다.

외부 URL은 fragment 제거 기준 **75개**를 점검했습니다. 자동 HTTP 검사에서 **71개가 2xx**, OpenAI 페이지 4개는 자동 요청에 403을 반환했지만 Browser에서 정상 열림을 확인해 **75/75 접근 가능**으로 판정했습니다.

## 모델 신원과 Browser 확인 원문

| 구분 | 정확한 모델/체크포인트 | 공개일 | Browser 확인 원문 | 카드/보고서 상태 |
| :--- | :--- | :---: | :--- | :--- |
| Frontier | Claude Opus 5 (`claude-opus-5`) | 2026-07-24 | [Anthropic 발표](https://www.anthropic.com/news/claude-opus-5) · [System Card landing](https://www.anthropic.com/claude-opus-5-system-card) · [고정 PDF](https://www-cdn.anthropic.com/b514064af1408018e64b1ad24e7d5e75850b4ffd/Claude%20Opus%205%20System%20Card.pdf) | 공식 System Card 확인 |
| Frontier | GPT-5.6 Sol (`gpt-5.6-sol`) | 2026-07-09 GA | [6/26 preview](https://openai.com/index/previewing-gpt-5-6-sol/) · [7/9 발표·평가표](https://openai.com/index/gpt-5-6/) · [System Card](https://deploymentsafety.openai.com/gpt-5-6) · [고정 PDF](https://deploymentsafety.openai.com/gpt-5-6/gpt-5-6.pdf) · [API 문서](https://developers.openai.com/api/docs/models/gpt-5.6-sol) | 발표 표와 System Card 확인 |
| Frontier | Gemini 3.1 Pro Preview (`gemini-3.1-pro-preview`) | 2026-02-19 | [DeepMind Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) · [고정 Model Card PDF](https://storage.googleapis.com/deepmind-media/Model-Cards/Gemini-3-1-Pro-Model-Card.pdf) · [평가 방법론 PDF](https://storage.googleapis.com/deepmind-media/gemini/gemini_3-1_pro_model_evaluation.pdf) | 공식 카드·방법론 확인 |
| Frontier | Grok 4.6 (`grok-4.6`) | 2026-08-12 | [xAI 발표·평가표](https://x.ai/news/grok-4-6) · [모델 문서](https://docs.x.ai/developers/models/grok-4.6) | 별도 공식 model card/tech report는 2026-08-19 현재 발견하지 못함 |
| Open weight | `google/gemma-4-31B-it` | 2026-04-02 | [고정 카드](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [Google 출시](https://blog.google/innovation-and-ai/technology/developers-tools/gemma-4/) · [기술 보고서 v2](https://arxiv.org/html/2607.02770v2) | owner card/report 확인 |
| Open weight | `google/diffusiongemma-26B-A4B-it` | 2026-06-10 | [고정 카드](https://huggingface.co/google/diffusiongemma-26B-A4B-it/blob/f7f5b7f5fa82ffc52addd066915886d497f5517b/README.md) · [Google 출시](https://blog.google/innovation-and-ai/technology/developers-tools/diffusion-gemma-faster-text-generation/) | owner card/blog 확인 |
| Open weight | `inclusionAI/LLaDA2.2-flash` | 2026-07-16 | [고정 카드](https://huggingface.co/inclusionAI/LLaDA2.2-flash/blob/ee56264534721014d8e651293543f6dc3fcb1f9c/README.md) · [고정 기술 보고서 PDF](https://raw.githubusercontent.com/inclusionAI/LLaDA2.X/f402f0b52817e1c3586a024ebf89e69ad8ca5523/LLaDA2_2_tech_report.pdf) | owner card/report 확인 |
| Open weight · **size exception** | `LGAI-EXAONE/K-EXAONE-2.0-750B-A37B` | 2026-07-31 | [LG 공식 출시 보도](https://www.lgresearch.ai/news/view?seq=678) · [LG 공식 출시 연혁](https://github.com/LG-AI-EXAONE/K-EXAONE-2.0) · [고정 owner card](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B/blob/b159206982abe02813dae76f0bd568dbd3d4f53f/README.md) · [첫 전체 weight 커밋](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B/commit/b159206982abe02813dae76f0bd568dbd3d4f53f) · [기술 보고서 v1](https://arxiv.org/html/2608.04505v1) | 최신 general-purpose EXAONE · owner card(BF16) · report(Reasoning) · 총 750B 예외 |
| Open weight | `Qwen/Qwen3.8-27B` | 2026-08-13 weight commit | [고정 카드](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md) · [첫 전체 weight 커밋](https://huggingface.co/Qwen/Qwen3.8-27B/commit/72a217afab8029b39e4af1c7273a829995a3dbaf) | owner card/weights 확인 |
| Reference | `openai/gpt-oss-120b` | 2025-08-05 | [OpenAI 모델 문서](https://developers.openai.com/api/docs/models/gpt-oss-120b) · [OpenAI 성능표](https://openai.com/open-models/) · [모델 카드 안내](https://openai.com/index/gpt-oss-model-card/) · [고정 PDF](https://cdn.openai.com/pdf/419b6906-9da6-406c-a19d-1bb078ac7637/oai_gpt-oss_model_card.pdf) · [고정 HF 카드](https://huggingface.co/openai/gpt-oss-120b/blob/b5c939de8f754692c1647ca79fbf85e8c1e70f8a/README.md) | 공식 모델 카드 확인 · 기간 예외 |
| Reference | `openai/gpt-oss-20b` | 2025-08-05 | [OpenAI 모델 문서](https://developers.openai.com/api/docs/models/gpt-oss-20b) · [OpenAI 성능표](https://openai.com/open-models/) · [모델 카드 안내](https://openai.com/index/gpt-oss-model-card/) · [고정 PDF](https://cdn.openai.com/pdf/419b6906-9da6-406c-a19d-1bb078ac7637/oai_gpt-oss_model_card.pdf) · [고정 HF 카드](https://huggingface.co/openai/gpt-oss-20b/blob/6cee5e81ee83917806bbde320786a8fb61efebee/README.md) | 공식 모델 카드 확인 · 기간 예외 |

### 파라미터 수의 산출 근거

recent 모델의 `artifact` 정수는 고정 revision Hugging Face API 응답의 `safetensors.total`을 사용했습니다. gpt-oss는 OpenAI 모델 카드 Table 1의 exact total/active parameter와 checkpoint-size 값을 사용했습니다.

| 체크포인트 | 고정 metadata / 모델 카드 |
| :--- | :--- |
| Gemma 4 31B-IT | [revision 842da379](https://huggingface.co/api/models/google/gemma-4-31B-it/revision/842da3794eaa0b77d5f08bae87a17459d91ff475) |
| DiffusionGemma 26B-A4B-IT | [revision f7f5b7f5](https://huggingface.co/api/models/google/diffusiongemma-26B-A4B-it/revision/f7f5b7f5fa82ffc52addd066915886d497f5517b) |
| LLaDA2.2-flash | [revision ee562645](https://huggingface.co/api/models/inclusionAI/LLaDA2.2-flash/revision/ee56264534721014d8e651293543f6dc3fcb1f9c) |
| K-EXAONE 2.0 A37B | [revision b1592069](https://huggingface.co/api/models/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B/revision/b159206982abe02813dae76f0bd568dbd3d4f53f): owner **~37B active / 750B total**, artifact **749,357,484,800**. A37B는 standalone·total size가 아님. |
| Qwen3.8-27B | [revision 1d4bf0f2](https://huggingface.co/api/models/Qwen/Qwen3.8-27B/revision/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0) |
| gpt-oss-120b | [OpenAI Model Card Table 1](https://arxiv.org/html/2508.10925v1): total **116.83B**, active **5.13B**, checkpoint **60.8 GiB** |
| gpt-oss-20b | [OpenAI Model Card Table 1](https://arxiv.org/html/2508.10925v1): total **20.91B**, active **3.61B**, checkpoint **12.8 GiB** |

## [프론티어 4개 모델](./README.md#frontier-models) — 점수 provenance

| 모델 | 공통 표 채택값 | 근거와 핵심 설정 |
| :--- | :--- | :--- |
| Claude Opus 5 | SWE Verified **96.0**; SWE Pro **79.2**; DeepSWE 1.1 **68.8**; OSWorld 2.0 **70.57**; BrowseComp **90.8**; HLE **56.3/64.7**; ARC-AGI-2 **90.42**; GDPval-AA v2 **1861** | [고정 System Card PDF](https://www-cdn.anthropic.com/b514064af1408018e64b1ad24e7d5e75850b4ffd/Claude%20Opus%205%20System%20Card.pdf). 기본 adaptive thinking/max/default sampling, 평균 5회 unless noted. SWE·DeepSWE·OSWorld는 5회. OSWorld=first-attempt success, 1080p, max 500 actions. HLE는 thinking=auto, 총 token≤1M, compaction 없음, Opus 4.6 grader; tools판=search/fetch/PTC/code. BrowseComp는 10M-token budget, 200K compaction trigger, Opus 4.7 grader와 unreleased effort config 사용. |
| GPT-5.6 Sol | SWE Pro **64.6**; DeepSWE 1.1 **72.7**; Terminal-Bench 2.1 **88.8**; OSWorld 2.0 **62.6**; BrowseComp **90.4**; GPQA Diamond **94.6**; MMMU-Pro **83.0/84.6**; GDPval-AA v2 **1747.8** | [OpenAI 공식 발표 표](https://openai.com/index/gpt-5-6/). 표가 개별 effort/scaffold/trials와 OSWorld metric subtype을 공개하지 않아 partial config. Ultra 점수는 4-agent 설정이므로 Sol 단일행에 섞지 않음. |
| Gemini 3.1 Pro Preview | SWE Verified **80.6**; SWE Pro Public **54.2**; Terminal-Bench 2.0 **68.5**; BrowseComp **85.9**; GPQA Diamond **94.3**; HLE **44.4/51.4**; MMMU-Pro **80.5**; ARC-AGI-2 **77.1** | [Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) · [평가 방법론 PDF](https://storage.googleapis.com/deepmind-media/gemini/gemini_3-1_pro_model_evaluation.pdf). Thinking High, pass@1, single attempt, default sampling. SWE Verified 10회와 +0.6 corrected-harness 조정. SWE Pro 5회. HLE=full set(text+MM), no-tools/Search(blocklist)+Code. Terminal=Terminus-2. |
| Grok 4.6 High | DeepSWE 1.1 **65.9**; Terminal-Bench 3.0 **26.0**; GDPval-AA v2 **1753** | [xAI 공식 발표](https://x.ai/news/grok-4-6). 표는 `Grok 4.6 High`를 명시하지만 tools/scaffold/trials는 미공개. 별도 공식 model card/tech report를 찾지 못해 발표 밖 설정을 추정하지 않음. |

### 프론티어 추가값의 근거

- Claude의 README 추가값은 모두 같은 [System Card PDF](https://www-cdn.anthropic.com/b514064af1408018e64b1ad24e7d5e75850b4ffd/Claude%20Opus%205%20System%20Card.pdf)의 capability evaluation 절에서 추출했습니다. HealthBench Professional은 length-adjusted **59.8**과 raw **73.4**를 구분합니다. Harvey Legal Agent Benchmark 값은 production safeguards와 safety-classifier 발동 시 Opus 4.8 fallback을 포함할 수 있는 system 결과입니다.
- GPT-5.6 Sol의 추가값은 [OpenAI 발표 비교표](https://openai.com/index/gpt-5-6/)의 Sol 열에서 추출했습니다. `Agents' Last Exam`은 같은 페이지 본문 **53.6**, 표 **52.7**로 충돌합니다. BrowseComp 본문 **92.2**는 표의 Sol Ultra 값이고 Sol 열은 **90.4**입니다.
- Gemini 추가값은 [Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/)의 exact preview 열만 사용했습니다. τ² Airline은 grading 품질 문제로 카드가 제외하므로 Retail/Telecom만 기록했습니다.
- Grok 추가값은 [xAI 발표 표](https://x.ai/news/grok-4-6)의 `Grok 4.6 High` 열만 사용했습니다.

## [Recent open-weight 5개](./README.md#recent-open-weight) — 공통 표 provenance

| 모델 | 공통 표 채택값 | 근거 유형·평가 설정 |
| :--- | :--- | :--- |
| Gemma 4 31B-IT | τ² avg **76.9**; LCB v6 **80.0**; IFBench **76.0**; GPQA-D **84.3**; HLE **19.5/26.5**; MMLU-Pro **85.2** | [owner card](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [report](https://arxiv.org/html/2607.02770v2). IT 모델, 기본 thinking. HLE no-tools/search 분리. per-benchmark decoder/trials 일부 미공개. |
| DiffusionGemma 26B-A4B-IT | τ² avg **56.2**; LCB v6 **69.1**; GPQA-D **73.2**; HLE **11.0/11.9**; MMLU-Pro **77.6** | [owner card](https://huggingface.co/google/diffusiongemma-26B-A4B-it/blob/f7f5b7f5fa82ffc52addd066915886d497f5517b/README.md). Entropy-Bound sampler, max48 denoise, temp .8→.4, entropy bound .1, adaptive stop. HLE no-tools/search 분리; shots/pass@k/trials 일부 미공개. |
| LLaDA2.2-flash | SWE-V **49.28**; BFCL v4 **60.78**; IFBench **30.20**; GPQA-D **48.67** | [owner card](https://huggingface.co/inclusionAI/LLaDA2.2-flash/blob/ee56264534721014d8e651293543f6dc3fcb1f9c/README.md) · [report PDF](https://raw.githubusercontent.com/inclusionAI/LLaDA2.X/f402f0b52817e1c3586a024ebf89e69ad8ca5523/LLaDA2_2_tech_report.pdf). 전 값 5회 평균; SWE=Claude Code. 128K, temp1, block32, threshold.5, editing threshold0. BFCL subtype/IF/GPQA 세부 일부 미공개. |
| K-EXAONE 2.0 A37B | SWE-V **68.2**; IFBench **72.6**; GPQA-D **82.2**; HLE text-only **18.3**; MMLU-Pro **83.5** | [고정 owner card BF16 열](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B/blob/b159206982abe02813dae76f0bd568dbd3d4f53f/README.md) · [report Table 6](https://arxiv.org/html/2608.04505v1#S6.T6) · [Appendix C](https://arxiv.org/html/2608.04505v1#A3). report의 K-EXAONE 2.0 **Reasoning** 첫 열만 사용. SWE=mini-SWE-agent, temp1/top-p.95, 32,768 tokens/step, 256K, 4h; trials/pass@k 미공개. 나머지는 owner internal eval의 official setup, trials 일부 미공개. |
| Qwen3.8-27B | LCB v6 **90.3**; IFBench **79.5**; GPQA-D **89.2**; HLE **30.8** | [owner card](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md). HLE=GPT-4o judge. 공통 4개 지표의 mode/tools/trials 일부 미공개; 일반 xhigh 권장값을 평가 설정으로 소급하지 않음. |

## [참고용 gpt-oss](./README.md#gpt-oss-reference) — 점수 provenance

OpenAI 모델 카드 Table 3의 **high reasoning effort** 열과 기본 system prompt/pass@1 결과를 사용했습니다. 모든 평가는 두 모델의 **MXFP4 양자화 체크포인트**로 수행됐습니다. SWE의 scaffold·trials, GPQA/HLE의 정확한 tool 구성·shots·trials, HLE subset·judge 등은 표에 공개되지 않아 partial config입니다.

| 모델 | 참고표 채택값 | 고정 근거 |
| :--- | :--- | :--- |
| gpt-oss-120b | SWE-V **62.4**; GPQA-D **80.1/80.9** no-tools/tools; HLE **14.9/19.0** no-tools/tools; MMLU **90.0**; AIME 2025 **92.5/97.9** no-tools/tools | [OpenAI 고정 Model Card PDF](https://cdn.openai.com/pdf/419b6906-9da6-406c-a19d-1bb078ac7637/oai_gpt-oss_model_card.pdf) · [HTML Table 3](https://arxiv.org/html/2508.10925v1) |
| gpt-oss-20b | SWE-V **60.7**; GPQA-D **71.5/74.2** no-tools/tools; HLE **10.9/17.3** no-tools/tools; MMLU **85.3**; AIME 2025 **91.7/98.7** no-tools/tools | [OpenAI 고정 Model Card PDF](https://cdn.openai.com/pdf/419b6906-9da6-406c-a19d-1bb078ac7637/oai_gpt-oss_model_card.pdf) · [HTML Table 3](https://arxiv.org/html/2508.10925v1) |

OpenAI의 [오픈 모델 요약표](https://openai.com/open-models/)는 GPQA에 no-tools 값을, HLE와 AIME에 tools 값을 한 표에서 사용합니다. 이 저장소는 요약값을 섞지 않고 Model Card Table 3의 도구 구분을 보존했습니다. `Tau-Bench Retail/Airline`은 2024 original τ-bench이므로 τ² 공통열에 넣지 않았습니다.

## 추가 공식 결과 provenance

| 모델 | 추가 결과가 실린 고정 근거 | extraction/config 메모 |
| :--- | :--- | :--- |
| Gemma 4 31B-IT | [card](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [report Table 5 및 부록](https://arxiv.org/html/2607.02770v2) | IT/Thinking 열. MMMLU, MMMU-Pro, MATH-Vision을 각각 MMLU/MMMU/MathVista로 바꾸지 않음. |
| DiffusionGemma | [owner card full table](https://huggingface.co/google/diffusiongemma-26B-A4B-it/blob/f7f5b7f5fa82ffc52addd066915886d497f5517b/README.md) | own IT column. lower-is-better OmniDoc edit distance 단위 유지. |
| LLaDA2.2-flash | [owner card](https://huggingface.co/inclusionAI/LLaDA2.2-flash/blob/ee56264534721014d8e651293543f6dc3fcb1f9c/README.md) · [report Tables 1–2](https://raw.githubusercontent.com/inclusionAI/LLaDA2.X/f402f0b52817e1c3586a024ebf89e69ad8ca5523/LLaDA2_2_tech_report.pdf) | vendor-labelled τ² 80.33은 인용 문헌 불일치 때문에 supplemental claim으로만 보존. LCB version 미공개. |
| K-EXAONE 2.0 A37B | [고정 owner card BF16 table](https://huggingface.co/LGAI-EXAONE/K-EXAONE-2.0-750B-A37B/blob/b159206982abe02813dae76f0bd568dbd3d4f53f/README.md) · [report Table 6](https://arxiv.org/html/2608.04505v1#S6.T6) · [Appendix C](https://arxiv.org/html/2608.04505v1#A3) | first K-EXAONE 2.0 column only. τ³-Banking은 τ²에 넣지 않음. Terminal 2.1은 Terminus-2/temp1/top-p.95/32,768 tokens per step/256K/4h. Claw-Eval은 patched commit `d3f02d4`; card/report 충돌은 아래 로그에 분리. |
| Qwen3.8-27B | [owner card text/VL tables](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md) | first Qwen3.8 column only. OSWorld-Verified/WebArena-Verified는 OSWorld2/original WebArena와 다름. with-CI/without-CI를 분리. |
| gpt-oss-120b/20b | [OpenAI Model Card Table 3, 9, 10](https://arxiv.org/html/2508.10925v1) | Table 3은 high reasoning. AIME/GPQA/HLE/Codeforces의 no-tools/tools를 분리하고 Tau-Bench Retail/Airline은 original τ-bench로 보존. Table 9·10의 SimpleQA/PersonQA/BBQ는 effort 미공개이며 원문 proportion을 ×100으로 환산; SimpleQA/PersonQA는 no browsing. accuracy와 hallucination rate, BBQ ambiguous/disambiguated accuracy를 각각 분리. |

## 명시적 제외·충돌 로그

| 후보 주장 | 판정 | 이유 |
| :--- | :---: | :--- |
| GPT-5.6 Sol `Agents' Last Exam`을 HLE로 사용 | 제외 | 서로 다른 benchmark. 같은 OpenAI 페이지 내부 53.6/52.7 충돌도 별도 주석 처리. |
| GPT-5.6 Sol OSWorld 2.0을 `Partial`로 단정 | 제외 | 공식 발표 표가 62.6은 주지만 Binary/Partial subtype을 밝히지 않음. |
| Gemini SWE Verified 80.6을 표준 운영자 row로 간주 | 제외 | Google corrected internal harness 및 +0.6 조정, 10회 결과이므로 해당 설정을 함께 기록. |
| Grok 4.6의 발표 밖 scaffold/trials 추정 | 제외 | 공식 model card/tech report가 발견되지 않았고 발표 표도 설정을 공개하지 않음. |
| LLaDA `τ²-Bench 80.33`을 canonical τ²로 채택 | 제외 | 보고서 참고문헌이 Sierra τ²가 아니라 2024 original τ-bench를 가리킴. 원문 주장으로만 보존. |
| K-EXAONE 2.0 A37B `τ³-Banking 14.2`를 τ²로 채택 | 제외 | benchmark generation/domain이 다름. supplemental에만 보존. |
| K-EXAONE 2.0 A37B SciCode/Claw-Eval 단일값 선택 | 보류 | owner card는 SciCode **37.4**, generic Claw-Eval **77.7**; 동봉 report v1 Reasoning Table 6은 SciCode **40.1**, Claw-Eval (general) **80.0**. 설정 차이를 설명하지 않아 두 값을 함께 기록. |
| EXAONE 4.5 점수를 최신 K-EXAONE 2.0 A37B에 사용 | 제외 | 33B multimodal EXAONE 4.5와 `K-EXAONE 2.0 A37B`(750B total text)는 별개 체크포인트·라이선스·평가열. |
| K-EXAONE 2.0 A37B를 ≤120B total 모델로 분류 | 제외 | total 750B이며 active 37B 또는 양자화 형식은 total-parameter 기준을 낮추지 않음. 사용자 지정 size exception으로만 포함. |
| Qwen3.8 OSWorld-Verified/WebArena-Verified를 OSWorld2/WebArena로 변경 | 제외 | benchmark variant 불일치. |
| Gemma MMMLU/MMMU-Pro/MATH-Vision을 MMLU/MMMU/MathVista로 변경 | 제외 | 서로 다른 benchmark. |
| gpt-oss Tau-Bench Retail/Airline을 τ² 열에 사용 | 제외 | OpenAI 카드가 인용하는 것은 2024 original τ-bench. |
| gpt-oss 요약 페이지의 GPQA/HLE/AIME 값을 모두 같은 tools 설정으로 간주 | 제외 | 요약표는 no-tools와 tools 값을 섞으므로 Model Card Table 3의 구분을 사용. |
| 모델 카드 일반 권장 temperature/top-p를 모든 eval에 적용 | 제외 | 해당 benchmark 실제 설정이라는 명시가 없음. |

## Benchmark 정의·운영자 URL

아래 링크는 benchmark 정의 또는 운영자 결과를 설명하며, 그 자체가 README의 모델 점수를 증명하지는 않습니다.

| benchmark | 공식 정의/운영자 URL | 필수 한정자 |
| :--- | :--- | :--- |
| SWE-bench Verified | [공식 사이트](https://www.swebench.com/) · [experiments](https://github.com/swe-bench/experiments) | variant, agent/scaffold, trials |
| SWE-bench Pro | [Scale 공개 저장소](https://github.com/scaleapi/SWE-bench_Pro-os) | public/refined set, scaffold, trials |
| OSWorld 2.0 | [프로젝트](https://osworld-v2.xlang.ai/) · [공식 결과 JSON](https://osworld-v2.xlang.ai/static/data/leaderboard/official-results.json) | task version, Binary/Partial/success |
| τ-bench / τ² / τ³ | [original τ-bench repo](https://github.com/sierra-research/tau-bench) · [τ² core](https://taubench.com/leaderboard?benchmark=core) · [τ³ knowledge](https://taubench.com/leaderboard?benchmark=knowledge) · [τ²/τ³ repo](https://github.com/sierra-research/tau2-bench) | generation, domain, Pass^k, user simulator |
| BFCL | [공식 리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html) · [결과 CSV](https://gorilla.cs.berkeley.edu/data_overall.csv) | version, FC/Prompt, Overall/category |
| LiveCodeBench | [공식 리더보드](https://livecodebench.github.io/leaderboard.html) · [결과 JSON](https://livecodebench.github.io/performances_generation.json) | version/date window, scenario, pass@k |
| IFBench | [AllenAI 공식 저장소](https://github.com/allenai/IFBench) | loose/strict, prompt level, generation |
| IFEval | [Google Research 코드·데이터](https://github.com/google-research/google-research/tree/master/instruction_following_eval) | strict/loose, instruction/prompt, aggregate |
| Multi-IF | [Meta 공식 저장소](https://github.com/facebookresearch/Multi-IF) | language, turns, metric |
| Terminal-Bench | [공식 사이트](https://www.tbench.ai/) · [v2 repo](https://github.com/harbor-framework/terminal-bench-2) · [v2.1 repo](https://github.com/harbor-framework/terminal-bench-2-1) | exact version, agent, timeout, trials |
| GPQA Diamond | [공식 저장소](https://github.com/idavidrein/gpqa) | Diamond subset, shots, sampling |
| HLE | [공식 프로젝트](https://lastexam.ai/) | Full/Text, tools, judge |
| MMLU / MMLU-Pro | [MMLU](https://github.com/hendrycks/test) · [MMLU-Pro](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro) | shots, CoT, accuracy/EM |
| ARC-AGI | [ARC Prize](https://arcprize.org/) | version, verified status, effort |

## 읽는 법

- 이 저장소는 “가장 높은 점수” 순위표가 아니라 **공식 주장과 설정의 출처 지도**입니다.
- operator score와 vendor score, bare model과 agent system, no-tools와 tools는 직접 같은 조건으로 간주하지 않습니다.
- 동적 페이지가 바뀌더라도 재검증할 수 있도록 가능한 경우 HF SHA, Git commit, 고정 PDF를 우선 기록했습니다.
