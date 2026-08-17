# 성능 수치 출처 (Performance Result Provenance)

검증 기준일: **2026-08-17 (KST)**

이 문서는 `README.md`와 `small_models_2026.md`에 실제 숫자로 기재된 성능값만 추적합니다. 모델 홈페이지나 벤치마크 소개 페이지를 여러 셀의 포괄 출처로 사용하지 않습니다.

## 채택 기준

- 공식 벤치마크 운영자 리더보드 또는 모델 제공사의 공식 발표문·시스템 카드에서 **모델명, 벤치마크 버전/지표, 수치**가 함께 확인되어야 합니다.
- `-`는 0점이나 모델의 기능 부재를 뜻하지 않습니다. 동일 조건의 공개 수치를 직접 확인하지 못했다는 뜻입니다.
- 개발사 자체 평가와 운영자 리더보드 평가는 하네스, 추론 설정, 시행 횟수가 다를 수 있으므로 서로 같은 조건의 점수로 간주하지 않습니다.
- 동적 리더보드는 검증 기준일의 공개 상태를 기준으로 판정합니다.

## 검증되어 채택한 수치

| ID | 모델 | 벤치마크 / 지표 | 채택값 | 결과 근거 | 벤치마크 정의 | 근거 유형 / 평가 조건 |
| :--- | :--- | :--- | :---: | :--- | :--- | :--- |
| `claude-opus-5-swebench-verified` | Claude Opus 5 | SWE-bench Verified, 500문항 | **96.0%** | [Anthropic Claude Opus 5 System Card, §8.2, 인쇄본 p.149](https://www.anthropic.com/claude-opus-5-system-card#page=149) | [SWE-bench 공식 사이트](https://www.swebench.com/) | 개발사 보고. 5회 시행 평균. 별도 표기가 없으면 adaptive thinking, max effort, 기본 sampling 설정. |
| `gpt-5-6-sol-osworld-2-partial` | GPT-5.6 Sol | OSWorld 2.0, **Partial reward** | **62.6%** | [OpenAI GPT-5.6 공식 발표의 Computer use 표](https://openai.com/index/gpt-5-6/) | [OSWorld 2.0 공식 프로젝트](https://osworld-v2.xlang.ai/) · [공식 `v2026.06.24` 릴리스](https://github.com/xlang-ai/OSWorld-V2/releases/tag/v2026.06.24) | 개발사 보고. OpenAI 표는 전체 하네스 설정을 공개하지 않습니다. 비교 대상 Opus 4.8의 54.8%가 운영자 페이지의 Partial reward와 일치하므로 지표를 Partial로 식별했습니다. |

## 제거한 미검증 수치

| 기존 주장 | 처리 | 1차 출처 확인 결과 |
| :--- | :---: | :--- |
| Claude Opus 5 · SWE-bench Verified **52.3%** | **96.0%로 교정** | [Anthropic System Card](https://www.anthropic.com/claude-opus-5-system-card#page=149)가 500문항·5회 평균 **96.0%**를 명시합니다. 52.3%는 공식 자료에서 확인되지 않았습니다. |
| Claude Opus 5 · WebArena **61.8%** | **`-`로 제거** | [WebArena 공식 프로젝트](https://webarena.dev/og/)가 연결한 [공식 리더보드](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ/edit?usp=sharing)와 [Anthropic 발표](https://www.anthropic.com/news/claude-opus-5)에 해당 모델·수치가 없습니다. |
| GPT-5.6 Sol · GAIA **46.8%** | **`-`로 제거** | [GAIA 공식 리더보드](https://gaia-benchmark-leaderboard.hf.space/)와 [OpenAI 발표](https://openai.com/index/gpt-5-6/)에 해당 결과가 없습니다. |
| GPT-5.6 Sol · OSWorld **36.5%** | **62.6%로 교정** | [OpenAI 공식 발표](https://openai.com/index/gpt-5-6/)는 OSWorld 2.0에서 **62.6%**를 보고합니다. [운영자 페이지](https://osworld-v2.xlang.ai/)와 대조해 Partial reward로 표기했습니다. |
| GPT-5.6 Sol · Tau²-Bench **71.2%** | **`-`로 제거** | 71.2%는 OpenAI 발표에서 **SEC-Bench Pro** 점수입니다. [Sierra의 GPT-5.6 Sol 공식 제출 JSON](https://github.com/sierra-research/tau2-bench/blob/main/web/leaderboard/public/submissions/gpt-5-6-sol_sierra_2026-08-04/submission.json)은 airline·retail·telecom이 `null`이며, 별도 벤치마크인 Tau³ Banking 결과만 제공합니다. |
| GPT-5.6 Sol · BFCL **93.8%** | **`-`로 제거** | [BFCL V4 공식 리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html)는 2026-04-12 업데이트 상태로 GPT-5.6 행이 없습니다. 버전·Overall Accuracy/세부 범주·FC/Prompt 설정이 없는 단일 BFCL 수치도 채택하지 않습니다. |
| GPT-5.6 Sol · LiveCodeBench **79.5%** | **`-`로 제거** | 79.5%는 OpenAI 발표에서 **GPT-5.6 Luna의 MMMU Pro (with tools)** 값입니다. [LiveCodeBench 공식 리더보드](https://livecodebench.github.io/leaderboard.html)에 GPT-5.6 결과가 없습니다. |
| GPT-5.6 Sol · HumanEval **96.1%** | **`-`로 제거** | [OpenAI GPT-5.6 발표](https://openai.com/index/gpt-5-6/)에 HumanEval 결과가 없고, [HumanEval 공식 저장소](https://github.com/openai/human-eval)는 최신 모델 중앙 리더보드를 제공하지 않습니다. pass@k와 sampling 조건이 없는 수치는 채택하지 않습니다. |

## 벤치마크 정의 URL

아래 URL은 벤치마크와 평가 조건을 정의하거나 공식 결과를 게시하는 곳입니다. 링크 자체가 특정 모델 점수의 근거가 되는 것은 아닙니다.

| 벤치마크 | 공식 URL | 수치 기록 시 필수 한정자 |
| :--- | :--- | :--- |
| SWE-bench Verified | [swebench.com](https://www.swebench.com/) | variant, agent/scaffold, 추론 설정, 시행 횟수 |
| GAIA | [공식 리더보드](https://gaia-benchmark-leaderboard.hf.space/) | test/dev, 전체/level별 점수, agent·tool 구성 |
| OSWorld 2.0 | [프로젝트·리더보드](https://osworld-v2.xlang.ai/) · [`v2026.06.24`](https://github.com/xlang-ai/OSWorld-V2/releases/tag/v2026.06.24) | task version, step budget, Binary/Partial |
| WebArena | [공식 프로젝트](https://webarena.dev/og/) · [공식 리더보드](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ/edit?usp=sharing) | WebArena/VisualWebArena, harness, trajectory 공개 여부 |
| Tau² / Tau³ | [공식 리더보드](https://taubench.com/) · [공식 저장소](https://github.com/sierra-research/tau2-bench) | 세대, domain, Pass^k, user simulator, task version |
| BFCL V4 | [공식 리더보드](https://gorilla.cs.berkeley.edu/leaderboard.html) | commit/package version, Overall/세부 범주, FC/Prompt |
| LiveCodeBench | [공식 리더보드](https://livecodebench.github.io/leaderboard.html) · [공식 저장소](https://github.com/LiveCodeBench/LiveCodeBench) | release/date window, scenario, pass@k |
| HumanEval | [OpenAI 공식 저장소](https://github.com/openai/human-eval) | pass@k, sample 수, temperature |

## 비교 주의사항

- Claude Opus 5의 96.0%는 Anthropic 자체 하네스의 5회 평균입니다. SWE-bench 공식 사이트 기본 화면의 `mini-SWE-agent` 단일 환경 결과와 직접 비교하면 안 됩니다.
- GPT-5.6 Sol의 62.6%는 OSWorld 2.0의 Partial reward입니다. 주 지표인 Binary completion과 혼용하면 안 됩니다.
- Tau²와 Tau³ Banking은 서로 다른 평가입니다. Tau³ Banking 46.907%를 Tau² 종합 점수로 옮겨 적지 않습니다.
- 향후 수치를 추가할 때는 모델 홈페이지가 아니라, 해당 수치가 실제로 표시된 고정 URL과 평가 설정을 함께 기록해야 합니다.
