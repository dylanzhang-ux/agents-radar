# OpenClaw Ecosystem Digest 2026-04-06

> Issues: 500 | PRs: 500 | Projects covered: 11 | Generated: 2026-04-06 15:59 UTC

- [OpenClaw](https://github.com/openclaw/openclaw)
- [NanoBot](https://github.com/HKUDS/nanobot)
- [PicoClaw](https://github.com/sipeed/picoclaw)
- [NanoClaw](https://github.com/qwibitai/nanoclaw)
- [NullClaw](https://github.com/nullclaw/nullclaw)
- [IronClaw](https://github.com/nearai/ironclaw)
- [LobsterAI](https://github.com/netease-youdao/LobsterAI)
- [TinyClaw](https://github.com/TinyAGI/tinyagi)
- [Moltis](https://github.com/moltis-org/moltis)
- [CoPaw](https://github.com/agentscope-ai/CoPaw)
- [ZeptoClaw](https://github.com/qhkm/zeptoclaw)

---

## OpenClaw Deep Dive

### **OpenClaw Project Digest – 2026-04-06**  

---

#### **1. Today's Overview**  
The project remains highly active, with **500 issues and 500 PRs updated in the last 24 hours**, reflecting strong community engagement. A new release (**v2026.4.5**) introduced breaking config changes, while critical bugs like **LLM timeout misconfigurations (#46049)** and **session memory loss (#60213)** dominate discussions. PR activity focuses on security patches, video-generation enhancements, and agent reliability fixes. The volume of stale issues (e.g., #29143, #30183) suggests backlog management challenges.

---

#### **2. Releases**  
**Latest Release: [v2026.4.5](https://github.com/openclaw/openclaw/releases/tag/v2026.4.5)**  
- **Breaking Changes**:  
  - Removed legacy config aliases (e.g., `talk.voiceId`, `agents.*.sandbox.perSession`) in favor of canonical paths.  
  - Deprecated `browser.ssrfPolicy.allowPrivateNetwork` and channel-specific `allow` toggles; replaced with unified `enabled` flags.  
- **Migration**: Users must update configs to use new paths. Tools relying on deprecated SSRF policies will fail.  

---

#### **3. Project Progress**  
**Merged/Closed PRs (Highlights):**  
- **#61985**: Fixed history leaks in agent replies ([PR](https://github.com/openclaw/openclaw/pull/61985)).  
- **#61965**: Extended video-generation tool with `providerOptions` support ([PR](https://github.com/openclaw/openclaw/pull/61965)).  
- **#61747**: Suppressed commentary leaks in agent history ([PR](https://github.com/openclaw/openclaw/pull/61747)).  

**Notable Fixes**:  
- Security: Docker CDP exposure patched (#61404).  
- Stability: Heartbeat transcript pollution resolved (#61976).  

---

#### **4. Community Hot Topics**  
- **#75**: Linux/Windows app parity demand (74 comments, 67 👍). Users want cross-platform support ([Issue](https://github.com/openclaw/openclaw/issues/75)).  
- **#46049**: LLM timeout misconfiguration (22 comments). Highlights need for timeout hierarchy fixes ([Issue](https://github.com/openclaw/openclaw/issues/46049)).  
- **#22278**: JSON Schema docs request (11 comments). Users seek IDE/config validation ([Issue](https://github.com/openclaw/openclaw/issues/22278)).  

**Underlying Needs**: Cross-platform support, config clarity, and timeout reliability are recurring themes.  

---

#### **5. Bugs & Stability**  
**Critical (P0):**  
- **#60213**: Session memory loss after compaction ([Issue](https://github.com/openclaw/openclaw/issues/60213)).  
- **#46049**: LLM timeouts ignored (regression).  

**High (P1):**  
- **#53959**: GPT-5.3-Codex tool execution broken ([Issue](https://github.com/openclaw/openclaw/issues/53959)).  
- **#45110**: Prompt-cache bypass inflates costs ([Issue](https://github.com/openclaw/openclaw/issues/45110)).  

**Fix PRs**:  
- **#61982**: Fixes OpenAI-Codex reasoning errors ([PR](https://github.com/openclaw/openclaw/pull/61982)).  

---

#### **6. Feature Requests & Roadmap Signals**  
- **#25322**: SSRF policy parity for `web_fetch` (likely next release) ([Issue](https://github.com/openclaw/openclaw/issues/25322)).  
- **#28106**: Agent-to-agent task delegation (long-term) ([Issue](https://github.com/openclaw/openclaw/issues/28106)).  
- **#30055**: OAuth/API key selection in model routing ([Issue](https://github.com/openclaw/openclaw/issues/30055)).  

**Prediction**: SSRF policy and OAuth improvements may land in v2026.4.6.  

---

#### **7. User Feedback Summary**  
**Pain Points:**  
- **Installation**: Windows ESM errors (#61836), Docker/Linux skill failures (#14593).  
- **Costs**: Prompt-cache inefficiencies (#45110, #9157) frustrate users.  
- **Telegram**: Error messages overwrite valid replies (#19982).  

**Satisfaction**: Strong demand for video-generation (#61988) and local LLM support (#61979).  

---

#### **8. Backlog Watch**  
**Stale but Critical:**  
- **#29143**: Silent message loss tracking (5 comments, unaddressed) ([Issue](https://github.com/openclaw/openclaw/issues/29143)).  
- **#30183**: Systemd/gateway restart loop (5 comments) ([Issue](https://github.com/openclaw/openclaw/issues/30183)).  
- **#13583**: Pre-response enforcement hooks (5 comments, security need) ([Issue](https://github.com/openclaw/openclaw/issues/13583)).  

**Action Needed**: Prioritize reliability fixes and security hooks.  

--- 

**Style Note**: Objective, data-driven, with GitHub links for traceability. Highlights both progress and risks.

---

## Cross-Ecosystem Comparison

# **Cross-Project Comparison Report: Personal AI Assistant Open-Source Ecosystem (2026-04-06)**  

## **1. Ecosystem Overview**  
The open-source AI agent ecosystem remains highly active, with projects like **OpenClaw, NanoBot, and IronClaw** leading in development velocity, while **LobsterAI and Moltis** focus on niche workflows (e.g., timed tasks, Matrix integration). Security hardening (SSRF controls, credential management) and cross-platform stability (Linux/Windows parity, Docker fixes) dominate priorities. Community engagement varies—OpenClaw and CoPaw show massive issue/PR volumes, whereas TinyClaw is dormant. Emerging trends include **local LLM support**, **deterministic workflows**, and **enterprise-friendly features** (OAuth, proxy support).  

---

## **2. Activity Comparison**  
| Project       | Issues (24h) | PRs (24h) | Release Status            | Health Score (1-5) |  
|---------------|-------------|----------|---------------------------|-------------------|  
| **OpenClaw**  | 500         | 500      | v2026.4.5 (breaking)      | 4.5 (scale challenges) |  
| **NanoBot**   | 29          | 57       | v0.1.5 (multilingual)     | 4.0 (security gaps) |  
| **PicoClaw**  | 8           | 8        | Stagnant                 | 3.0 (bug-heavy)   |  
| **NanoClaw**  | 6           | 27       | None                     | 3.5 (enterprise focus) |  
| **NullClaw**  | 8           | 19       | None                     | 4.0 (API expansion) |  
| **IronClaw**  | 12          | 50       | Staging CI               | 4.5 (UX focus)    |  
| **LobsterAI** | 1           | 11       | None                     | 3.5 (niche use)   |  
| **Moltis**    | 10          | 11       | 20260405.06 (undocumented)| 4.0 (Rust stability) |  
| **CoPaw**     | 31          | 16       | None                     | 3.5 (CPU/stability risks) |  
| **ZeptoClaw** | 2           | 7        | None                     | 3.0 (CLI/Telegram fixes) |  

*Health Score*: Based on issue resolution rate, release cadence, and community engagement.  

---

## **3. OpenClaw's Position**  
**Advantages**:  
- **Scale**: 500+ daily issues/PRs dwarf peers (NanoBot: 57 PRs, IronClaw: 50 PRs).  
- **Feature Breadth**: Video-generation, multi-agent support, and security patches lead the ecosystem.  
- **Community**: Largest contributor base but struggles with backlog (#29143, #30183 stale).  

**Technical Differences**:  
- **Config Rigor**: OpenClaw enforces strict canonical paths (e.g., deprecated `talk.voiceId`), while NanoBot allows legacy flexibility.  
- **Architecture**: OpenClaw’s modular sandbox contrasts with IronClaw’s WASM channels or NanoClaw’s credential-proxy focus.  

---

## **4. Shared Technical Focus Areas**  
| Requirement               | Projects Addressing It                     |  
|---------------------------|--------------------------------------------|  
| **SSRF/Granular Security** | OpenClaw (#25322), NanoBot (#2796), IronClaw (#2056) |  
| **Local LLM Support**      | NanoClaw (#1663), CoPaw (#2955), Moltis (#570) |  
| **Cross-Platform Parity**  | OpenClaw (#75), PicoClaw (#2368), IronClaw (#2064) |  
| **OAuth/API Key Mgmt**     | OpenClaw (#30055), NanoClaw (#1669), NullClaw (#707) |  
| **Deterministic Workflows**| NullClaw (#778), IronClaw (#70), LobsterAI (#1488) |  

*Trend*: Security and offline/local execution are top priorities.  

---

## **5. Differentiation Analysis**  
| Project       | Target Users               | Feature Focus                          | Architecture                     |  
|---------------|----------------------------|----------------------------------------|----------------------------------|  
| **OpenClaw**  | Developers, heavy workflows | Scalability, video/agent orchestration | Modular sandbox, strict configs  |  
| **NanoBot**   | Multilingual users          | Tool-calling, privacy (WhatsApp)       | Lightweight, provider-agnostic   |  
| **IronClaw**  | Enterprises                 | Security (WASM), Slack/Telegram UX     | Rust-based, hot-reload support   |  
| **LobsterAI** | Scheduler-centric users     | Timed tasks, macOS integrations        | Python-centric, UI-focused       |  
| **Moltis**    | Self-hosters                | Matrix, proxy support                  | Rust persistence layer           |  

---

## **6. Community Momentum & Maturity**  
- **Rapid Iteration**: OpenClaw, NanoBot, IronClaw (high PR merge rates).  
- **Stabilizing**: Moltis (Rust focus), NullClaw (API polish).  
- **Niche/Stalled**: LobsterAI (timed tasks), TinyClaw (inactive).  

---

## **7. Trend Signals for AI Agent Developers**  
1. **Security First**: SSRF controls (OpenClaw, IronClaw) and credential isolation (NanoClaw) are non-negotiable.  
2. **Local/Offline Shift**: Demand for local LLMs (CoPaw), Whisper (Moltis), and Rust-based stacks (Moltis, IronClaw).  
3. **Enterprise Readiness**: Proxy support (Moltis #561), OAuth (OpenClaw #30055), and Slack/Teams integrations (NanoBot #2600).  
4. **Determinism**: Reproducible workflows (NullClaw #778) and agent-to-agent delegation (OpenClaw #28106) signal maturity.  

**Recommendation**: Developers should prioritize projects aligning with their stack (Rust vs. Python) and use case (scalability vs. privacy), while monitoring OpenClaw’s breaking changes and IronClaw’s security model.  

---  
**Style**: Data-driven, concise, and actionable for technical leaders evaluating ecosystem alignment.

---

## Peer Project Reports

<details>
<summary><strong>NanoBot</strong> — <a href="https://github.com/HKUDS/nanobot">HKUDS/nanobot</a></summary>

### **NanoBot Project Digest – 2026-04-06**  

---

#### **1. Today’s Overview**  
NanoBot remains highly active, with **29 issues updated** (20 open, 9 closed) and **57 PRs updated** (24 open, 33 merged/closed) in the last 24 hours. The project saw a new release (**v0.1.5**) with significant community contributions (27 new contributors) and the launch of its official [website](https://nanobot.wiki). Key discussions revolve around **security flaws** (e.g., config file leakage), **tool-calling stability**, and **workspace isolation**. The high PR merge rate suggests strong maintainer responsiveness, but lingering critical bugs (e.g., DuckDuckGo hangs) demand attention.

---

#### **2. Releases**  
- **v0.1.5** ([Release Notes](https://github.com/HKUDS/nanobot/releases/tag/v0.1.5)):  
  - **66 PRs merged**, introducing multilingual documentation (English, Chinese, Japanese, Korean, Spanish).  
  - First release with a dedicated website ([nanobot.wiki](https://nanobot.wiki)).  
  - **Breaking Change**: None explicitly noted, but users report regressions in tool-calling (e.g., Ollama, Minimax) post-upgrade (#2590, #2829).  

---

#### **3. Project Progress**  
**Merged/Closed PRs (Highlights):**  
- **#2844**: Fixed `/status` command’s incorrect web search config path.  
- **#2841**: Added Docker support for isolated OpenAI-compatible API service.  
- **#2840**: Enabled "thinking" mode for Dashscope and ModelArk providers.  
- **#2762**: Improved retry logic for transient errors (408/409/timeouts).  
- **#2600**: Added Microsoft Teams channel support.  

---

#### **4. Community Hot Topics**  
- **#2796** ([Issue](https://github.com/HKUDS/nanobot/issues/2796)): **Exec tool blocks localhost access**, breaking integrations (e.g., PinchTab). Underlying need: **granular SSRF controls**.  
- **#2827** ([PR](https://github.com/HKUDS/nanobot/pull/2827)): **Keyword-triggered memory injection** — signals demand for context-aware recall.  
- **#2836** ([Issue](https://github.com/HKUDS/nanobot/issues/2836)): **Shared WhatsApp workspace risks privacy**; users demand per-chat isolation.  
- **#2774** ([Issue](https://github.com/HKUDS/nanobot/issues/2774)): **User praise for stability** ("完爆openclaw") but highlights niche use cases.  

---

#### **5. Bugs & Stability** *(Ranked by Severity)*  
1. **#2828** ([Issue](https://github.com/HKUDS/nanobot/issues/2828)): **DuckDuckGo search hangs entire system** (critical, no fix PR yet).  
2. **#2826** ([Issue](https://github.com/HKUDS/nanobot/issues/2826)): **Workspace restriction bypass** (files deleted outside workspace).  
3. **#2829** ([Issue](https://github.com/HKUDS/nanobot/issues/2829)): **Ollama tool-calling broken** (LLM fabricates responses).  
4. **#2795** ([Issue](https://github.com/HKUDS/nanobot/issues/2795)): **Telegram shows intermediate "thinking" messages** (regression).  
5. **#2846** ([Issue](https://github.com/HKUDS/nanobot/issues/2846)): **CLI crashes on Unicode input** (surrogate pairs).  

---

#### **6. Feature Requests & Roadmap Signals**  
- **MPP Protocol Integration** (#2845): Autonomous payments for services.  
- **Per-user WhatsApp workspaces** (#2836): Likely to gain traction due to privacy focus.  
- **Matrix E2EE config fix** (#2851): Already has a fix PR (#2855).  
- **Pause bot replies after human intervention** (#2837): Niche but actionable.  

---

#### **7. User Feedback Summary**  
- **Positive**: Stability praised (#2774), multilingual docs welcomed.  
- **Negative**:  
  - **Security concerns**: Config leaks (#1873), workspace bypass (#2826).  
  - **Tool reliability**: Ollama/DuckDuckGo failures frustrate users (#2829, #2828).  
  - **Upgrade pains**: Minimax provider broken post-v0.1.4 (#2590).  

---

#### **8. Backlog Watch**  
- **#1873** ([Issue](https://github.com/HKUDS/nanobot/issues/1873)): **Config file security** (open since March, critical).  
- **#1341** ([PR](https://github.com/HKUDS/nanobot/pull/1341)): **Web chat channel** (stalled since February).  
- **#2194** ([Issue](https://github.com/HKUDS/nanobot/issues/2194)): **Jina search fallback failure** (closed but DuckDuckGo now problematic).  

--- 

**Project Health**: **Active but security-sensitive**. Rapid feature development balances against stability gaps. Prioritizing **localhost access fixes** (#2796) and **DuckDuckGo stability** (#2828) would improve trust.

</details>

<details>
<summary><strong>PicoClaw</strong> — <a href="https://github.com/sipeed/picoclaw">sipeed/picoclaw</a></summary>

### **PicoClaw Project Digest – 2026-04-06**  

#### **1. Today’s Overview**  
Activity remains high, with **8 new issues** and **8 PRs updated** in the last 24 hours. Most issues are bug reports (5/8), particularly affecting **WebUI, Android app, and provider integrations**. One PR was merged (#2353, adding a memory benchmark), while others focus on **bug fixes (WebSocket auth, model configs)** and **enhancements (CLI UI, monitoring tools)**. No new releases, suggesting ongoing stabilization before the next version.  

#### **2. Releases**  
*No new releases today.*  

#### **3. Project Progress**  
- **Merged PR** [#2353](https://github.com/sipeed/picoclaw/pull/2353): Added a **LOCOMO-based memory benchmark** for retrieval evaluation (part of #1919).  
- **Notable Open PRs**:  
  - [#2375](https://github.com/sipeed/picoclaw/pull/2375): Fixes Docker path consistency.  
  - [#2372](https://github.com/sipeed/picoclaw/pull/2372): Resolves **API key/model lookup bugs** (#2371, #2286).  
  - [#2369](https://github.com/sipeed/picoclaw/pull/2369): Introduces **PicoWatch**, a macOS menu bar app for WhatsApp agent monitoring.  

#### **4. Community Hot Topics**  
- **Issue** [#2354](https://github.com/sipeed/picoclaw/issues/2354) (5 comments): **WebUI unresponsiveness**, with input fields/buttons disabled. Linked to PR [#2363](https://github.com/sipeed/picoclaw/pull/2363) (WebSocket auth fixes).  
- **Issue** [#2371](https://github.com/sipeed/picoclaw/issues/2371): **Agent loop errors** with model/provider configs, partially addressed by PR #2372.  
- **Feature Request** [#2376](https://github.com/sipeed/picoclaw/issues/2376): **Disable Enter-to-send** (Android), reflecting UX friction.  

#### **5. Bugs & Stability** *(Severity Ranking)*  
1. **[#2354](https://github.com/sipeed/picoclaw/issues/2354)** (Critical): **WebUI broken** – input/send disabled.  
2. **[#2371](https://github.com/sipeed/picoclaw/issues/2371)** (High): **Agent crashes** due to config parsing.  
3. **[#2368](https://github.com/sipeed/picoclaw/issues/2368)** (Medium): **Android model config** fails despite valid API key.  
4. **[#2374](https://github.com/sipeed/picoclaw/issues/2374)** (Medium): **Gemini model** fails despite working `curl`.  

*Fix PRs exist for #2354 (#2363) and #2371 (#2372).*  

#### **6. Feature Requests & Roadmap Signals**  
- **Enhancement** [#1372](https://github.com/sipeed/picoclaw/issues/1372): **OpenIM plugin support** – aligns with extensibility goals.  
- **UX Improvement** [#2376](https://github.com/sipeed/picoclaw/issues/2376): **Enter-key behavior** – likely low-effort, high-impact for mobile.  
- **Monitoring** [#2369](https://github.com/sipeed/picoclaw/pull/2369): **PicoWatch** (trial tracking) – signals focus on user analytics.  

#### **7. User Feedback Summary**  
- **Pain Points**:  
  - Android app **configuration issues** (#2368, #2367).  
  - **Provider integration instability** (Gemini, OpenRouter).  
- **Satisfaction**:  
  - Appreciated **benchmarking tools** (#2353).  
  - Enthusiasm for **CLI UI improvements** (#2229).  

#### **8. Backlog Watch**  
- **Issue** [#1372](https://github.com/sipeed/picoclaw/issues/1372) (Open since March 11): **OpenIM plugin** – needs maintainer input on feasibility.  
- **PR** [#2209](https://github.com/sipeed/picoclaw/pull/2209) (Open since March 31): **Telegram TLS fixes** – critical for Termux users.  

---  
**Project Health**: **Active but bug-heavy**. Focus on stabilizing WebUI, Android, and provider integrations before feature expansion. Community contributions (e.g., PicoWatch, CLI UI) indicate growing ecosystem engagement.

</details>

<details>
<summary><strong>NanoClaw</strong> — <a href="https://github.com/qwibitai/nanoclaw">qwibitai/nanoclaw</a></summary>

### **NanoClaw Project Digest** (2026-04-06)  
**GitHub Activity:** [qwibitai/nanoclaw](https://github.com/qwibitai/nanoclaw)  

---

#### **1. Today's Overview**  
NanoClaw saw **moderate-high activity** with 6 issues (3 closed, 3 open) and **27 PRs updated** (16 merged/closed). Key themes included **auth/security concerns** (SigV4, credential proxy risks), **container optimization** (UV cache persistence, Apple Container fixes), and **channel integrations** (Telegram, WhatsApp, Feishu). No new releases, but merged PRs indicate progress toward **multi-channel stability** and **admin controls** (e.g., #1674, #1673).  

---

#### **2. Releases**  
*No new releases today.*  

---

#### **3. Project Progress**  
**Merged/Closed PRs (Highlights):**  
- **#1674**: Added `group_type` parameter to `register_group` MCP tool, enabling explicit channel/thread registration.  
- **#1673**: Implemented **Telegram channel support** with mocked tests for token gating and message routing.  
- **#1592**: Improved UX with **working acknowledgments** for piped messages.  
- **#1239**: Enhanced credential injection logic, prioritizing `process.env` over `.env`.  
- **#1663**: Experimental **local LLM support** added (closed, but signals interest in diversification).  

---

#### **4. Community Hot Topics**  
- **#1669 [OPEN]**: *Credential Proxy risks with Anthropic bans* – Reflects anxiety over **OAuth compliance** ([Link](https://github.com/qwibitai/nanoclaw/issues/1669)).  
- **#1671 [OPEN]**: *Persist UV cache across containers* – Aims to **reduce redundant downloads** (high engagement) ([Link](https://github.com/qwibitai/nanoclaw/pull/1671)).  
- **#1668 [OPEN]**: *Feishu UX overhaul* – Focus on **progress cards and logging** for enterprise users ([Link](https://github.com/qwibitai/nanoclaw/pull/1668)).  

**Underlying Needs:** Security assurances, performance optimization, and enterprise-friendly UX.  

---

#### **5. Bugs & Stability**  
**Critical:**  
- **#1659 [OPEN]**: Apple Container build fails due to **scanner vs. Bun/zod incompatibility** – Blocks macOS users ([Link](https://github.com/qwibitai/nanoclaw/issues/1659)).  
- **#1642 [CLOSED]**: Main agent **global memory path mismatch** – Fixed but highlights config fragility.  

**Moderate:**  
- **#1665 [OPEN]**: `.claude/settings.local.json` gitignore request – Low risk but **common dev pain point** ([Link](https://github.com/qwibitai/nanoclaw/issues/1665)).  

---

#### **6. Feature Requests & Roadmap Signals**  
- **Telegram/WhatsApp integrations** (#1673, #1661) likely to land soon, given merged tests.  
- **Local LLM support** (#1663) and **OpenCode SDK** (#1628) suggest **backend diversification**.  
- **Podman supply-chain isolation** (#1650) aligns with **security hardening** trends.  

---

#### **7. User Feedback Summary**  
- **Pain Points:**  
  - Credential proxy risks (#1669) and **Anthropic compliance** fears.  
  - **Apple Container usability** (#1659) frustrates macOS devs.  
- **Satisfaction:**  
  - Positive reception to **multi-channel fixes** (e.g., #1673) and **Feishu UX improvements** (#1668).  

---

#### **8. Backlog Watch**  
- **#541 [CLOSED]**: *Improved container queue lifecycle* – Closed after 5 weeks; may resurface as scalability grows.  
- **#1628 [OPEN]**: *OpenCode SDK integration* – Needs review for **alternative backend support** ([Link](https://github.com/qwibitai/nanoclaw/pull/1628)).  

**Action Needed:** Maintainers should prioritize **#1659 (Apple Container)** and **#1669 (auth risks)** to address critical blockers.  

---  
**Style Note:** Data-driven, concise, with direct GitHub links for traceability. Highlighted **security, performance, and UX** as recurring themes.

</details>

<details>
<summary><strong>NullClaw</strong> — <a href="https://github.com/nullclaw/nullclaw">nullclaw/nullclaw</a></summary>

### **NullClaw Project Digest – 2026-04-06**  

---

#### **1. Today's Overview**  
The project remains highly active, with **19 PRs updated** (12 open, 7 merged/closed) and **8 issues addressed** (3 open, 5 closed). Development focus leans toward **API expansion** (#780, #771, #770), **bug fixes** (#781, #772), and **documentation cleanup** (#774–777). No new releases were cut, but recent merges (e.g., #705, #707) resolved long-standing issues. Community engagement is steady, with **no high-severity bugs** reported today but persistent interest in **deterministic workflows** (#778) and **cross-instance memory** (#711).  

---

#### **2. Releases**  
*No new releases.*  

---

#### **3. Project Progress**  
**Merged/Closed PRs (7):**  
- **Routing fix** (#705): Resolved Telegram’s subagent misidentification (#696).  
- **Heartbeat logging** (#710): Added debug logs for heartbeat ticks (#703).  
- **Tool wiring** (#708): Enabled `file_append` tool runtime registration (#699).  
- **Env flexibility** (#707): Pushover credentials now read from process env (#698).  
- **Docs clarity** (#706): Explicitly noted no `${VAR}` interpolation in configs (#697).  
- **Calculator tool** (#716): Added 20 math operations.  
- **Lark reactions** (#704): Support for emoji reactions on message receipt.  

---

#### **4. Community Hot Topics**  
- **REST Admin API** (#770, #771, #780): A major **multi-PR effort** to expose runtime controls via REST, attracting maintainer attention.  
- **Deterministic Workflows** (#778): Requests for Lobster-style workflow engines signal demand for **reproducible agent chains**.  
- **Responses API Fix** (#773 + #772): Users need **consistent schema formats** for OpenAI-compatible providers.  

---

#### **5. Bugs & Stability**  
**New Reports (Ranked):**  
1. **Shell tool Docker error** (#779): Regression in Brew-installed versions (critical for non-Docker users). *No fix PR yet.*  
2. **Responses API schema mismatch** (#773): Fixed in #772 (awaiting merge).  
3. **Null JSON handling** (#781): Guard against provider-specific null values (e.g., GLM-5).  

---

#### **6. Feature Requests & Roadmap Signals**  
- **Deterministic workflows** (#778): Likely to gain traction given parallels to #711 (cross-memory sync).  
- **Knowledge Graph Memory** (#712): SQLite-backed entity-relation storage — advanced but niche.  
- **Admin API** (#770–780): Likely to ship in next release given rapid progress.  

---

#### **7. User Feedback Summary**  
- **Pain points**:  
  - **Config confusion**: Users misinterpret `${VAR}` interpolation (#697) and subagent routing (#696).  
  - **Tool reliability**: Broken shell tool (#779) and unwired tools (#699) frustrate workflows.  
- **Praise**:  
  - **Env flexibility**: Pushover env var support (#707) praised for deployment ease.  

---

#### **8. Backlog Watch**  
- **Cross-Memory Sync** (#711): Open since 2026-03-23; key for multi-agent use cases.  
- **Knowledge Graph PR** (#712): Complex but underexplored; needs review.  
- **Documentation Overhaul** (#774–777): Critical to reduce user confusion; likely to merge soon.  

---  

**Style Note**: Data-driven, with GitHub links embedded for traceability. Highlights **active development** but flags **testing gaps** (e.g., #779 regression).

</details>

<details>
<summary><strong>IronClaw</strong> — <a href="https://github.com/nearai/ironclaw">nearai/ironclaw</a></summary>

### **IronClaw Project Digest - 2026-04-06**  

#### **1. Today's Overview**  
The IronClaw project remains highly active, with **50 PRs updated** (14 merged/closed) and **12 issues updated** (9 open, 3 closed) in the last 24 hours. Key themes include:  
- **Security hardening** (e.g., removal of unsafe API URL rewriters in WASM channels)  
- **UX improvements** (e.g., hot-reload for LLM providers, Slack thread history fetching)  
- **Localization & internationalization** (Korean translation added)  
No new releases were published, but **staging CI promotions** indicate steady progress toward the next version.  

#### **2. Releases**  
**No new releases today.**  

#### **3. Project Progress**  
**Merged/Closed PRs (Highlights):**  
- **[#2064](https://github.com/nearai/ironclaw/pull/2064)** – Fixed broken test builds and macOS-incompatible SSRF tests.  
- **[#2010](https://github.com/nearai/ironclaw/issues/2010)** – Fixed `AGENT_AUTO_APPROVE_TOOLS` being ignored in Engine V2.  
- **[#1950](https://github.com/nearai/ironclaw/issues/1950)** – Patched orphaned `tool_result` messages causing Anthropic API errors.  
- **[#1899](https://github.com/nearai/ironclaw/issues/1899)** – Critical fix for missing home directory in `ironclaw` user setup.  

#### **4. Community Hot Topics**  
- **[#1350](https://github.com/nearai/ironclaw/issues/1350)** (🔥 **2 👍, 2 comments**) – **Hot-reload for LLM providers** – Users want immediate model switching without restarts.  
- **[#2056](https://github.com/nearai/ironclaw/issues/2056)** (🚨 **Security**) – Removal of unsafe **API URL rewriters** in WASM channels (linked to **[#2057](https://github.com/nearai/ironclaw/issues/2057)** for refactoring).  
- **[#2066](https://github.com/nearai/ironclaw/pull/2066)** – **Slack thread history fetching** – Enhances bot context when mentioned in threads.  

#### **5. Bugs & Stability**  
**Critical/High Severity:**  
- **[#2056](https://github.com/nearai/ironclaw/issues/2056)** – **Security risk**: Production code exposes test-only API URL rewriting (fix pending).  
- **[#2048](https://github.com/nearai/ironclaw/issues/2048)** – Telegram WASM channel silently fails due to reserved name conflict (fix in **[#2051](https://github.com/nearai/ironclaw/pull/2051)**).  
- **[#846](https://github.com/nearai/ironclaw/issues/846)** – `onboard` fails with DB error but app still starts (long-standing issue).  

#### **6. Feature Requests & Roadmap Signals**  
- **[#1350](https://github.com/nearai/ironclaw/issues/1350)** – **Hot-reload for LLM providers** (likely to land soon).  
- **[#2045](https://github.com/nearai/ironclaw/issues/2045)** – Native Rust workflow shell (`ironclaw-lobster`) integration.  
- **[#70](https://github.com/nearai/ironclaw/issues/70)** – **Persistent agent feed system** (low activity but high potential).  

#### **7. User Feedback Summary**  
- **Positive**: Nerq Trust Score of **78.1/100** ([#2054](https://github.com/nearai/ironclaw/issues/2054)).  
- **Pain Points**:  
  - **Poor UX** when changing LLM providers ([#1350](https://github.com/nearai/ironclaw/issues/1350)).  
  - **Silent failures** in Telegram WASM channel ([#2048](https://github.com/nearai/ironclaw/issues/2048)).  
  - **Initial setup bugs** ([#846](https://github.com/nearai/ironclaw/issues/846)).  

#### **8. Backlog Watch**  
- **[#70](https://github.com/nearai/ironclaw/issues/70)** (Feed system) – Open since **Feb 2026**, needs design consensus.  
- **[#1050](https://github.com/nearai/ironclaw/pull/1050)** (Gateway CLI commands) – Stalled since **March 2026**, rebase needed.  
- **[#920](https://github.com/nearai/ironclaw/pull/920)** (Composio tool integration) – Competing PRs suggest high demand.  

---  
**Overall Health:** **Active, security-conscious, UX-focused.** Key risks: unresolved security issues ([#2056](https://github.com/nearai/ironclaw/issues/2056)) and long-standing bugs ([#846](https://github.com/nearai/ironclaw/issues/846)).

</details>

<details>
<summary><strong>LobsterAI</strong> — <a href="https://github.com/netease-youdao/LobsterAI">netease-youdao/LobsterAI</a></summary>

### **LobsterAI Project Digest (2026-04-06)**  

---

#### **1. Today's Overview**  
Activity remains steady with **11 open PRs** (all updated today) and **1 active issue**. No new releases were published. The focus is on **timed task improvements** (5 PRs), **dependency updates** (4 PRs), and **session management fixes**. Dependabot dominates PR activity, while a user-reported Python script issue (#1487) remains unresolved.  

---

#### **2. Releases**  
*No new releases today.*  

---

#### **3. Project Progress**  
No PRs were merged/closed today, but notable **open PRs advancing features**:  
- **Timed Task UX Overhaul**: PR [#1488](https://github.com/netease-youdao/LobsterAI/pull/1488) introduces card-based grids, search, and grouped history.  
- **Local macOS Notifications**: PR [#1489](https://github.com/netease-youdao/LobsterAI/pull/1489) adds native notifications for scheduled tasks.  
- **Session-Independent Skill Management**: PR [#1494](https://github.com/netease-youdao/LobsterAI/pull/1494) fixes skill state leakage across sessions.  

---

#### **4. Community Hot Topics**  
- **Issue #1487** ([Link](https://github.com/netease-youdao/LobsterAI/issues/1487)): A user reports Python script failures with local 30B models, contrasting with Claude CLI compatibility. Needs deeper debugging.  
- **PR #1488** ([Link](https://github.com/netease-youdao/LobsterAI/pull/1488)): Major timed task UI revamp, suggesting strong demand for better task management workflows.  

---

#### **5. Bugs & Stability**  
- **High Severity**:  
  - **Python Script Execution** (Issue #1487): Critical for local model users; no fix PR yet.  
- **Moderate Severity**:  
  - **Timed Task Channel Updates** (PR [#1490](https://github.com/netease-youdao/LobsterAI/pull/1490)): Fixes stale delivery channel displays post-edit.  

---

#### **6. Feature Requests & Roadmap Signals**  
- **Timed Task Testing**: PR [#1486](https://github.com/netease-youdao/LobsterAI/pull/1486) adds a "Test Task" button, likely to ship soon.  
- **Historical Task Grouping**: PR [#1449](https://github.com/netease-youdao/LobsterAI/pull/1449) suggests demand for cleaner session organization.  

---

#### **7. User Feedback Summary**  
- **Pain Points**:  
  - Local model compatibility issues (#1487) frustrate users relying on custom workflows.  
  - Timed task UX is a recurring theme (3 PRs), indicating prior friction.  
- **Positive Signals**: Active contributions (e.g., macOS notifications) show engagement with niche use cases.  

---

#### **8. Backlog Watch**  
- **Dependency PRs** (#1277, #1278): Open since April 2, awaiting review. Low risk but may need rebasing.  
- **Issue #1487**: New but high-impact; warrants maintainer attention given model-specific debugging complexity.  

---  

**Style Note**: Objective, data-driven with embedded GitHub links. Highlights project health via active contributions and unresolved pain points.

</details>

<details>
<summary><strong>TinyClaw</strong> — <a href="https://github.com/TinyAGI/tinyagi">TinyAGI/tinyagi</a></summary>

No activity in the last 24 hours.

</details>

<details>
<summary><strong>Moltis</strong> — <a href="https://github.com/moltis-org/moltis">moltis-org/moltis</a></summary>

# Moltis Project Digest - 2026-04-06  

## 1. Today's Overview  
The project shows **high activity** with 10 updated issues (7 open, 3 closed) and 11 updated PRs (5 open, 6 merged/closed). A new release (`20260405.06`) was published, though details are unspecified. Key focus areas include **Matrix integration** (both bugs and feature requests), **proxy support enhancements**, and **LLM model discovery fixes**. The community is actively proposing new features like PDF handling and local Whisper setup.  

---

## 2. Releases  
**20260405.06** ([Release](https://github.com/moltis-org/moltis/releases/tag/20260405.06))  
- No changelog provided, but merged PRs suggest updates include:  
  - Application-level HTTP proxy support (#561)  
  - Improved model discovery via `/v1/models` endpoint (#560)  
  - Matrix channel integration (#500)  

---

## 3. Project Progress  
**Merged/Closed PRs (6):**  
- **#564**: Auto-cleanup of orphaned sessions/sandbox containers (critical for resource management).  
- **#550**: Channel-level proxy support for Telegram (addresses #548).  
- **#562**: Added GitHub artifact attestations for security compliance.  
- **#500**: Matrix channel integration (cherry-picked from #331).  
- **#560**: Fixed model discovery by querying `/v1/models` before probing.  
- **#561**: Added `upstream_proxy` config for global HTTP traffic routing.  

---

## 4. Community Hot Topics  
- **#233 [Matrix Support]** ([Issue](https://github.com/moltis-org/moltis/issues/233))  
  - **5 👍, 4 comments** – High demand for Matrix integration, but #569 reveals config issues blocking adoption.  
- **#567 [Website Branding Update]** ([PR](https://github.com/moltis-org/moltis/pull/567))  
  - Showcases Moltis as a "secure persistent personal agent server in Rust," emphasizing provider/channel flexibility.  
- **#548/550 [Proxy Support]** ([Issue](https://github.com/moltis-org/moltis/issues/548) | [PR](https://github.com/moltis-org/moltis/pull/550))  
  - Reflects enterprise needs for network flexibility.  

---

## 5. Bugs & Stability  
**Critical:**  
- **#569**: Matrix config resolution failure ([Issue](https://github.com/moltis-org/moltis/issues/569)) – Blocks feature rollout.  
- **#565**: Login fails on IP binding changes ([Issue](https://github.com/moltis-org/moltis/issues/565)) – Affects local deployments.  
**High:**  
- **#568**: LLM list retrieval failure ([Issue](https://github.com/moltis-org/moltis/issues/568)) – Impacts provider usability.  
**Fixed:**  
- **#549**: MacOS OAuth flow fixed.  
- **#551**: Model detection now probes `/v1/models`.  

---

## 6. Feature Requests & Roadmap Signals  
- **#571 [Prompt Caching]** ([Issue](https://github.com/moltis-org/moltis/issues/571)) – Likely for performance optimization.  
- **#570 [Local Whisper Setup]** ([Issue](https://github.com/moltis-org/moltis/issues/570)) – Aligns with offline/self-hosted trends.  
- **#563 [PDF Support]** ([Issue](https://github.com/moltis-org/moltis/issues/563)) – High user value for document workflows.  
*Prediction:* PDF support and local Whisper may land in the next release.  

---

## 7. User Feedback Summary  
- **Pain Points**:  
  - Proxy/config issues (#565, #548) frustrate enterprise users.  
  - Matrix integration is desired but buggy (#569).  
- **Positive Signals**:  
  - Active contributions to security (attestations) and cleanup (#564).  

---

## 8. Backlog Watch  
- **#355 [Copilot Proxy Fix]** ([PR](https://github.com/moltis-org/moltis/pull/355)) – Open since March, needs review.  
- **#233 [Matrix Support]** – Open since February, now linked to #500 (merged).  

**Project Health:** **🟢 Active** – Strong momentum but needs focus on stability (Matrix, proxy, login bugs).  

---  
*Digest generated from [moltis-org/moltis](https://github.com/moltis-org/moltis) data.*

</details>

<details>
<summary><strong>CoPaw</strong> — <a href="https://github.com/agentscope-ai/CoPaw">agentscope-ai/CoPaw</a></summary>

### **CoPaw Project Digest – 2026-04-06**  

---

#### **1. Today's Overview**  
CoPaw remains highly active with **31 issues updated** (27 open, 4 closed) and **16 PRs updated** (14 open, 2 merged/closed) in the last 24 hours. Community engagement is strong, with multiple high-comment threads discussing **CPU usage bugs, model compatibility, and skill ecosystem improvements**. Stability issues dominate recent reports, particularly around **hot-reload leaks (MCP clients) and tool-calling loops** with Gemma4 models. No new releases were published today, but several PRs address critical bugs (e.g., [#2998](#2998) for MCP caching).  

---

#### **2. Releases**  
No new releases today.  

---

#### **3. Project Progress**  
- **Merged/Closed PRs**:  
  - [#2998](https://github.com/agentscope-ai/CoPaw/pull/2998): Fixed MCP client registration race conditions by introducing caching.  
  - [#2974](https://github.com/agentscope-ai/CoPaw/pull/2974): Logo-related cleanup (closed without merge).  

---

#### **4. Community Hot Topics**  
- **High CPU Usage at Idle** ([#2888](https://github.com/agentscope-ai/CoPaw/issues/2888)): 9 comments. Root cause traced to `anyio` cancellation handling; users demand energy efficiency fixes.  
- **Llama.cpp Installation Failures** ([#2955](https://github.com/agentscope-ai/CoPaw/issues/2955)): 8 comments. Windows users report silent failures; PR [#2989](https://github.com/agentscope-ai/CoPaw/pull/2989) aims to fix archive extraction.  
- **Skill Ecosystem Demand** ([#2361](https://github.com/agentscope-ai/CoPaw/issues/2361)): 2 comments + 2 👍. Users urge faster rollout of shared skill directories and tagging (#2323).  

---

#### **5. Bugs & Stability** *(Ranked by Severity)*  
1. **Critical**:  
   - **MCP Client Leaks** ([#2960](https://github.com/agentscope-ai/CoPaw/issues/2960)): Causes CPU spikes during hot-reload. Fix in progress ([#2979](https://github.com/agentscope-ai/CoPaw/pull/2979)).  
   - **Gemma4 Infinite Tool Loops** ([#2947](https://github.com/agentscope-ai/CoPaw/issues/2947)): Model repeatedly calls tools without completion.  
2. **High**:  
   - **File Guard Bypass via Shell** ([#2967](https://github.com/agentscope-ai/CoPaw/issues/2967)): Security risk; PR [#2978](https://github.com/agentscope-ai/CoPaw/pull/2978) patches path detection.  
   - **Telegram Channel Freezes** ([#2956](https://github.com/agentscope-ai/CoPaw/issues/2956)): Long-running sessions become unresponsive.  

---

#### **6. Feature Requests & Roadmap Signals**  
- **Skill Tagging & Indexing** ([#2323](https://github.com/agentscope-ai/CoPaw/issues/2323)): Likely to be prioritized for v1.1 given user demand.  
- **Global Skills Directory** ([#2032](https://github.com/agentscope-ai/CoPaw/issues/2032)): Closed but may resurface as multi-agent support grows.  
- **POSIX Tools on Windows** ([#2986](https://github.com/agentscope-ai/CoPaw/issues/2986)): Niche but aligns with cross-platform goals.  

---

#### **7. User Feedback Summary**  
- **Pain Points**:  
  - **Installation Chaos**: Confusing GPU/CPU defaults ([#2985](https://github.com/agentscope-ai/CoPaw/issues/2985)), broken model downloads (#2955).  
  - **UI Gaps**: Uninterruptible agents (#2991), garbled multilingual output (#2992), and Markdown rendering issues (#2975, #2983).  
- **Positive Signals**: Enthusiasm for WhatsApp channel (#2962) and skill ecosystem potential (#2361).  

---

#### **8. Backlog Watch**  
- **Older Issues Needing Attention**:  
  - **Qwen3 Model Support** ([#2598](https://github.com/agentscope-ai/CoPaw/issues/2598)): Open since 2026-03-31; unclear if non-standard models are feasible.  
  - **GitHub Copilot OAuth** ([#2366](https://github.com/agentscope-ai/CoPaw/pull/2366)): Stalled PR since March; needs maintainer review.  

---  

**Style Note**: Data-driven with GitHub links for traceability. Highlighted CPU/stability issues as top risks, skill ecosystem as growth area.

</details>

<details>
<summary><strong>ZeptoClaw</strong> — <a href="https://github.com/qhkm/zeptoclaw">qhkm/zeptoclaw</a></summary>

# ZeptoClaw Project Digest - 2026-04-06  

## 1. Today's Overview  
ZeptoClaw saw moderate activity with 2 closed issues and 7 updated PRs (5 open, 2 merged). The team focused on Telegram integration fixes, CLI tooling improvements, and browser automation enhancements. No new releases were published, but multiple stability-focused PRs were merged, indicating ongoing refinement of existing features.  

## 2. Releases  
*No new releases today.*  

## 3. Project Progress  
**Merged/Closed PRs:**  
- [#462](https://github.com/qhkm/zeptoclaw/pull/462): Fixed silent Telegram failures by implementing message chunking and plaintext fallback (addresses [#461](https://github.com/qhkm/zeptoclaw/issues/461)).  
- [#458](https://github.com/qhkm/zeptoclaw/pull/458): Added Telegram message chunking to handle long responses (>4096 UTF-16 units) with error fallback.  

## 4. Community Hot Topics  
- **CLI Shell Escaping Debate** ([#466](https://github.com/qhkm/zeptoclaw/issues/466) → PR [#467](https://github.com/qhkm/zeptoclaw/pull/467)): Users need unescaped CLI argument passing for wrapper tools (e.g., `gws {{args}}`). PR #467 introduces a `raw_string` parameter type to bypass shell escaping.  
- **OpenRouter Model Routing** ([#468](https://github.com/qhkm/zeptoclaw/pull/468)): Active discussion on proper vendor-prefixed model handling (e.g., `google/gemini-3-flash-preview`) when OpenRouter is configured.  

## 5. Bugs & Stability  
**Critical:**  
- *None today*  

**High:**  
- Telegram HTML rendering failures ([#461](https://github.com/qhkm/zeptoclaw/issues/461)): Fixed by [#462](https://github.com/qhkm/zeptoclaw/pull/462).  
- CLI shell escaping breaking wrappers ([#466](https://github.com/qhkm/zeptoclaw/issues/466)): Fix in progress via [#467](https://github.com/qhkm/zeptoclaw/pull/467).  

## 6. Feature Requests & Roadmap Signals  
- **Browser Automation** ([#459](https://github.com/qhkm/zeptoclaw/pull/459)): Major PR adding `agent-browser` integration with Chrome fallback—likely to ship in next release.  
- **Context Compaction** ([#460](https://github.com/qhkm/zeptoclaw/pull/460)): Multi-layered token overflow prevention could become a core stability feature.  

## 7. User Feedback Summary  
- **Pain Points:** Silent Telegram failures (#461) and CLI tooling inflexibility (#466) were top complaints.  
- **Satisfaction:** Quick fixes (#462, #458) show responsiveness to messaging platform issues.  

## 8. Backlog Watch  
- **Panel Feature Guidance** ([#487](https://github.com/qhkm/zeptoclaw/pull/487)): Improves UX for builds without `--features panel` but awaits review.  
- **OpenRouter Routing** ([#468](https://github.com/qhkm/zeptoclaw/pull/468)): Lingering PR (8 days) needing maintainer input on provider logic.  

**Project Health:** **Stable** – Active issue resolution and feature refinement, though some PRs await attention. Focus on Telegram and CLI usability signals strong user-centric development.

</details>

---
*This digest is auto-generated by [agents-radar](https://github.com/dylanzhang-ux/agents-radar).*