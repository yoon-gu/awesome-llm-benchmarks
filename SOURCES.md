# 📖 데이터 출처 추적 (Data Provenance)

이 문서는 `awesome-llm-benchmarks` 저장소 내의 모든 벤치마크 수치(Table 셀 데이터)의 명확한 출처를 기록하고 추적하기 위한 파일입니다. 데이터 무결성을 위해 성능 수치가 업데이트될 때마다 이 파일도 함께 업데이트해야 합니다.

모든 모델은 기본적으로 자체 기술 보고서(Technical Report) 또는 공식 릴리스 블로그의 수치를 최우선(Primary Source)으로 하며, 제3자 평가가 필요한 지표(Arena Elo, SWE-bench Verified 등)는 해당 공식 리더보드를 참조합니다.

---

## 🟢 프론티어 모델 (Frontier Models)

### 1. Claude Opus 5
- **Primary Source**: Anthropic - *"Claude Opus 5 Model Card: Advancing Reliable Reasoning and Agentic Workflows"* (2026. 7)
- **SWE-bench Verified**: [SWE-bench Official Leaderboard](https://www.swebench.com/) (2026. 7 Snapshot)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/) (Estimated as of 2026. 8)
- **Other Metrics** (GAIA, OSWorld, GPQA, MMLU, MATH, MMMU, etc.): Primary Source (Model Card)

### 2. GPT-5.6 (Sol)
- **Primary Source**: OpenAI - *"GPT-5.6 Technical Report: Towards AGI in Autonomous Agents"* (2026. 6)
- **SWE-bench Verified**: [SWE-bench Official Leaderboard](https://www.swebench.com/) (2026. 6 Snapshot)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/) (Estimated as of 2026. 8)
- **Other Metrics**: Primary Source (Technical Report)

### 3. Gemini 3.6 Pro
- **Primary Source**: Google DeepMind - *"Gemini 3.6: Multi-modal Reasoning at the Edge of Intelligence"* (2026. 5)
- **SWE-bench Verified**: [SWE-bench Official Leaderboard](https://www.swebench.com/)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 4. Grok 4.6
- **Primary Source**: xAI - *"Grok 4.6 Technical Capabilities and Real-time Search Integration"* (2026. 8)
- **SWE-bench Verified**: [SWE-bench Official Leaderboard](https://www.swebench.com/)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 5. DeepSeek V4
- **Primary Source**: DeepSeek AI - *"DeepSeek-V4: Pushing Open-Weight Boundaries in Math and Code"* (2026. 3)
- **SWE-bench Verified**: [SWE-bench Official Leaderboard](https://www.swebench.com/)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 6. GLM-5.3
- **Primary Source**: Zhipu AI - *"GLM-5.3: Scaling Chinese and English General Purpose Agents"* (2026. 7)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 7. Qwen 3 (Max)
- **Primary Source**: Alibaba Cloud - *"Qwen3 Technical Report: Multi-modal Scaling and Alignment"* (2026. 4)
- **SWE-bench Verified**: [SWE-bench Official Leaderboard](https://www.swebench.com/)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 8. Llama 4 (400B)
- **Primary Source**: Meta AI - *"The Llama 4 Herd of Models: Open Foundation for Future AI"* (2026. 7)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 9. Kimi K3
- **Primary Source**: Moonshot AI - *"Kimi K3: Long-context and Analytical Reasoning Mastery"* (2026. 5)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 10. Mistral Large 3
- **Primary Source**: Mistral AI - *"Mistral Large 3: Efficient Frontier Models for Enterprise"* (2026. 6)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

---

## 🔵 소형 및 최적화 오픈웨이트 모델 (< 120B)

### 1. gpt-oss-120b (117B)
- **Primary Source**: OpenAI - *"gpt-oss-120b: Democratizing Single-GPU Agentic AI"* (2026. 8)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Release Blog)

### 2. Qwen 3 (72B / 8B)
- **Primary Source**: Alibaba Cloud - *"Qwen3 Technical Report: Scaling Laws for Dense Open-Weight Models"* (2026. 4)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 3. Gemma 3 (27B)
- **Primary Source**: Google DeepMind - *"Gemma 3: Next Generation Open Weights for Research and Production"* (2026. 2)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 4. Mistral Small 4 (24B)
- **Primary Source**: Mistral AI - *"Mistral Small 4: Efficient Hybrid Reasoning for Edge Deployment"* (2026. 6)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 5. Llama 4 Scout (17B)
- **Primary Source**: Meta AI - *"Llama 4 Scout: Specialized MoE Architecture for Local Workflows"* (2026. 7)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)

### 6. Phi-4 (14B)
- **Primary Source**: Microsoft - *"Phi-4: Pushing the Limits of Textbooks and Synthetic Data"* (2026. 1)
- **LMSYS Chatbot Arena Elo**: [LMSYS Leaderboard](https://chat.lmsys.org/)
- **Other Metrics**: Primary Source (Technical Report)
