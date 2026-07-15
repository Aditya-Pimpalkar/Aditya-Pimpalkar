<h1 align="center">Hi, I'm Aditya Pimpalkar 👋</h1>

<p align="center">
  <b>Software Engineer · AI Engineer</b><br>
  <sub>Distributed systems · AI observability & evaluation · Java · Python · Go · AWS</sub><br>
  <sub>MSIS Northeastern '26 · AWS Certified · Building production backend & LLM systems</sub>
</p>

<p align="center">
  <a href="https://linkedin.com/in/aditya-pimpalkar-905b4417b">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="mailto:pimpalkar.aditya123@gmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white" alt="Email">
  </a>
  <a href="https://www.credly.com/users/aditya-pimpalkar">
    <img src="https://img.shields.io/badge/AWS%20Certified-SAA--C03-FF9900?style=flat&logo=amazon-aws&logoColor=white" alt="AWS Certified">
  </a>
  <a href="https://github.com/langchain4j/langchain4j/pull/5358">
    <img src="https://img.shields.io/badge/LangChain4j-Contributor-2F855A?style=flat&logo=github&logoColor=white" alt="LangChain4j Contributor">
  </a>
</p>

---

### About Me

Software engineer with 3+ years of backend experience at Cognizant and a graduate focus on AI systems. I build **production-grade observability and evaluation infrastructure** for LLM applications — the parts that make AI systems debuggable, measurable, and reliable rather than opaque and hoped-for.

The thing I've learned across professional backend and graduate AI work: **production AI engineering and production backend engineering are essentially the same job.** Both come down to the unglamorous parts — the validation layer, the eval harness, the retry logic, the cost budget, the graceful degradation when something goes wrong.

Currently seeking full-time roles starting Summer 2026 — Software Engineer, Backend, AI Engineer, or Platform/Infrastructure Engineer.

---

### 🌱 Recent Open Source

