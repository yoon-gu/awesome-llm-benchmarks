# Benchmark Result Provenance

검증 기준일: **2026-08-19 (KST)**

README.md와 small_models_2026.md를 기존 값에서 이어 고치지 않고, 추적 대상 19개의 공식 원문을 Browser에서 다시 열어 처음부터 재구성했습니다. 모델명·benchmark variant·수치가 함께 표시된 모델 제공사의 공식 카드·기술 보고서·평가 발표만 점수 근거로 채택했습니다.

## 검증 규칙

- **vendor-reported**: 모델 제공사의 공식 모델 카드, 시스템 카드, 기술 보고서 또는 공식 평가 발표에 실린 값.
- **vendor-reported / reproducible**: 위 조건에 더해 공식 실행 recipe·harness·반복 설정이 공개된 값.
- **partial config**: 모델과 정확한 benchmark 이름·값은 확인했지만 shot, tools, pass@k, trials, decoding 또는 scaffold 일부가 미공개.
- `Verified`, `Pro`, `Multilingual`, `v3/v4/v5/v6`, `MMMU/MMMU-Pro`, `τ²/τ³`처럼 이름이 다르면 별도 benchmark로 취급.
- agent scaffold가 있으면 bare-model 결과로 바꾸지 않고 `model + scaffold`로 기록.
- 모델 카드의 경쟁 모델 비교열은 사용하지 않고 **해당 카드 소유자의 정확한 모델 열**만 추출. 예외는 Qwen3.6-35B의 GPQA variant 확인처럼 동일 공급사의 후속 공식 카드가 행명을 더 정확히 밝힌 경우뿐이며 이를 명시.
- 일반 권장 sampling 값을 개별 benchmark 설정으로 소급하지 않음.

## 확인 통계

| 범위 | Browser에서 공식 원문 확인 | 공통 비교 채움 | 공통 비교 미확인 | 채움률 |
| :--- | ---: | ---: | ---: | ---: |
| 프론티어 4개 모델, 11개 열 | **4/4** | **27/44** | 17/44 | **61.36%** |
| 공개 가중치 15개, 13개 열 | **15/15** | **70/195** | 125/195 | **35.90%** |
| **합계** | **19/19** | **97/239** | **142/239** | **40.59%** |

추가·전문화 표의 수치는 version과 subset이 달라 공통 행렬 분모에서 제외했습니다. 공통 표에서는 19개 모델 전체가 빈 benchmark 열을 제거했습니다.

외부 링크는 fragment를 제거해 중복을 합친 **111개**를 검사했습니다. 109개는 HTTP 2xx로 확인했고, 자동 요청에 403을 반환한 OpenAI preview·GA 발표 2개는 인앱 Browser에서 정상 렌더링을 직접 확인해 **111/111 접근 가능**으로 판정했습니다.

## 모델 신원과 Browser 확인 원문

