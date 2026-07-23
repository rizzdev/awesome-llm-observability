# Awesome LLM Observability [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Tracing, monitoring, and evaluating LLM apps once they hit production.

I put every LLM feature I ship behind a trace within the first week, because the alternative is guessing why a chain that worked fine in the demo fell apart for a real user. This list is the tools I've actually looked at for that job: platforms that capture spans and cost per call, evals that catch regressions before a release goes out, and the standards everyone is quietly converging on so you're not stuck reading one vendor's proprietary trace format forever.

Everything here has a real repo or a real product behind it, checked by hand. I kept the well-known platforms next to the small, newer projects on purpose, because a two-person team's sharper trace viewer is sometimes exactly what you need and the big names never bother building it. If something looked abandoned, was a thin wrapper with nothing behind it, or just duplicated a tool already on the list, it didn't make the cut.

🌿 means it's newer and still under 500 stars. Often worth a try, just less proven than the ones that have been around a while.

## Contents

<table>
<tr>
<td valign="top">

- [🔭 Tracing &amp; Monitoring Platforms](#tracing-monitoring-platforms)
- [🧰 Self-Hosted &amp; Open-Source Stacks](#self-hosted-open-source-stacks)
- [🧪 Evaluation &amp; Testing](#evaluation-testing)
- [📐 Open Standards &amp; OpenTelemetry](#open-standards-opentelemetry)

</td>
<td valign="top">

- [🤖 Agent &amp; Coding-Agent Observability](#agent-coding-agent-observability)
- [💰 Cost &amp; Token Tracking](#cost-token-tracking)
- [🧩 Language &amp; Framework SDKs](#language-framework-sdks)

</td>
<td valign="top">

- [📚 Papers &amp; Books](#papers-books)
- [🗂️ Reference Repos &amp; Guides](#reference-repos-guides)
- [🎓 Courses &amp; Community](#courses-community)

</td>
</tr>
</table>

---

<a id="tracing-monitoring-platforms"></a>
## 🔭 Tracing & Monitoring Platforms

- **[Langfuse](https://github.com/langfuse/langfuse)** · Open source LLM engineering platform for tracing, evals, prompt management and datasets, about as close to a default choice as this space has
- **[Helicone](https://github.com/Helicone/helicone)** · One line of code to monitor, evaluate and experiment on LLM calls, self-hostable with a separate open source AI gateway alongside it
- **[Arize Phoenix](https://github.com/Arize-ai/phoenix)** · Open source AI observability and evaluation platform built on OpenTelemetry tracing, runs from a notebook, a container or the cloud
- **[Traceloop (OpenLLMetry)](https://github.com/traceloop/openllmetry)** · OpenTelemetry-based instrumentation for LLM providers and vector DBs that emits standard OTel data any backend can read
- **[LangSmith](https://smith.langchain.com/)** · Agent and LLM observability, evaluation and prompt engineering platform from the LangChain team, framework-agnostic despite the name
- **[W&B Weave](https://github.com/wandb/weave)** · Tracing, evaluation and monitoring toolkit for GenAI apps and agents, built on top of Weights & Biases
- **[Braintrust](https://www.braintrust.dev/)** · Closed source SaaS unifying tracing, evals and prompt/model comparison, used by Notion, Stripe and Vercel
- **[Comet Opik](https://github.com/comet-ml/opik)** · Open source LLM evaluation and observability platform with tracing, automated evals and dashboards, no feature gating between tiers
- **[Datadog LLM Observability](https://www.datadoghq.com/product/llm-observability/)** · End-to-end monitoring, evaluation and security tooling for LLM apps folded into Datadog's existing APM product
- **[Pydantic Logfire](https://github.com/pydantic/logfire)** · Opinionated OpenTelemetry wrapper for production LLM and agent systems with Python/JS/Rust SDKs, query your traces with plain SQL
- **[Galileo](https://galileo.ai/)** · Enterprise AI observability platform for agent reliability, guardrails and monitoring, runs its own small models for fast evals
- **[PromptLayer](https://www.promptlayer.com/)** · One of the earliest LLM observability players, going back to 2022, prompt management plus request, cost and latency tracking
- **[Laminar](https://github.com/lmnr-ai/lmnr)** · OTel-native observability platform built specifically for AI agents, docker-compose self-host, known for a clean trace UX
- **[Langtrace](https://github.com/Scale3-Labs/langtrace)** · Real-time OpenTelemetry-based tracing, evals and metrics for LLM apps on a Postgres plus ClickHouse backend
- **[LangWatch](https://github.com/langwatch/langwatch)** · OTLP-native LLM Ops platform for tracing, evaluation, simulation and testing of AI agents with built-in RAGAS scorers
- **[OpenLIT](https://github.com/openlit/openlit)** · Self-hosted, OpenTelemetry-native platform bundling LLM tracing, GPU monitoring, cost tracking, prompt management and evals in one Docker/K8s deploy
- **[HoneyHive](https://www.honeyhive.ai/)** 🌿 · OpenTelemetry-native observability and evaluation platform covering the whole agent development lifecycle
- **[Literal AI](https://www.literalai.com/)** 🌿 · Observability, evaluation and monitoring for production LLM apps from the Chainlit team, with a self-host option
- **[Openlayer](https://www.openlayer.com/)** 🌿 · AI/ML observability platform combining pre-deployment testing, production monitoring and drift detection
- **[Athina](https://www.athina.ai/)** 🌿 · Tracing, online evals and cost/latency analytics for LLM apps, also ships an open source evals SDK separately
- **[Parea](https://www.parea.ai/)** 🌿 · LLM evaluation, observability and human-annotation platform with a version-controlled prompt playground
- **[traceAI](https://github.com/future-agi/traceAI)** 🌿 · OpenTelemetry-based tracing framework for AI applications across Python, TypeScript, Java and C#
- **[Oodle.ai](https://www.oodle.ai/)** 🌿 · AI-native observability that ingests OpenTelemetry GenAI semantic-convention traces, positioned as a Datadog/Langfuse alternative

<a id="self-hosted-open-source-stacks"></a>
## 🧰 Self-Hosted & Open-Source Stacks

- **[AgentOps](https://github.com/AgentOps-AI/agentops)** · Self-hostable observability and devtool platform for AI agents with session replay, cost tracking and CrewAI/AutoGen/LangChain integrations
- **[Coze Loop](https://github.com/coze-dev/coze-loop)** · ByteDance's self-hosted full-lifecycle agent platform combining prompt engineering, multi-dimensional evaluation and pipeline observability
- **[SigNoz](https://github.com/SigNoz/signoz)** · OpenTelemetry-native observability platform with dedicated LLM tracing for LangChain, LlamaIndex and CrewAI, a good pick if you want unified infra plus LLM observability instead of a separate tool
- **[MLflow Tracing](https://github.com/mlflow/mlflow)** · Open source ML platform with built-in OpenTelemetry-compatible GenAI tracing and autologging for LangChain, OpenAI and LlamaIndex
- **[PostHog LLM Observability](https://github.com/PostHog/posthog)** · Open source product analytics platform extended with LLM tracing, per-user cost tracking and session replay for AI features
- **[llm-trace](https://github.com/llm-trace/llm-trace)** 🌿 · Zero-infrastructure LLM tracing library that stores everything in a single SQLite file, no Docker or Postgres required
- **[TMA1](https://github.com/tma1-ai/tma1)** 🌿 · Local-first, single-binary observability for coding agents (Claude Code, Codex, Copilot CLI) with an embedded time-series DB and MCP hooks that feed observations back into the agent loop
- **[openfuse](https://github.com/tma1-ai/openfuse)** 🌿 · Langfuse fork that swaps ClickHouse for GreptimeDB while keeping Langfuse's data model, UI and SDKs

<a id="evaluation-testing"></a>
## 🧪 Evaluation & Testing

- **[DeepEval](https://github.com/confident-ai/deepeval)** · Pytest-like open source LLM evaluation framework for RAG, chatbots and agents, implements G-Eval, hallucination and RAGAS-style metrics
- **[promptfoo](https://github.com/promptfoo/promptfoo)** · CLI and library for testing, evaluating and red-teaming prompts, agents and RAG pipelines across 50+ model providers
- **[Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai)** · Evaluation framework for LLMs and agents from the UK AI Safety Institute, with composable solvers, scorers and a rich log viewer, heavily used for agentic and safety evals
- **[Ragas](https://github.com/explodinggradients/ragas)** · The de facto reference-free evaluation library for RAG pipelines, integrated into Langfuse, LangWatch and TruLens
- **[TruLens](https://github.com/truera/trulens)** · Evaluation and tracking framework for LLM experiments and agents using feedback functions, instrumentation now built on OpenTelemetry
- **[Giskard](https://github.com/Giskard-AI/giskard-oss)** · Open source evaluation, testing and red-teaming library for LLM agents and RAG apps that automatically flags hallucinations and security flaws
- **[Evidently AI](https://github.com/evidentlyai/evidently)** · Open source framework to evaluate, test and monitor ML and LLM-powered systems with 100+ built-in metrics
- **[ARES](https://github.com/stanford-futuredata/ares)** · Automated evaluation framework for RAG systems measuring context relevance, faithfulness and answer relevance, from Stanford's FutureData Lab
- **[UpTrain](https://github.com/uptrain-ai/uptrain)** 🌿 · Open source platform with 20+ preconfigured evaluations and root-cause analysis, runs locally so nothing leaves your machine
- **[WhyLabs LangKit](https://github.com/whylabs/langkit)** · Open source toolkit that extracts quality, safety and relevance signals from prompts and responses, pairs with whylogs for production monitoring
- **[Fiddler Auditor](https://github.com/fiddler-labs/fiddler-auditor)** 🌿 · Red-teaming and robustness auditing for LLMs covering hallucination, prompt perturbation and model comparison

<a id="open-standards-opentelemetry"></a>
## 📐 Open Standards & OpenTelemetry

- **[OpenTelemetry Semantic Conventions for GenAI](https://github.com/open-telemetry/semantic-conventions-genai)** 🌿 · Official OTel spec defining gen_ai.* attributes, metrics, events and spans, the cross-vendor standard most platforms are converging on
- **[OpenInference](https://github.com/Arize-ai/openinference)** · Semantic convention spec for AI application tracing built on OpenTelemetry, standardizes span attributes for LLM calls, retrieval and tool calls
- **[OWASP Agent Observability Standard](https://github.com/OWASP/www-project-agent-observability-standard)** 🌿 · OWASP project defining a standard for agent observability, covering OTel/OCSF tracing and an Agent Bill of Materials
- **[opentelemetry-mcp-server](https://github.com/pavolloffay/opentelemetry-mcp-server)** 🌿 · MCP server that lets an LLM query and reason over your OpenTelemetry data like an OTel expert
- **[loongsuite-js](https://github.com/alibaba/loongsuite-js)** 🌿 · OpenTelemetry instrumentation plugins for JavaScript coding agents (Claude Code, OpenClaw), collecting traces and tool calls, from Alibaba
- **[openllmtelemetry](https://github.com/whylabs/openllmtelemetry)** 🌿 · Open LLM telemetry package from WhyLabs for capturing LLM app metrics via OpenTelemetry
- **[opentelemetry-instrumentation-ruby_llm](https://github.com/thoughtbot/opentelemetry-instrumentation-ruby_llm)** 🌿 · OpenTelemetry instrumentation for the RubyLLM gem, from thoughtbot, fills a real gap in the Ruby ecosystem

<a id="agent-coding-agent-observability"></a>
## 🤖 Agent & Coding-Agent Observability

- **[CloudDetail/apo](https://github.com/CloudDetail/apo)** 🌿 · OpenTelemetry plus eBPF observability platform that uses an LLM to automate root-cause analysis and troubleshooting, self-hosted, Go
- **[databuff](https://github.com/databufflabs/databuff)** 🌿 · AI-native OpenTelemetry APM with multi-agent root-cause analysis across traces, metrics and service topology, self-hosted, Java
- **[radicalbit AI Monitoring](https://github.com/radicalbit/radicalbit-ai-monitoring)** 🌿 · Self-hosted platform for monitoring AI models and LLMs in production, drift, data quality and model metrics
- **[Axon](https://github.com/langchain-tracer/Axon)** 🌿 · OpenTelemetry-native LLM observability CLI, point any OTEL exporter at it and watch LLM and agent traces in real time
- **[otelite](https://github.com/planetf1/otelite)** 🌿 · Lightweight OpenTelemetry receiver and local dashboard for LLM development, single binary, zero deps
- **[otellix](https://github.com/oluwajubelo1/otellix)** 🌿 · OpenTelemetry-native tracing, token tracking, cost attribution and prompt analytics for Go backends
- **[Lookspan](https://github.com/JoniMartin27/lookspan)** 🌿 · Local-first, MCP-native observability dashboard for AI agents with trace replay and dataset-driven evals
- **[tracely](https://github.com/evidentlyai/tracely)** 🌿 · LLM application tracing library based on OpenTelemetry, from the Evidently AI team
- **[agent-prism](https://github.com/evilmartians/agent-prism)** 🌿 · React components for visualizing AI agent traces, a UI toolkit for building your own trace viewer, from Evil Martians
- **[agentcanvas](https://github.com/vstorm-co/agentcanvas)** 🌿 · Visualizes Pydantic AI agent workflows from Logfire traces as an interactive HTML diagram
- **[llm-traces (Grafana plugin)](https://github.com/agoda-com/llm-traces)** 🌿 · Grafana app plugin for visualizing LLM traces in Tempo, prompts, completions, tool calls and token usage, supports OpenInference and OTel GenAI conventions, from Agoda
- **[agent-trace](https://github.com/Siddhant-K-code/agent-trace)** 🌿 · Observability for AI agents that shows what your agent did, why it cost that much, and what to fix
- **[agent-inspect](https://github.com/rajudandigam/agent-inspect)** 🌿 · Local execution trees for TypeScript AI agents to help you understand what happened in a run
- **[Agent-Blackbox](https://github.com/TaewoooPark/Agent-Blackbox)** 🌿 · Local-first flight recorder for coding agents, replays every run as a live session map and scores the context bill
- **[agent-lens](https://github.com/dreadnode/agent-lens)** 🌿 · Agent observability and replay tooling for AI safety and interpretability research
- **[traccia-py](https://github.com/traccia-ai/traccia-py)** 🌿 · OpenTelemetry-native observability, governance and compliance for AI agents and LLM applications
- **[dunetrace](https://github.com/dunetrace/dunetrace)** 🌿 · Self-hosted, real-time monitoring of production AI agents
- **[spark-dashboard](https://github.com/niklasfrick/spark-dashboard)** 🌿 · Real-time hardware and LLM inference monitoring, GPU/CPU/memory and vLLM metrics streamed to a dashboard
- **[AgentProvenance](https://github.com/ByteYellow/AgentProvenance)** 🌿 · Three-axis observability for sandboxed AI agents covering model intent, app context and runtime action
- **[heron](https://github.com/Netis/heron)** 🌿 · Reconstructs LLM agent traffic from network packets (pcap), no SDK or proxy, the Wireshark approach to agent observability
- **[AIOstack](https://github.com/aurva-io/AIOstack)** 🌿 · eBPF runtime visibility for AI workloads in Kubernetes, discovers shadow AI and traces LLM and tool activity with no code changes
- **[clawlens](https://github.com/nk3750/clawlens)** 🌿 · Local OpenClaw plugin for agent observability and guardrails, risk scoring, audit trails and a dashboard
- **[openclaw-exporter-to-langfuse](https://github.com/aliyun/openclaw-exporter-to-langfuse)** 🌿 · OpenClaw exporter that sends agent, LLM and tool tracing to Langfuse via OpenTelemetry, from Alibaba Cloud
- **[ClaudeSec](https://github.com/aanjaneyasinghdhoni/ClaudeSec)** 🌿 · Real-time AI agent observability dashboard that visualizes OpenTelemetry traces as a communication graph

<a id="cost-token-tracking"></a>
## 💰 Cost & Token Tracking

- **[splitrail](https://github.com/Piebald-AI/splitrail)** 🌿 · Fast, cross-platform, real-time token usage tracker and cost monitor for Claude Code, Codex CLI and other agent CLIs
- **[tokentelemetry](https://github.com/VasiHemanth/tokentelemetry)** 🌿 · Dashboard for autonomous and coding agents tracking tokens, sessions and tool calls
- **[opencode-bar](https://github.com/opgginc/opencode-bar)** 🌿 · Token usage tracker for OpenCode
- **[codex-usage-tracker](https://github.com/douglasmonsky/codex-usage-tracker)** 🌿 · Local-first MCP tools and dashboard for investigating Codex token usage, credits, costs and caching
- **[claude_telemetry](https://github.com/TechNickAI/claude_telemetry)** 🌿 · OpenTelemetry wrapper for the Claude Code CLI logging tool calls, token usage, costs and execution traces
- **[claude-code-metrics-prometheus](https://github.com/rockdarko/claude-code-metrics-prometheus)** 🌿 · Grafana dashboard for monitoring Claude Code CLI usage on Prometheus-compatible backends
- **[MCPSpend](https://github.com/andreisirbu91-lab/MCPSpend)** 🌿 · Real-time cost observability for Model Context Protocol tool calls, wraps any MCP server
- **[tokentally](https://github.com/steipete/tokentally)** 🌿 · One tiny library for LLM token and cost math
- **[inferock-bench](https://github.com/inferock/inferock-bench)** 🌿 · Local LLM cost-tracking proxy for OpenAI, Anthropic, Gemini and pinned OpenRouter calls with token accounting
- **[Azure OpenAI Logger](https://github.com/aavetis/azure-openai-logger)** 🌿 · Logging for Azure OpenAI via an API Management proxy routed into Application Insights, keeps telemetry inside your own Azure subscription
- **[openai-agents-tracing](https://github.com/yusuf-eren/openai-agents-tracing)** 🌿 · Open source tracing dashboard for the OpenAI Agents SDK, including costs and usage
- **[costclaw-telemetry](https://github.com/Aperturesurvivor/costclaw-telemetry)** 🌿 · Free real-time LLM cost tracking and dashboard for OpenClaw agents, installs in about a minute

<a id="language-framework-sdks"></a>
## 🧩 Language & Framework SDKs

- **[Spring AI Observability](https://docs.spring.io/spring-ai/reference/observability/index.html)** · Built-in Micrometer/OpenTelemetry tracing and metrics for chat model, vector store and tool calls in Java's Spring AI framework
- **[Semantic Kernel Telemetry](https://github.com/microsoft/semantic-kernel/blob/main/dotnet/docs/TELEMETRY.md)** · .NET's Semantic Kernel ships OpenTelemetry activity sources and GenAI-semantic-convention-compliant tracing out of the box
- **[OpenLLMetry Go SDK](https://github.com/traceloop/go-openllmetry)** 🌿 · Go instrumentation for OpenLLMetry, giving Go services the same OpenTelemetry-based LLM tracing as the Python/JS SDKs
- **[langfuse-java](https://github.com/langfuse/langfuse-java)** 🌿 · Official auto-generated Java client for the Langfuse ingestion API
- **[ruby_llm-monitoring](https://github.com/sinaptia/ruby_llm-monitoring)** 🌿 · Monitor LLM usage inside a Rails application
- **[ampere](https://github.com/socket-link/ampere)** 🌿 · Observable AI cognition for Kotlin Multiplatform, every agent decision emits a structured event

<a id="papers-books"></a>
## 📚 Papers & Books

- **[AI Observability for Large Language Model Systems](https://arxiv.org/abs/2604.26152)** · Survey proposing a five-layer taxonomy for LLM observability, from confidence calibration to infrastructure-level tracing
- **[Observability Engineering, 2nd Edition](https://www.oreilly.com/library/view/observability-engineering-2nd/9781098179915/)** · O'Reilly book by Majors, Fong-Jones and Miranda from the Honeycomb team, the standard text on event-based observability, high-cardinality telemetry and tracing that LLM instrumentation builds on

<a id="reference-repos-guides"></a>
## 🗂️ Reference Repos & Guides

- **[oss-llmops-stack](https://github.com/langfuse/oss-llmops-stack)** 🌿 · Modular open source LLMOps reference stack pairing LiteLLM routing with Langfuse observability
- **[LLM-Observability-FOSS](https://github.com/sarva-20/LLM-Observability-FOSS)** 🌿 · Step-by-step guide to learning LLM observability using entirely free open source tools
- **[Datadog llm-observability examples](https://github.com/DataDog/llm-observability)** 🌿 · Official Datadog examples teaching how to instrument the LLM Observability product
- **[qdrant-rag-eval](https://github.com/qdrant/qdrant-rag-eval)** 🌿 · Central repo for RAG evaluation reference material and partner workshops, from Qdrant
- **[multi-agent-observability-opentelemetry](https://github.com/chrisipanaque/multi-agent-observability-opentelemetry)** 🌿 · Reference implementation of OpenTelemetry distributed tracing patterns for multi-agent LLM systems
- **[microsoft-foundry-e2e-agent-observability-workshop](https://github.com/Azure-Samples/microsoft-foundry-e2e-agent-observability-workshop)** 🌿 · Hands-on Microsoft workshop covering Foundry Control Plane observability for agents
- **[pyconf-hyd-2026-trustworthy-llm-agents](https://github.com/droideronline/pyconf-hyd-2026-trustworthy-llm-agents)** 🌿 · PyCon Hyderabad workshop on building trustworthy LLM agents with OpenTelemetry and Langfuse
- **[Agent-Observability-Demo](https://github.com/Mr-Q526/Agent-Observability-Demo)** 🌿 · Teaching project showing what happens inside an AI agent turn by turn, decisions, tools and prompts
- **[llm-observability (codex-odyssey)](https://github.com/codex-odyssey/llm-observability)** 🌿 · Sample application from a Japanese tech-book chapter on LLM application observability

<a id="courses-community"></a>
## 🎓 Courses & Community

- **[Evaluating AI Agents](https://www.deeplearning.ai/courses/evaluating-ai-agents/)** · Free DeepLearning.AI short course with Arize AI on adding tracing to agents and running structured evaluation experiments
- **[Evaluating and Debugging Generative AI](https://www.deeplearning.ai/short-courses/evaluating-debugging-generative-ai/)** · Free DeepLearning.AI course with Weights & Biases on tracing, versioning and monitoring generative AI experiments
- **[Evidently AI Courses](https://www.evidentlyai.com/courses)** · Free hands-on courses covering LLM-as-judge design, RAG evaluation, adversarial testing and production monitoring
- **[MLOps Community](https://mlops.community/)** · Large practitioner community (Slack, YouTube, podcast) with regular deep-dives on LLMOps and production LLM observability
- **[Inside the LLM Call: GenAI Observability with OpenTelemetry](https://opentelemetry.io/blog/2026/genai-observability/)** · Official OpenTelemetry blog post walking through instrumenting LLM calls, agent spans and MCP tool calls with the GenAI semantic conventions

---

*Last audited 2026-07-22 · 107 items · [Submit an entry](contributing.md)*
