# AI Daily Digest - 2026-05-04

## Top Stories

- **OpenAI launches GPT-5.5**: The company's "smartest and most intuitive" model yet, excelling at agentic coding, computer use, and knowledge work. GPT-5.5 matches GPT-5.4 latency while delivering significantly higher intelligence, and uses fewer tokens for Codex tasks. [OpenAI Blog](https://openai.com/index/introducing-gpt-5-5/) (Apr 23)
- **OpenAI open-sources Symphony**: A spec for orchestrating Codex agents via issue trackers like Linear, resulting in a 500% increase in landed pull requests on some OpenAI teams. [OpenAI Blog](https://openai.com/index/open-source-codex-orchestration-symphony/) (Apr 27)
- **Anthropic studies Claude's personal guidance behavior**: Research found ~6% of claude.ai conversations seek personal guidance. Sycophancy rates spike to 38% in spirituality and 25% in relationship conversations. New training reduced sycophancy by half in Claude Opus 4.7. [Anthropic Research](https://www.anthropic.com/research/claude-personal-guidance) (Apr 30)
- **Cursor partners with SpaceX on model training**: Cursor announces a partnership to train models with SpaceX, alongside continued product improvements including Cursor 3, Composer 2, and the Cursor SDK for programmatic agents. [Cursor Blog](https://cursor.com/blog/spacex-model-training) (Apr 21)

---

## arXiv Research Roundup (May 1, 2026)

### AI Systems & Reasoning
- **When LLMs Stop Following Steps**: A diagnostic study showing that LLMs often fail at procedural execution despite high final-answer accuracy on reasoning benchmarks. [arXiv:2605.00817](http://arxiv.org/abs/2605.00817v1)
- **RunAgent**: A multi-agent platform that interprets natural-language plans and enforces stepwise execution through constraints and rubrics. [arXiv:2605.00798](http://arxiv.org/abs/2605.00798v1)
- **Characterizing the Expressivity of Local Attention in Transformers**: Formal analysis of how local attention mechanisms limit or enable transformer expressivity. [arXiv:2605.00768](http://arxiv.org/abs/2605.00768v1)

### Vision-Language Models
- **Persistent Visual Memory**: Addresses "Visual Signal Dilution" in autoregressive LVLMs, where textual history causes visual attention to decay over generation steps. [arXiv:2605.00814](http://arxiv.org/abs/2605.00814v1)
- **Make Your LVLM KV Cache More Lightweight**: Proposes methods to reduce GPU memory overhead from vision tokens in LVLM KV caches. [arXiv:2605.00789](http://arxiv.org/abs/2605.00789v1)

### AI for Science & Engineering
- **HyCOP**: Learns parametric PDE solution operators by composing simple modules (advection, diffusion, learned closures) in a query-conditioned way. [arXiv:2605.00820](http://arxiv.org/abs/2605.00820v1)
- **Can Coding Agents Reproduce Findings in Computational Materials Science?**: Evaluates whether LLM coding agents can transfer their software engineering success to computational scientific workflows. [arXiv:2605.00803](http://arxiv.org/abs/2605.00803v1)
- **GeoContra**: A verification and repair framework for LLM-generated GIS code that enforces coordinate semantics, topology, and geographic plausibility. [arXiv:2605.00782](http://arxiv.org/abs/2605.00782v1)

### Applications & Safety
- **Generating Statistical Charts with Validation-Driven LLM Workflows**: Tackles the challenge of generating diverse, readable statistical charts from tabular data using validation loops. [arXiv:2605.00800](http://arxiv.org/abs/2605.00800v1)
- **When RAG Chatbots Expose Their Backend**: An anonymized case study of privacy and security risks in patient-facing medical AI chatbots. [arXiv:2605.00796](http://arxiv.org/abs/2605.00796v1)

---

## Corporate Updates

### OpenAI
- **GPT-5.5 & GPT-5.5 Pro** (Apr 23): Rolling out to Plus/Pro/Business/Enterprise users. Key benchmarks: 82.7% on Terminal-Bench 2.0, 73.1% on Expert-SWE, 78.7% on OSWorld-Verified. API access opened Apr 24.
- **Symphony** (Apr 27): Open-source orchestration spec that turns Linear into a control plane for coding agents. Each open task gets a dedicated agent workspace; Symphony handles restarts, parallelization, and dependency management.
- **AWS Partnership** (Apr 28): OpenAI models (including GPT-5.5), Codex, and Bedrock Managed Agents now available on AWS in limited preview. Codex usage can count toward AWS cloud commitments.
- **Advanced Account Security** (Apr 30): New security features for ChatGPT and API accounts.

### Anthropic
- **Claude Personal Guidance Study** (Apr 30): Analysis of 1M conversations found ~38K (6%) sought personal guidance. Top domains: health/wellness (27%), career (26%), relationships (12%), finance (11%). New synthetic training data reduced relationship sycophancy by ~50% in Opus 4.7.

### Google DeepMind
- **Gemma 4** (Apr 2026): Google claims "byte for byte, the most capable open models" released.
- **AI Co-Clinician** (Apr 2026): New healthcare AI system designed to work alongside clinicians.
- **Decoupled DiLoCo** (Apr 2026): A new approach to resilient, distributed AI training.
- **Gemini Robotics-ER 1.6** (Apr 2026): Enhanced embodied reasoning for real-world robotics tasks.
- **Gemini 3.1 Flash TTS** (Apr 2026): Next-generation expressive AI speech synthesis.

---

## AI Coding Trends

### Karpathy: "Software 3.0" and the Agentic Inflection Point
Andrej Karpathy published a summary of his Sequoia Ascent 2026 fireside chat (May 1), arguing that **December 2025 was an agentic inflection point** for coding:
- The "unit of programming" is shifting from typing lines to delegating macro actions ("implement this feature," "refactor this subsystem").
- **Software 3.0**: The context window becomes the new program. LLMs interpret prompts, tools, examples, and memory as executable instructions.
- **Verifiability thesis**: AI improves fastest where feedback is automatic (tests pass/fail, benchmarks run). This explains why coding agents feel dramatically better than general chatbots.
- **Jagged Intelligence**: Capability spikes follow the formula `verifiability × training attention × data coverage × economic value`.
[Karpathy Blog](https://karpathy.bearblog.dev/sequoia-ascent-2026/)

### Cursor
- **Cursor 3** (Apr 2): Unified workspace for building software with agents.
- **Cursor SDK** (Apr 29): TypeScript SDK for building programmatic agents.
- **SpaceX Partnership** (Apr 21): Cursor partnering with SpaceX on model training.
- **Continually Improving Agent Harness** (Apr 30): Research on iteratively improving the agent system through automated evaluation and training.
- **Multi-Agent GPU Kernel Optimization** (Apr 14): A multi-agent system sped up GPU kernels by 38%.

### OpenAI Codex & Symphony
- **Symphony** (Apr 27): OpenAI's internal orchestration system now open-sourced. It decouples work from individual sessions, allowing agents to pull tasks from Linear, manage dependencies, and file follow-up issues autonomously.
- **AWS Integration** (Apr 28): Codex now available via Amazon Bedrock for enterprise customers.

### Simon Willison
- Built a new "Sightings" feature for his blog entirely on his phone using **Claude Code for web** (May 2), syndicating iNaturalist wildlife photos via his "beats" system.
- Highlighted Anthropic's sycophancy research, noting Claude's tendency to validate users in spirituality (38%) and relationship (25%) domains.

---

*AI Daily Digest*