**[LangChain4j PR #5358](https://github.com/langchain4j/langchain4j/pull/5358)** — Merged (Jul 2026)

Added `enableAdaptiveReasoning` API to the `langchain4j-bedrock` module of [LangChain4j](https://github.com/langchain4j/langchain4j), the popular open-source Java LLM framework. The change added Claude Opus 4.7 adaptive reasoning support to the AWS Bedrock integration — backward-compatible with older Claude models, unit-tested against the confirmed working payload, reviewed and merged by the project maintainer. Resolved Issue [#5138](https://github.com/langchain4j/langchain4j/issues/5138).

---

### 🚀 Featured Projects

#### 📡 [AgentOps Radar — AI Agent Observability Platform](https://github.com/Aditya-Pimpalkar/Agentops-Radar)

**Production-grade distributed observability platform for AI agents** — full visibility into every model call, tool call, retrieval step, guardrail check, retry, and failure across agent workflows, with automated evaluation, semantic failure search, and replay-based regression testing.

`Go` · `Python` · `TypeScript` · `Kafka (KRaft)` · `PostgreSQL + pgvector` · `FastAPI` · `Celery` · `Next.js 14` · `Kubernetes` · `Helm` · `KEDA`

> **Polyglot ingestion pipeline:** Go gRPC + HTTP gateway → Kafka (3 consumer groups co-partitioned by run_id) → PostgreSQL / pgvector / evaluator workers  
> **8 rule-based evaluators** + LLM-as-judge (gpt-4o-mini) scoring every run on groundedness, safety, tool-call correctness, retry loops, and evidence  
> **Semantic failure search** via `text-embedding-3-small` + IVFFlat cosine index — find similar past failures for any run  
> **Replay & regression** — re-run with prompt / guardrail overrides, get before/after score deltas  
> **Kubernetes-native** — Helm chart with KEDA autoscaling on Kafka consumer group lag (2 → 20 pods)

---

#### 🔍 [ProductRank — Evaluation-First IR & Ranking Platform](https://github.com/Aditya-Pimpalkar/ProductRank)

**Multi-stage retrieval and ranking platform** built from scratch with rigorous IR evaluation. BM25 + dense retrieval + Reciprocal Rank Fusion + cross-encoder reranking, measured with `pytrec_eval` against MS MARCO and FiQA benchmarks with paired t-tests and bootstrap confidence intervals.

`Python` · `FastAPI` · `ParadeDB (Postgres 17 + pg_search + pgvector)` · `OpenAI Embeddings` · `Cross-Encoder Reranking` · `Next.js` · `Redis`

> **Discovered a domain-transfer regression:** reranking significantly improved MS MARCO NDCG@10 (p=9e-30) but *degraded* FiQA NDCG@10 (0.448 → 0.375), confirmed via controlled diagnostic  
> **Honest evaluation methodology** — MS MARCO absolute numbers documented with inflation-by-construction caveats; FiQA reported as leaderboard-comparable  
> **Live analytics dashboard** with per-variant NDCG/MRR/MAP, on-demand A/B experiments, and interactive query playground

---

#### 🤖 [MARS — Multi-Agent Research Synthesizer](https://github.com/Aditya-Pimpalkar/mars)

**Five-agent operational research system** built for the Elasticsearch Agent Builder Hackathon 2026. Five specialized agents (Planner, ES|QL Verifier, Internal Retrieval, Web Scout, Reviewer) coordinate through a shared Claim Ledger with structured evidence, confidence scores, and full provenance.

`Python` · `FastAPI` · `LangGraph` · `Elasticsearch` · `ES|QL` · `Kibana Agent Builder`

> Reduces 30–60 min manual incident investigations to ~3 min · Three live-switchable data-source modes · Two planted contradictions detected and resolved on every run · ES|QL Verifier catches query failures at write-time rather than runtime

---

#### 🎤 [Mirror — Real-Time Voice AI](https://github.com/Aditya-Pimpalkar/mirror-app)

**Real-time bidirectional voice AI** with four distinct AI personas (recruiter, first date, competitor, journalist) simulating how different people perceive the user through live voice conversation. Powered by the Gemini Live API with evidence-based belief scoring and multi-session memory.

`Node.js` · `Next.js` · `Gemini Live API` · `Google Cloud Run` · `Firestore` · `WebSocket`

> Four microservices on Cloud Run · PCM16 audio streaming at 16 kHz input / 24 kHz output · Custom mic gain control to prevent echo · Six scripted scenarios including FAANG interview and salary negotiation

---

#### 🧠 [Finley — AI Financial Advisor](https://github.com/Aditya-Pimpalkar/Finley)

**Production AI chatbot** with a fine-tuned GPT-4o-mini backbone, 6-node LangGraph workflow, dual memory architecture, and a **58-attack adversarial security framework** covering prompt injection, extended validation, and multi-turn erosion attacks.

`Python` · `Flask` · `LangChain` · `LangGraph` · `OpenAI Fine-tuning` · `Azure Prompt Flow`

> 92–95% recommendation consistency · 100% attack detection at <2% false positives · Two-layer security architecture (fast regex + LLM semantic analysis) · Dual memory reduces token usage 60% while supporting long-horizon conversations

---

#### ☁️ [CloudHealth — AWS Web Service Monitoring](https://github.com/Aditya-Pimpalkar/CloudHealth)

**Cloud-native application** built during AWS SAA-C03 preparation — three architectural variants (serverless, traditional, hybrid) of the same product, all deployed with Terraform IaC. Full CI/CD, auto-scaling EC2, and CloudWatch observability.

`Node.js` · `Express.js` · `PostgreSQL` · `AWS` · `Terraform` · `Docker` · `GitHub Actions`

> Auto-scaling group (min 3, max 5) · Multi-AZ VPC with public/private subnets · Custom StatsD metrics via CloudWatch · Cost-optimized deployment patterns compared side-by-side

---

### 💼 Experience

**Graduate Teaching Assistant** — Northeastern University · *Jan 2026 – May 2026*  
INFO 7375: Prompt Engineering for Generative AI. Mentored 30+ graduate students building production LLM systems with LangChain, RAG pipelines, evaluation frameworks (LangSmith, Azure Prompt Flow), and adversarial security testing.

**Software Engineer (Associate)** — Cognizant Technology Solutions · *Jul 2021 – Aug 2024*  
Built and maintained 8+ Spring Boot microservices serving 10,000+ daily users. Reduced backend latency 30% via Redis caching and connection pooling; improved P95 query time 40% through composite indexing and N+1 elimination. Raised automated test coverage to 90%+ using JUnit and Mockito. Maintained 99%+ uptime through proactive monitoring and structured incident response.

---

### 🛠️ Tech Stack

**Languages**  
Java · Python · Go · JavaScript · TypeScript · SQL

**Backend & Frameworks**  
Spring Boot · FastAPI · Flask · Node.js · Express.js · gRPC · REST APIs · Microservices

**AI / LLM Systems**  
LangChain · LangGraph · OpenAI Fine-tuning · RAG · Multi-Agent Systems · LLM Evaluation · Adversarial Security Testing · LangSmith · Azure Prompt Flow

**Data & Infrastructure**  
Kafka (KRaft mode) · PostgreSQL · MongoDB · MySQL · Elasticsearch · Redis · pgvector · ParadeDB · Celery

**Cloud & Platform**  
AWS (EC2, RDS, S3, VPC, Lambda, Bedrock, CloudWatch, IAM) · Google Cloud Run · Kubernetes · Helm · KEDA · Terraform · Docker · GitHub Actions · CI/CD

**Certifications**  
[AWS Certified Solutions Architect – Associate (SAA-C03)](https://www.credly.com/users/aditya-pimpalkar)

---

### 📫 Let's Connect

📧 **[pimpalkar.aditya123@gmail.com](mailto:pimpalkar.aditya123@gmail.com)**  
🔗 **[LinkedIn](https://linkedin.com/in/aditya-pimpalkar-905b4417b)** — active with regular technical content  
🎓 **Open to full-time roles starting Summer 2026** — Software Engineer, Backend, AI Engineer, Platform/Infrastructure Engineer