| 구분 | 정확한 모델/체크포인트 | 공개일 | Browser 확인 원문 | 카드/보고서 상태 |
| :--- | :--- | :---: | :--- | :--- |
| Frontier | Claude Opus 5 (`claude-opus-5`) | 2026-07-24 | [Anthropic 발표](https://www.anthropic.com/news/claude-opus-5) · [System Card landing](https://www.anthropic.com/claude-opus-5-system-card) · [고정 PDF](https://www-cdn.anthropic.com/b514064af1408018e64b1ad24e7d5e75850b4ffd/Claude%20Opus%205%20System%20Card.pdf) | 공식 System Card 확인 |
| Frontier | GPT-5.6 Sol (`gpt-5.6-sol`) | 2026-07-09 GA | [6/26 preview](https://openai.com/index/previewing-gpt-5-6-sol/) · [7/9 발표·평가표](https://openai.com/index/gpt-5-6/) · [System Card](https://deploymentsafety.openai.com/gpt-5-6) · [고정 PDF](https://deploymentsafety.openai.com/gpt-5-6/gpt-5-6.pdf) · [API 문서](https://developers.openai.com/api/docs/models/gpt-5.6-sol) | 발표 표와 System Card 확인 |
| Frontier | Gemini 3.1 Pro Preview (`gemini-3.1-pro-preview`) | 2026-02-19 | [DeepMind Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) · [고정 Model Card PDF](https://storage.googleapis.com/deepmind-media/Model-Cards/Gemini-3-1-Pro-Model-Card.pdf) · [평가 방법론 PDF](https://storage.googleapis.com/deepmind-media/gemini/gemini_3-1_pro_model_evaluation.pdf) | 공식 카드·방법론 확인 |
| Frontier | Grok 4.6 (`grok-4.6`) | 2026-08-12 | [xAI 발표·평가표](https://x.ai/news/grok-4-6) · [모델 문서](https://docs.x.ai/developers/models/grok-4.6) | 별도 공식 model card/tech report는 2026-08-19 현재 발견하지 못함 |
| Open weight | `google/gemma-4-31B-it` | 2026-04-02 | [고정 카드](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [Google 출시](https://blog.google/innovation-and-ai/technology/developers-tools/gemma-4/) · [기술 보고서 v2](https://arxiv.org/html/2607.02770v2) | owner card/report 확인 |
| Open weight | `LGAI-EXAONE/EXAONE-4.5-33B` | 2026-04-09 | [고정 카드](https://huggingface.co/LGAI-EXAONE/EXAONE-4.5-33B/blob/570aa4b15a4f45ba1133072b45f50198f6e3b4fd/README.md) · [LG 출시](https://www.lgresearch.ai/blog/view?seq=641) · [기술 보고서](https://arxiv.org/html/2604.08644v1) | owner card/report 확인 |
| Open weight | `Qwen/Qwen3.6-35B-A3B` | 2026-04-15 | [고정 카드](https://huggingface.co/Qwen/Qwen3.6-35B-A3B/blob/995ad96eacd98c81ed38be0c5b274b04031597b0/README.md) · [Qwen 출시](https://qwen.ai/blog?id=qwen3.6-35b-a3b) | owner card/blog 확인 |
| Open weight | `Qwen/Qwen3.6-27B` | 2026-04-22 | [고정 카드](https://huggingface.co/Qwen/Qwen3.6-27B/blob/6a9e13bd6fc8f0983b9b99948120bc37f49c13e9/README.md) · [Qwen 출시](https://qwen.ai/blog?id=qwen3.6-27b) | owner card/blog 확인 |
| Open weight | `nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16` | 2026-04-28 | [고정 카드](https://huggingface.co/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16/blob/24e67ea000b7c2837fc8f9488aa2008524fac8ba/README.md) · [기술 보고서](https://arxiv.org/html/2604.24954v2) | owner card/report 확인 |
| Open weight | `ibm-granite/granite-4.1-30b` | 2026-04-29 | [고정 카드](https://huggingface.co/ibm-granite/granite-4.1-30b/blob/4fae6278f7132abf5e971f9de49ebbad09c54cce/README.md) · [IBM 출시](https://research.ibm.com/blog/granite-4-1-ai-foundation-models) | owner card 확인 |
| Open weight | `openbmb/MiniCPM5-1B` | 2026-05-19 | [고정 카드](https://huggingface.co/openbmb/MiniCPM5-1B/blob/87179e5c1f455ef22e6223592d2d61351b525bfc/README.md) · [공식 changelog](https://github.com/OpenBMB/MiniCPM/blob/719e4fcfabff9b9c16f179c3f2986dfbd6c6047f/README.md) · [결과 이미지](https://raw.githubusercontent.com/OpenBMB/MiniCPM/719e4fcfabff9b9c16f179c3f2986dfbd6c6047f/assets/minicpm5/public_leaderboard_en.png) | owner card/image 확인 |
| Open weight | `tencent/Hy-MT2-30B-A3B` | 2026-05-21 | [고정 카드](https://huggingface.co/tencent/Hy-MT2-30B-A3B/blob/d3ead4dba61c09aac60a261a96ad1df3e705febb/README.md) · [기술 보고서](https://arxiv.org/html/2605.22064v2) · [결과 이미지](https://huggingface.co/tencent/Hy-MT2-30B-A3B/resolve/d3ead4dba61c09aac60a261a96ad1df3e705febb/imgs/main_result.png) | owner card/report 확인 |
| Open weight | `CohereLabs/North-Mini-Code-1.0` | 2026-06-09 | [고정 카드](https://huggingface.co/CohereLabs/North-Mini-Code-1.0/blob/d11e61a842617a22dc328552fa5bb86231ee4f37/README.md) · [Cohere 발표](https://cohere.com/blog/north-mini-code) · [기술 글](https://huggingface.co/blog/CohereLabs/introducing-north-mini-code) · [결과 이미지](https://cdn-uploads.huggingface.co/production/uploads/62668f725fb8d521d94d8451/xR7kZ3X9RKEZrbgD6hpG1.png) | owner card/blog/image 확인 |
| Open weight | `google/diffusiongemma-26B-A4B-it` | 2026-06-10 | [고정 카드](https://huggingface.co/google/diffusiongemma-26B-A4B-it/blob/f7f5b7f5fa82ffc52addd066915886d497f5517b/README.md) · [Google 출시](https://blog.google/innovation-and-ai/technology/developers-tools/diffusion-gemma-faster-text-generation/) | owner card/blog 확인 |
| Open weight | `inclusionAI/LLaDA2.2-flash` | 2026-07-16 | [고정 카드](https://huggingface.co/inclusionAI/LLaDA2.2-flash/blob/ee56264534721014d8e651293543f6dc3fcb1f9c/README.md) · [고정 기술 보고서 PDF](https://raw.githubusercontent.com/inclusionAI/LLaDA2.X/f402f0b52817e1c3586a024ebf89e69ad8ca5523/LLaDA2_2_tech_report.pdf) | owner card/report 확인 |
| Open weight | `LiquidAI/LFM2.5-2.6B` | 2026-08-04 | [고정 카드](https://huggingface.co/LiquidAI/LFM2.5-2.6B/blob/ab00687315bc1298e9d54e9c4b611dde9867ccc2/README.md) · [Liquid 출시](https://www.liquid.ai/blog/lfm2-5-2-6b) | owner card/blog 확인 |
| Open weight | `inclusionAI/Ling-3.0-tiny` | 2026-08-10 | [고정 카드](https://huggingface.co/inclusionAI/Ling-3.0-tiny/blob/2f9b5474a86ecfe63cfc95f5c87ddb3a745bfe2d/README.md) · [결과 이미지](https://cdn-uploads.huggingface.co/production/uploads/6502cf8fbdaeae26417cd3c9/g9Thw4ohjkDGYw0Cq7mKi.png) | owner card/image 확인 |
| Open weight | `nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16` | 2026-08-11 | [고정 카드](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16/blob/d468880b6ad3c6e0d21377ce7242adaea4cc884d/README.md) · [고정 reproducibility index](https://github.com/NVIDIA-NeMo/Gym/blob/a62c30035519f738e583b6c1f08254cde70ced1b/nemotron_recipes/lightning-3.5/reproducibility.md) | owner card + runnable recipes 확인 |
| Open weight | `Qwen/Qwen3.8-27B` | 2026-08-13 weight commit | [고정 카드](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md) · [첫 전체 weight 커밋](https://huggingface.co/Qwen/Qwen3.8-27B/commit/72a217afab8029b39e4af1c7273a829995a3dbaf) | owner card/weights 확인 |

### 정확한 artifact 파라미터 수의 산출 근거

small_models_2026.md의 `artifact` 정수는 아래 고정 revision의 Hugging Face API 응답에 있는 `safetensors.total`을 사용했습니다. 공식 반올림 규모와 active/effective 수는 각 owner model card를 따릅니다.

| 체크포인트 | 고정 HF metadata (`safetensors.total`) |
| :--- | :--- |
| Gemma 4 31B-IT | [revision 842da379](https://huggingface.co/api/models/google/gemma-4-31B-it/revision/842da3794eaa0b77d5f08bae87a17459d91ff475) |
| EXAONE 4.5 33B | [revision 570aa4b1](https://huggingface.co/api/models/LGAI-EXAONE/EXAONE-4.5-33B/revision/570aa4b15a4f45ba1133072b45f50198f6e3b4fd) |
| Qwen3.6-35B-A3B | [revision 995ad96e](https://huggingface.co/api/models/Qwen/Qwen3.6-35B-A3B/revision/995ad96eacd98c81ed38be0c5b274b04031597b0) |
| Qwen3.6-27B | [revision 6a9e13bd](https://huggingface.co/api/models/Qwen/Qwen3.6-27B/revision/6a9e13bd6fc8f0983b9b99948120bc37f49c13e9) |
| Nemotron 3 Nano Omni | [revision 24e67ea0](https://huggingface.co/api/models/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16/revision/24e67ea000b7c2837fc8f9488aa2008524fac8ba) |
| Granite 4.1 30B | [revision 4fae6278](https://huggingface.co/api/models/ibm-granite/granite-4.1-30b/revision/4fae6278f7132abf5e971f9de49ebbad09c54cce) |
| MiniCPM5-1B | [revision 87179e5c](https://huggingface.co/api/models/openbmb/MiniCPM5-1B/revision/87179e5c1f455ef22e6223592d2d61351b525bfc) |
| Hy-MT2-30B-A3B | [revision d3ead4db](https://huggingface.co/api/models/tencent/Hy-MT2-30B-A3B/revision/d3ead4dba61c09aac60a261a96ad1df3e705febb) |
| North-Mini-Code-1.0 | [revision d11e61a8](https://huggingface.co/api/models/CohereLabs/North-Mini-Code-1.0/revision/d11e61a842617a22dc328552fa5bb86231ee4f37) |
| DiffusionGemma 26B-A4B-IT | [revision f7f5b7f5](https://huggingface.co/api/models/google/diffusiongemma-26B-A4B-it/revision/f7f5b7f5fa82ffc52addd066915886d497f5517b) |
| LLaDA2.2-flash | [revision ee562645](https://huggingface.co/api/models/inclusionAI/LLaDA2.2-flash/revision/ee56264534721014d8e651293543f6dc3fcb1f9c) |
| LFM2.5-2.6B | [revision ab006873](https://huggingface.co/api/models/LiquidAI/LFM2.5-2.6B/revision/ab00687315bc1298e9d54e9c4b611dde9867ccc2) |
| Ling-3.0-tiny | [revision 2f9b5474](https://huggingface.co/api/models/inclusionAI/Ling-3.0-tiny/revision/2f9b5474a86ecfe63cfc95f5c87ddb3a745bfe2d) |
| Nemotron 3.5 Lightning | [revision d468880b](https://huggingface.co/api/models/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16/revision/d468880b6ad3c6e0d21377ce7242adaea4cc884d) |
| Qwen3.8-27B | [revision 1d4bf0f2](https://huggingface.co/api/models/Qwen/Qwen3.8-27B/revision/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0) |

## 프론티어 4개 모델 — 점수 provenance

| 모델 | 공통 표 채택값 | 근거와 핵심 설정 |
| :--- | :--- | :--- |
| Claude Opus 5 | SWE Verified **96.0**; SWE Pro **79.2**; DeepSWE 1.1 **68.8**; OSWorld 2.0 **70.57**; BrowseComp **90.8**; HLE **56.3/64.7**; ARC-AGI-2 **90.42**; GDPval-AA v2 **1861** | [고정 System Card PDF](https://www-cdn.anthropic.com/b514064af1408018e64b1ad24e7d5e75850b4ffd/Claude%20Opus%205%20System%20Card.pdf). 기본 adaptive thinking/max/default sampling, 평균 5회 unless noted. SWE 4종·DeepSWE·OSWorld는 5회. OSWorld=first-attempt success, 1080p, max 500 actions. HLE는 thinking=auto, 총 token≤1M, compaction 없음, Opus 4.6 grader; tools판=search/fetch/PTC/code. BrowseComp는 10M-token budget curve, 200K compaction trigger, Opus 4.7 grader와 unreleased effort config를 사용해 단순 max로 재표기하지 않음. |
| GPT-5.6 Sol | SWE Pro **64.6**; DeepSWE 1.1 **72.7**; Terminal-Bench 2.1 **88.8**; OSWorld 2.0 **62.6**; BrowseComp **90.4**; GPQA Diamond **94.6**; MMMU-Pro **83.0/84.6**; GDPval-AA v2 **1747.8** | [OpenAI 공식 발표 표](https://openai.com/index/gpt-5-6/). 표가 개별 effort/scaffold/trials와 OSWorld metric subtype을 공개하지 않아 모두 partial config. Ultra 점수는 4-agent 설정이므로 Sol 단일행에 섞지 않음. |
| Gemini 3.1 Pro Preview | SWE Verified **80.6**; SWE Pro Public **54.2**; Terminal-Bench 2.0 **68.5**; BrowseComp **85.9**; GPQA Diamond **94.3**; HLE **44.4/51.4**; MMMU-Pro **80.5**; ARC-AGI-2 **77.1** | [Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/) · [평가 방법론 PDF](https://storage.googleapis.com/deepmind-media/gemini/gemini_3-1_pro_model_evaluation.pdf). Thinking High, pass@1, single attempt, default sampling. SWE Verified 10회이며 공식 harness의 impossible-item 3개를 고친 +0.6 조정 포함. SWE Pro 5회. HLE=full set(text+MM), no-tools/Search(blocklist)+Code. Terminal=Terminus-2. GDPval-AA **1317**은 version 미표기라 v2 공통열이 아닌 supplemental claim으로 분리. |
| Grok 4.6 High | DeepSWE 1.1 **65.9**; Terminal-Bench 3.0 **26.0**; GDPval-AA v2 **1753** | [xAI 공식 발표](https://x.ai/news/grok-4-6). 표는 `Grok 4.6 High`를 명시하지만 tools/scaffold/trials는 미공개. 별도 공식 model card/tech report를 찾지 못했으므로 발표 밖의 설정을 추정하지 않음. |

### 프론티어 추가값의 근거

- Claude의 README 추가값은 모두 같은 [System Card PDF](https://www-cdn.anthropic.com/b514064af1408018e64b1ad24e7d5e75850b4ffd/Claude%20Opus%205%20System%20Card.pdf)의 capability evaluation 절에서 추출했습니다. Chartography·BenchCAD는 no-tools/tools를, Toolathlon은 Pass@1/Pass@3/Pass³를 분리했습니다. HealthBench Professional은 length-adjusted **59.8**과 raw **73.4**를 구분하며 OpenAI의 length-adjustment 방식과 자동 직접 비교하지 않습니다. Harvey open-source Legal Agent Benchmark 값은 production safeguards와 safety-classifier 발동 시 Opus 4.8 fallback을 포함할 수 있는 system 결과입니다.
- GPT-5.6 Sol의 추가값은 [OpenAI 발표의 모델 비교표](https://openai.com/index/gpt-5-6/)에서 Sol 열만 추출했습니다. `Agents' Last Exam`은 같은 페이지 본문 **53.6**, 표 **52.7**로 충돌하고 설정 차이가 공개되지 않았습니다. BrowseComp 본문 **92.2**는 비교표에서 Sol Ultra 값이고, Sol 열은 **90.4**입니다. README에는 구조화된 비교표의 Sol 열을 보존하며 HLE나 Ultra와 합치지 않습니다.
- Gemini 추가값은 [Model Card](https://deepmind.google/models/model-cards/gemini-3-1-pro/)의 `gemini-3.1-pro-preview` 열만 사용했습니다. τ² Airline은 grading 품질 문제로 카드가 제외하므로 Retail/Telecom만 기록했습니다.
- Grok 추가값은 [xAI 발표 표](https://x.ai/news/grok-4-6)의 `Grok 4.6 High` 열만 사용했습니다. 경쟁 모델 best-score 설명은 Grok 자체 harness 공개로 해석하지 않았습니다.

## 공개 가중치 15개 — 공통 표 provenance

| 모델 | 공통 표 채택값 | 근거 유형·평가 설정 |
| :--- | :--- | :--- |
| Gemma 4 31B-IT | τ² avg **76.9**; LCB v6 **80.0**; IFBench **76.0**; GPQA-D **84.3**; HLE **19.5/26.5**; MMLU-Pro **85.2** | [owner card](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [report](https://arxiv.org/html/2607.02770v2). IT 모델, 기본 thinking. HLE no-tools/search 분리. per-benchmark decoder/trials 일부 미공개. |
| EXAONE 4.5 33B | τ² weighted **72.0**; LCB v6 **81.4**; IFBench **62.6**; GPQA-D **80.5**; MMLU-Pro **83.3**; MMMU **78.7**; MathVista-mini **85.0** | [owner card](https://huggingface.co/LGAI-EXAONE/EXAONE-4.5-33B/blob/570aa4b15a4f45ba1133072b45f50198f6e3b4fd/README.md) · [report](https://arxiv.org/html/2604.08644v1). 정확한 표 열=`EXAONE 4.5 33B (Reasoning)`. language temp1/top-p.95/max128K, vision max32K, MTP off; trials/scaffold 일부 미공개. |
| Qwen3.6-35B-A3B | SWE-V **73.4**; LCB v6 **80.4**; GPQA-D **86.0**; HLE **21.4**; MMLU-Pro **85.2**; MMMU **81.7**; MathVista-mini **86.4** | [35B owner card](https://huggingface.co/Qwen/Qwen3.6-35B-A3B/blob/995ad96eacd98c81ed38be0c5b274b04031597b0/README.md); GPQA `Diamond` variant는 동일 공급사의 [27B 후속 비교표](https://huggingface.co/Qwen/Qwen3.6-27B/blob/6a9e13bd6fc8f0983b9b99948120bc37f49c13e9/README.md)가 같은 35B 값 86.0을 명시. SWE=internal bash+file-edit,temp1/top-p.95,200K. 나머지 mode/tools/trials 일부 미공개. |
| Qwen3.6-27B | SWE-V **77.2**; LCB v6 **83.9**; GPQA-D **87.8**; HLE **24.0**; MMLU-Pro **86.2**; MMMU **82.9**; MathVista-mini **87.4** | [owner card](https://huggingface.co/Qwen/Qwen3.6-27B/blob/6a9e13bd6fc8f0983b9b99948120bc37f49c13e9/README.md). SWE=internal bash+file-edit,temp1/top-p.95,200K. 비에이전트 표의 mode/tools/trials는 미공개. |
| Nemotron 3 Nano Omni | IFBench **74.2**; GPQA no-tools **72.2**; MMLU-Pro **77.3**; MMMU-val **70.8**; MathVista-mini **82.8** | [owner card](https://huggingface.co/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16/blob/24e67ea000b7c2837fc8f9488aa2008524fac8ba/README.md) · [report](https://arxiv.org/html/2604.24954v2). text=NeMo-Skills,temp1/top_p1,max output131072. GPQA 4회, IFBench 1회. MMMU/MathVista는 reasoning-on. 보고서의 `TauBench V2 (Telecom) 42.7`은 τ²/Sierra 식별이 없어 supplemental로 분리. |
| Granite 4.1 30B | MMLU **80.16**; MMLU-Pro **64.09**; GSM8K **94.16**; HumanEval **88.41** | [IBM owner card](https://huggingface.co/ibm-granite/granite-4.1-30b/blob/4fae6278f7132abf5e971f9de49ebbad09c54cce/README.md). MMLU 5-shot, MMLU-Pro 5-shot CoT, GSM8K 8-shot, HumanEval pass@1. 카드의 generic `GPQA 45.76`은 exact Diamond variant를 owner source가 밝히지 않아 supplemental로 이동. |
| MiniCPM5-1B | τ² Telecom-AA **79.53**; BFCL v4 **25.15**; LCB v6 Avg3 **33.52**; IFBench **46.67**; GPQA-D **26.26**; MMLU-Pro **48.85** | [owner card](https://huggingface.co/openbmb/MiniCPM5-1B/blob/87179e5c1f455ef22e6223592d2d61351b525bfc/README.md) · [official image](https://raw.githubusercontent.com/OpenBMB/MiniCPM/719e4fcfabff9b9c16f179c3f2986dfbd6c6047f/assets/minicpm5/public_leaderboard_en.png). 정확한 열=`MiniCPM5-1B (Thinking)`. τ²는 Telecom-AA 단일 domain. LCB만 Avg3, 나머지 일부 config 미공개. |
| Hy-MT2-30B-A3B | IFBench **50.67** | [owner card](https://huggingface.co/tencent/Hy-MT2-30B-A3B/blob/d3ead4dba61c09aac60a261a96ad1df3e705febb/README.md) · [report](https://arxiv.org/html/2605.22064v2). 해당 행은 `(T)` 표시가 없어 non-thinking. benchmark-specific decoding/trials 미공개. |
| North-Mini-Code-1.0 | SWE-V **67.6**; LCB v6 **70.3** | [owner card](https://huggingface.co/CohereLabs/North-Mini-Code-1.0/blob/d11e61a842617a22dc328552fa5bb86231ee4f37/README.md) · [official figure](https://cdn-uploads.huggingface.co/production/uploads/62668f725fb8d521d94d8451/xR7kZ3X9RKEZrbgD6hpG1.png). 3 seeds,temp1/top-p.95. SWE=SWE-Agent v1.1.0; LCB=no-tools code generation. |
| DiffusionGemma 26B-A4B-IT | τ² avg **56.2**; LCB v6 **69.1**; GPQA-D **73.2**; HLE **11.0/11.9**; MMLU-Pro **77.6** | [owner card](https://huggingface.co/google/diffusiongemma-26B-A4B-it/blob/f7f5b7f5fa82ffc52addd066915886d497f5517b/README.md). Entropy-Bound sampler,max48 denoise,temp .8→.4,entropy bound .1,adaptive stop. HLE no-tools/search 분리; shots/pass@k/trials 일부 미공개. |
| LLaDA2.2-flash | SWE-V **49.28**; BFCL v4 **60.78**; IFBench **30.20**; GPQA-D **48.67** | [owner card](https://huggingface.co/inclusionAI/LLaDA2.2-flash/blob/ee56264534721014d8e651293543f6dc3fcb1f9c/README.md) · [report PDF](https://raw.githubusercontent.com/inclusionAI/LLaDA2.X/f402f0b52817e1c3586a024ebf89e69ad8ca5523/LLaDA2_2_tech_report.pdf). 전 값 5회 평균; SWE=Claude Code. 128K,temp1,block32,threshold.5,editing threshold0. BFCL subtype/IF/GPQA 세부 일부 미공개. |
| LFM2.5-2.6B | BFCL v4 **56.88**; LCB v6 **59.41**; IFBench **59.17** | [owner card](https://huggingface.co/LiquidAI/LFM2.5-2.6B/blob/ab00687315bc1298e9d54e9c4b611dde9867ccc2/README.md). pure reasoning/always thinks. benchmark별 pass@k,trials,tools,harness와 BFCL subtype 미공개. |
| Ling-3.0-tiny | BFCL v4 FC **62.72**; IFBench **63.61**; GPQA-D **73.40**; HLE **9.30** | [owner card](https://huggingface.co/inclusionAI/Ling-3.0-tiny/blob/2f9b5474a86ecfe63cfc95f5c87ddb3a745bfe2d/README.md) · [official image](https://cdn-uploads.huggingface.co/production/uploads/6502cf8fbdaeae26417cd3c9/g9Thw4ohjkDGYw0Cq7mKi.png). 정확한 열=`Ling-3.0-tiny (Thinking)`; BFCL=FC. 나머지 tools/trials 일부 미공개. |
| Nemotron 3.5 Lightning | SWE-V **51.56**; IFBench loose **71.88**; GPQA-D **75.44**; HLE text/no-tools **11.72**; MMLU-Pro **81.94** | [owner card](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16/blob/d468880b6ad3c6e0d21377ce7242adaea4cc884d/README.md) · [repro index](https://github.com/NVIDIA-NeMo/Gym/blob/a62c30035519f738e583b6c1f08254cde70ced1b/nemotron_recipes/lightning-3.5/reproducibility.md). SWE OpenHands1.17,500×5,max200 turns; GPQA198×8 no-tools; HLE2158×1 no-tools/GPT-4o judge; temp1/top-p.95/thinking. IF/MMLU-Pro recipe 미공개. |
| Qwen3.8-27B | LCB v6 **90.3**; IFBench **79.5**; GPQA-D **89.2**; HLE **30.8** | [owner card](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md). HLE=GPT-4o judge. 공통 4개 지표의 mode/tools/trials 일부 미공개; 일반 xhigh 권장값을 평가 설정으로 소급하지 않음. |

## 추가 공식 결과 provenance

small_models_2026.md의 추가 결과는 다음 owner-source 표·그림에서 해당 모델 열을 전사했습니다. 경쟁 모델 열은 사용하지 않았습니다.

| 모델 | 추가 결과가 실린 고정 근거 | extraction/config 메모 |
| :--- | :--- | :--- |
| Gemma 4 31B-IT | [card](https://huggingface.co/google/gemma-4-31B-it/blob/842da3794eaa0b77d5f08bae87a17459d91ff475/README.md) · [report Table 5 및 부록](https://arxiv.org/html/2607.02770v2) | IT/Thinking 열. MMMLU, MMMU-Pro, MATH-Vision을 각각 MMLU/MMMU/MathVista로 바꾸지 않음. |
| EXAONE 4.5 33B | [card benchmark tables](https://huggingface.co/LGAI-EXAONE/EXAONE-4.5-33B/blob/570aa4b15a4f45ba1133072b45f50198f6e3b4fd/README.md) | `EXAONE 4.5 33B (Reasoning)` 열만 전사. |
| Qwen3.6 35B/27B | [35B card](https://huggingface.co/Qwen/Qwen3.6-35B-A3B/blob/995ad96eacd98c81ed38be0c5b274b04031597b0/README.md) · [27B card](https://huggingface.co/Qwen/Qwen3.6-27B/blob/6a9e13bd6fc8f0983b9b99948120bc37f49c13e9/README.md) | SWE-Pro=`refined` set; Terminal2.0=Harbor/Terminus-2,5회. τ³는 τ²와 분리. |
| Nemotron 3 Nano Omni | [card tables](https://huggingface.co/nvidia/Nemotron-3-Nano-Omni-30B-A3B-Reasoning-BF16/blob/24e67ea000b7c2837fc8f9488aa2008524fac8ba/README.md) · [report](https://arxiv.org/html/2604.24954v2) | reasoning off/on 열을 순서대로 유지. LCB는 v5; `TauBench V2 (Telecom)`은 τ² 식별 미공개; OSWorld는 generic label이므로 v6/τ²/OSWorld2로 바꾸지 않음. |
| Granite 4.1 30B | [owner card tables](https://huggingface.co/ibm-granite/granite-4.1-30b/blob/4fae6278f7132abf5e971f9de49ebbad09c54cce/README.md) | `GPQA 45.76`은 card label 그대로 보존. BFCL은 v3, IFEval Avg는 vendor aggregate. |
| MiniCPM5-1B | [official result image](https://raw.githubusercontent.com/OpenBMB/MiniCPM/719e4fcfabff9b9c16f179c3f2986dfbd6c6047f/assets/minicpm5/public_leaderboard_en.png) | `MiniCPM5-1B (Thinking)` 열. AIME/HMMT는 Avg16, LCBv6는 Avg3. |
| Hy-MT2 | [report Tables 2–5](https://arxiv.org/html/2605.22064v2) · [official image](https://huggingface.co/tencent/Hy-MT2-30B-A3B/resolve/d3ead4dba61c09aac60a261a96ad1df3e705febb/imgs/main_result.png) | non-thinking 30B-A3B 행; XCOMET/CometKiwi/GEMBA 순서를 유지. |
| North Mini Code | [official result image](https://cdn-uploads.huggingface.co/production/uploads/62668f725fb8d521d94d8451/xR7kZ3X9RKEZrbgD6hpG1.png) · [tech blog](https://huggingface.co/blog/CohereLabs/introducing-north-mini-code) | final release row, 3 seeds. SFT-only/pass@10와 human ablation은 제외. |
| DiffusionGemma | [owner card full table](https://huggingface.co/google/diffusiongemma-26B-A4B-it/blob/f7f5b7f5fa82ffc52addd066915886d497f5517b/README.md) | own IT column. lower-is-better OmniDoc edit distance 단위 유지. |
| LLaDA2.2-flash | [owner card](https://huggingface.co/inclusionAI/LLaDA2.2-flash/blob/ee56264534721014d8e651293543f6dc3fcb1f9c/README.md) · [report Tables 1–2](https://raw.githubusercontent.com/inclusionAI/LLaDA2.X/f402f0b52817e1c3586a024ebf89e69ad8ca5523/LLaDA2_2_tech_report.pdf) | vendor-labelled τ² 80.33은 인용 문헌 불일치 때문에 supplemental claim으로만 보존. LCB version 미공개. |
| LFM2.5 | [owner card full table](https://huggingface.co/LiquidAI/LFM2.5-2.6B/blob/ab00687315bc1298e9d54e9c4b611dde9867ccc2/README.md) | τ³ Banking을 τ²로 바꾸지 않음. |
| Ling 3 tiny | [official benchmark image](https://cdn-uploads.huggingface.co/production/uploads/6502cf8fbdaeae26417cd3c9/g9Thw4ohjkDGYw0Cq7mKi.png) | Thinking 열. GDPval 772의 단위가 표에 없어 `%`를 붙이지 않음. |
| Nemotron 3.5 Lightning | [owner card main table](https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16/blob/d468880b6ad3c6e0d21377ce7242adaea4cc884d/README.md) · [recipes](https://github.com/NVIDIA-NeMo/Gym/blob/a62c30035519f738e583b6c1f08254cde70ced1b/nemotron_recipes/lightning-3.5/reproducibility.md) | main table 수치. agent-harness별 별도 SWE/TB 이미지 점수는 bare-model 값으로 합치지 않아 본문에서 제외. |
| Qwen3.8-27B | [owner card text/VL tables](https://huggingface.co/Qwen/Qwen3.8-27B/blob/1d4bf0f2ff6012fd82039f2fa52739d0dd7c60c0/README.md) | first Qwen3.8 column only. OSWorld-Verified/WebArena-Verified는 OSWorld2/original WebArena와 다름. with-CI/without-CI를 분리. |

## 명시적 제외·충돌 로그

| 후보 주장 | 판정 | 이유 |
| :--- | :---: | :--- |
| GPT-5.6 Sol `Agents' Last Exam`을 HLE로 사용 | 제외 | 서로 다른 benchmark. 같은 OpenAI 페이지 내부 53.6/52.7 충돌도 별도 주석 처리. |
| GPT-5.6 Sol OSWorld 2.0을 `Partial`로 단정 | 제외 | 공식 발표 표가 62.6은 주지만 Binary/Partial subtype을 밝히지 않음. |
| Gemini SWE Verified 80.6을 표준 운영자 row로 간주 | 제외 | Google corrected internal harness 및 +0.6 조정, 10회 결과이므로 해당 설정을 함께 기록. |
| Grok 4.6의 발표 밖 scaffold/trials 추정 | 제외 | 공식 model card/tech report가 발견되지 않았고 발표 표도 설정을 공개하지 않음. |
| Nemotron Omni LCB v5 63.2를 v6 열에 사용 | 제외 | exact version 불일치. |
| Nemotron Omni `TauBench V2 (Telecom) 42.7`을 τ² 열에 사용 | 제외 | owner report가 `τ²` 또는 Sierra benchmark라고 식별하지 않아 exact variant를 확정할 수 없음. |
| Granite GPQA 45.76을 GPQA Diamond 열에 사용 | 제외 | IBM owner card의 행명은 generic `GPQA`. [HF 직원이 추가한 VERIFIED metadata](https://huggingface.co/ibm-granite/granite-4.1-30b/blob/bd3a9ae805aa66e7af9df2896667dd0957a81916/.eval_results/gpqa_diamond.yaml)는 owner/operator 1차 근거가 아니므로 variant 확정에 사용하지 않음. |
| Granite BFCL v3 73.68을 V4 열에 사용 | 제외 | version 불일치. |
| MiniCPM/Nemotron Omni τ² Telecom을 전체 평균으로 표기 | 제외 | 단일 domain 값. 공통 셀에도 domain label 유지. |
| LLaDA `τ²-Bench 80.33`을 canonical τ²로 채택 | 제외 | 보고서 참고문헌이 Sierra τ²가 아니라 2024 original τ-bench를 가리킴. 원문 주장으로만 보존. |
| Qwen3.8 OSWorld-Verified/WebArena-Verified를 OSWorld2/WebArena로 변경 | 제외 | benchmark variant 불일치. |
| Gemma MMMLU/MMMU-Pro/MATH-Vision을 MMLU/MMMU/MathVista로 변경 | 제외 | 서로 다른 benchmark. |
| 모델 카드 일반 권장 temperature/top-p를 모든 eval에 적용 | 제외 | 해당 benchmark 실제 설정이라는 명시가 없음. |

## Benchmark 정의·운영자 URL

아래 링크는 benchmark 정의 또는 운영자 결과를 설명하며, 그 자체가 이 문서의 모델 점수를 증명하지는 않습니다.

| benchmark | 공식 정의/운영자 URL | 필수 한정자 |
| :--- | :--- | :--- |
| SWE-bench Verified | [공식 사이트](https://www.swebench.com/) · [experiments](https://github.com/swe-bench/experiments) | variant, agent/scaffold, trials |
| SWE-bench Pro | [Scale 공개 저장소](https://github.com/scaleapi/SWE-bench_Pro-os) | public/refined set, scaffold, trials |
| OSWorld 2.0 | [프로젝트](https://osworld-v2.xlang.ai/) · [공식 결과 JSON](https://osworld-v2.xlang.ai/static/data/leaderboard/official-results.json) | task version, Binary/Partial/success |
| τ² / τ³ | [τ² core](https://taubench.com/leaderboard?benchmark=core) · [τ³ knowledge](https://taubench.com/leaderboard?benchmark=knowledge) · [repo](https://github.com/sierra-research/tau2-bench) | generation, domain, Pass^k, user simulator |
| BFCL | [공식 리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html) · [결과 CSV](https://gorilla.cs.berkeley.edu/data_overall.csv) | version, FC/Prompt, Overall/category |
| LiveCodeBench | [공식 리더보드](https://livecodebench.github.io/leaderboard.html) · [결과 JSON](https://livecodebench.github.io/performances_generation.json) | version/date window, scenario, pass@k |
| IFBench | [AllenAI 공식 저장소](https://github.com/allenai/IFBench) | loose/strict, prompt level, generation |
| IFEval | [Google Research 코드·데이터](https://github.com/google-research/google-research/tree/master/instruction_following_eval) | strict/loose, instruction/prompt, aggregate |
| Multi-IF | [Meta 공식 저장소](https://github.com/facebookresearch/Multi-IF) | language, turns, metric |
| Terminal-Bench | [공식 사이트](https://www.tbench.ai/) · [v2 repo](https://github.com/harbor-framework/terminal-bench-2) · [v2.1 repo](https://github.com/harbor-framework/terminal-bench-2-1) | exact version, agent, timeout, trials |
| GPQA Diamond | [공식 저장소](https://github.com/idavidrein/gpqa) | Diamond subset, shots, sampling |
| HLE | [공식 프로젝트](https://lastexam.ai/) | Full/Text, tools, judge |
| MMLU / MMLU-Pro | [MMLU](https://github.com/hendrycks/test) · [MMLU-Pro](https://huggingface.co/datasets/TIGER-Lab/MMLU-Pro) | shots, CoT, accuracy/EM |
| GSM8K | [OpenAI 공식 저장소](https://github.com/openai/grade-school-math) | shots, CoT, extraction |
| HumanEval | [OpenAI 공식 저장소](https://github.com/openai/human-eval) | pass@k, samples, temperature |
| MMMU / MathVista | [MMMU](https://mmmu-benchmark.github.io/) · [MathVista](https://mathvista.github.io/) | val/test, Pro 여부, mini/testmini |
| ARC-AGI | [ARC Prize](https://arcprize.org/) | version, verified status, effort |

## 읽는 법

- 이 저장소는 “가장 높은 점수” 순위표가 아니라 **공식 주장과 설정의 출처 지도**입니다.
- operator score와 vendor score, bare model과 agent system, no-tools와 tools는 직접 같은 조건으로 간주하지 않습니다.
- 동적 페이지가 바뀌더라도 재검증할 수 있도록 가능한 경우 HF SHA, Git commit, 고정 PDF를 우선 기록했습니다.
