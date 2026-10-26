# AI Certification Field Guide 2026
## A practical, evidence-based preparation workbook for software engineers

**Version:** 1.0 · **Reviewed:** 26 October 2026 · **Price:** Free · **Format:** Independent guide, not affiliated with AWS, Microsoft, or Google.

> **Promise:** By the end, you will know which exam fits your goals, have a domain-by-domain study plan, complete one substantial engineering project, and have an evidence-based way to decide whether to schedule the exam. This guide does **not** promise a pass in 30 days.

## Start here: choose the right exam

| If you want to… | Choose | Experience fit | Avoid if… |
|---|---|---|---|
| Build production generative AI systems on AWS | **AWS Certified Generative AI Developer – Professional (AIP-C01)** | Experienced developer, comfortable with AWS, deployment, IAM, and GenAI implementation | You have never shipped an application or used AWS |
| Build agents, RAG, and multimodal AI on Azure | **Microsoft Azure AI Apps and Agents Developer Associate (AI-103)** | Python/AI app developer with working Azure familiarity | You only want agent topics and plan to skip vision, text, and extraction |
| Design, train, operate, and monitor ML systems on GCP | **Google Cloud Professional Machine Learning Engineer** | ML/MLOps engineer with production cloud experience | You want only LLM prompt engineering or chatbot development |

**Rule of thumb:** Prefer the stack used by your target employer. The certification is supporting evidence, not a replacement for experience.

**Official pages**
- AWS: https://aws.amazon.com/certification/certified-generative-ai-developer-professional/
- Microsoft: https://learn.microsoft.com/en-us/credentials/certifications/exams/ai-103/
- Google: https://cloud.google.com/learn/certification/machine-learning-engineer

**Exam snapshot (verify before booking):** AWS AIP-C01: 180 minutes, 75 questions, US$300. Microsoft AI-103: 120 minutes, cost depends on region. Google Professional ML Engineer: 2 hours, 50–60 questions, US$200 before applicable taxes. Exam formats, prices, objectives, and access to assessments may change.

---

## How to use this kit

1. Download the latest **official exam guide** for your chosen track; mark its revision date.
2. Fill out the **baseline scorecard** below *before* watching tutorials.
3. Study the weakest high-weight objectives first; complete the hands-on verification tasks.
4. Build the track project, record tests and metrics, and publish a sanitized portfolio repo.
5. Use official practice assessments where available, write down why each wrong answer was wrong, and close gaps.
6. Only book once you satisfy the **readiness gate**—not merely because 30 days have passed.

### Baseline scorecard (copy into your notes)

| Objective | Exam weight / importance | Knowledge (0–3) | Hands-on evidence | Next step |
|---|---|---|---|---|
| Domain A | From official blueprint | | | |
| Domain B | From official blueprint | | | |
| Domain C | From official blueprint | | | |
| Domain D | From official blueprint | | | |
| Domain E (if any) | From official blueprint | | | |

**Scoring rubric:** 0 = unfamiliar; 1 = can recognize terms; 2 = can explain design/tradeoffs; 3 = can build, secure, troubleshoot, and explain it without step-by-step instructions. Focus on progressing to 2–3 for all objectives; this is **our learning rubric**, not the vendors' scoring method.

---

# Track A — AWS Certified Generative AI Developer – Professional (AIP-C01)

**Who it's for:** Developers moving past demos into enterprise GenAI architecture and deployment. AWS recommends 2+ years building production applications and 1 year of hands-on GenAI implementation.

**Authoritative blueprint:** https://docs.aws.amazon.com/aws-certification/latest/ai-professional-01/ai-professional-01.html

### Official domain coverage

| Exam domain | Weight | What you should be able to demonstrate |
|---|---:|---|
| Foundation model integration, data management, compliance | **31%** | Choose model/inference patterns, ingest and govern data, design grounding and integration |
| Implementation and integration | **26%** | Implement model-backed services, RAG/agents, APIs, workflows, and infrastructure |
| AI safety, security, governance | **20%** | Identity/permissions, secret management, guardrails, least privilege, data controls |
| Operational efficiency and optimization | **12%** | Monitor latency, tokens, cost, reliability and performance; optimize deployment |
| Testing, validation, troubleshooting | **11%** | Build representative evaluations, diagnose retrieval/model/application failures |

The weights above come from the AWS AIP-C01 guide. Review the official detailed task statements, not only this summary.

### Study sequence and lab gates

**Phase A1 — Architecture and data (31%)**
- Explain when to use RAG, fine-tuning, prompt-based generation, or non-LLM software.
- Compare chunking, embeddings, vector search and metadata filters; evaluate retrieval recall on an annotated set.
- Draw your request flow: API → auth → retrieval → prompt assembly → model → citation formatting → response.
- **Evidence:** Architecture diagram, 15 labeled test questions, retrieval comparison table.

**Phase A2 — Implementation (26%)**
- Implement a backend using Amazon Bedrock and an appropriate data store; keep infrastructure reproducible.
- Include timeouts, backoff, idempotency where relevant, and clear separation of retrieval versus answer generation.
- **Evidence:** Working API, deployment steps, automated smoke test, infrastructure instructions.

**Phase A3 — Security and safety (20%)**
- Threat-model prompt injection in retrieved documents, sensitive-data leakage, excessive permissions, and unsafe tool calls.
- Add access controls, scoped IAM roles, secret handling and explicit approval for consequential actions.
- **Evidence:** Threat model with mitigations, five adversarial test cases and test outcomes.

**Phase A4 — Operations and tests (23% combined)**
- Collect request-level latency, token usage, approximate cost and failure reasons.
- Build an evaluation set: answer accuracy/grounding, retrieval relevance, refusal behavior and robustness.
- **Evidence:** Evaluation report, regression-test script, cost/latency dashboard or exported table.

### AWS capstone: source-grounded document assistant

**Scenario:** An internal knowledge assistant for a small company's publicly shareable policy documents.

**Minimum acceptance criteria:**
- At least 30 source documents (synthetic or public), with document IDs and update timestamps.
- At least 40 manually labeled evaluation questions spanning answerable, ambiguous, and unanswerable cases.
- Answers include source citations; unsupported claims are flagged or handled conservatively.
- Auth boundary prevents one simulated user group from querying restricted documents.
- Automated tests include prompt injection embedded in a retrieved document.
- Logs capture latency, token counts where supported, and cost estimates; no secrets or private data logged.
- README explains architecture, system limitations, setup, teardown, and tradeoffs.

**Official practice path:** use AWS Skill Builder's exam prep plan, official question set, and official practice exam (availability/pricing may vary).

**Supplementary GitHub (not an exam guide):** https://github.com/aws-samples/generative-ai-use-cases

---

# Track B — Microsoft Azure AI Apps and Agents Developer Associate (AI-103)

**Who it's for:** Python developers who build, manage and deploy AI apps and agents using Microsoft Foundry and related Azure services.

**Authoritative blueprint:** https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103

### Official domain coverage (skills measured as of April 16, 2026)

| Exam domain | Weight | Lab focus |
|---|---:|---|
| Plan and manage an Azure AI solution | **25–30%** | Deployment, selection, quotas, security, monitoring, responsible AI |
| Implement generative AI and agentic solutions | **30–35%** | RAG, tool calling, agent orchestration, evaluations, observability |
| Implement computer vision solutions | **10–15%** | Image/video workflows, vision understanding, multimodal safety |
| Implement text analysis solutions | **10–15%** | Structured extraction, entity/sentiment tasks, translation, speech |
| Implement information extraction solutions | **10–15%** | Search, OCR, indexing, document understanding and grounding |

**Important:** This is *not* an agents-only exam. The latter three domains collectively represent a substantial share of the blueprint.

### Study sequence and lab gates

**Phase B1 — Platform planning (25–30%)**
- Choose appropriate model, index, search, identity, deployment and monitoring methods for a given scenario.
- Test authentication and authorization paths using least privilege.
- **Evidence:** Service selection decision record, budget/quotas note, secure deployment diagram.

**Phase B2 — RAG and agents (30–35%)**
- Implement a Foundry-backed LLM application with citations, tool schemas and a human-approval step.
- Design a multi-step workflow and explain where an agent adds value vs deterministic orchestration.
- Evaluate tool-call success, grounding quality and policy failures.
- **Evidence:** Tool-call traces, annotated evaluation data and reproducible agent demo.

**Phase B3 — Vision, language and extraction (remaining objectives)**
- Analyze an image and explain how visual evidence was used.
- Produce structured extraction from text and a sample document; compare outputs against a manually labeled reference.
- Prototype a speech/text or translation flow appropriate to the current published objectives.
- **Evidence:** One notebook or test per modality with failure analysis.

### Azure capstone: customer-support triage agent

**Scenario:** An AI assistant triages synthetic support tickets, searches a help center, extracts details from attached sample documents, and proposes a response.

**Minimum acceptance criteria:**
- Retrieval with citations; tool calling with explicit schema validation.
- Human approval before refund, account change, or any external side effect.
- At least 40 annotated cases, including tool errors, malicious instructions, conflicting documents and out-of-scope tickets.
- At least one image/document extraction path and one language analysis path.
- Tracing of tool calls, failure categories and response latency.
- Least-privilege permissions and documented cloud cleanup.

**Official prep:** Microsoft Learn study guide and AI Skills Navigator practice assessment (sign-in required). Microsoft states the passing exam score is 700 on its scaled scoring system; it is not necessarily a raw 70% correct threshold.

**Free complementary GitHub curriculum:** https://github.com/microsoft/generative-ai-for-beginners (great for foundations; **not** a complete AI-103 exam course).

---

# Track C — Google Cloud Professional Machine Learning Engineer

**Who it's for:** Engineers designing, building, productionizing, orchestrating and monitoring ML solutions in Google Cloud. Google recommends 3+ years of industry experience, including at least 1 year with Google Cloud.

**Authoritative certification page:** https://cloud.google.com/learn/certification/machine-learning-engineer

**Exam guide:** https://cloud.google.com/learn/certification/guides/machine-learning-engineer

**Coverage to track against the live exam guide:** solution architecture, data preparation/processing, model development, ML pipelines and automation, and monitoring/optimization. The online guide can change; **copy the current sections and weights directly from Google rather than relying on cached percentages or an old blog**.

### Study sequence and lab gates

**Phase C1 — Data and modeling**
- Choose baseline models and metrics suitable to a business objective.
- Detect target leakage, label problems, class imbalance and invalid train/validation splits.
- Compare managed model APIs, BigQuery ML and custom training approaches for cost/complexity.
- **Evidence:** Dataset card, reproducible training pipeline, evaluation report.

**Phase C2 — Infrastructure and operationalization**
- Build a repeatable training/deployment pipeline; version data and model artifacts.
- Define validation gates before deployment and rollback conditions.
- **Evidence:** Pipeline definition, logs, model registry/version notes and deployment playbook.

**Phase C3 — Monitoring and troubleshooting**
- Design performance, drift, data quality and serving reliability monitoring.
- Run a simulated drift or bad-data incident and document detection/response.
- **Evidence:** Monitoring report and incident postmortem.

**Phase C4 — Generative AI topics (as applicable to current guide)**
- Demonstrate grounding, evaluation and responsible AI in a practical model-backed workflow.
- **Evidence:** Small evaluated GenAI example with clear limitations.

### Google capstone: reproducible end-to-end ML service

**Scenario:** Predict synthetic customer churn or support-ticket escalation risk.

**Minimum acceptance criteria:**
- Dataset with documented schema, splits and leakage check.
- Simple baseline and improved model compared on appropriate metrics.
- Automated pipeline from preparation through evaluation and deployment.
- Endpoint or batch prediction workflow with error handling.
- Simulated distribution shift and retraining/rollback decision.
- Explicit IAM, cost controls, cleanup instructions, and reproducibility notes.

**GitHub examples (supplementary, not a full ML certification course):** https://github.com/GoogleCloudPlatform/generative-ai

---

# 30-day structured preparation sprint

This is a **starter sprint** for experienced engineers, not a universal guarantee of exam readiness. Target ~6–10 hours per week, adjust upward if your baseline indicates significant gaps, and avoid booking until the readiness gate is met.

| Days | Focus | Deliverable |
|---|---|---|
| **1–3** | Read current official blueprint, record weights and baseline scores; review exam logistics | Filled baseline table, target exam, scope document |
| **4–7** | Study highest-weight domain; hands-on starter lab | Working small example + 10 self-written flashcards |
| **8–11** | Study second domain; build core services | Core service with tests and architecture diagram |
| **12–15** | Study security, governance, responsible AI | Threat model and permissions review |
| **16–19** | Complete remaining objectives, including less fashionable topics | Coverage matrix with no omitted domains |
| **20–24** | Build capstone, collect metrics, test adverse cases | Reproducible project + evaluation dataset |
| **25–27** | Official/reputable original practice materials; analyze errors | Error log tagged to exam objectives |
| **28–30** | Target weakest objectives, explain design choices aloud, decide readiness | Final scorecard and go/no-go decision |

### Study-session template (60–90 minutes)

- 10 min: recall yesterday's material *without notes*.
- 20–25 min: official documentation or guided module.
- 30–40 min: implement or troubleshoot one small task.
- 10–15 min: write a decision record and one exam-style scenario in your own words.

### Weekly milestone checklist

- [ ] Every topic studied maps to an official exam objective.
- [ ] I can justify a service selection, not just memorize its product name.
- [ ] I have produced code, logs, diagrams or tests as proof of learning.
- [ ] I can explain security, operations and failure modes.
- [ ] I recorded incorrect assumptions and how I corrected them.

---

# Exam readiness: don't rely on a single practice score

This is a **recommended decision framework**, not an official vendor pass rule:

1. **Blueprint coverage:** At least a score of 2 (can explain decisions) on *every* official domain, and a score of 3 (can implement/troubleshoot) on the dominant implementation domains.
2. **Evidence:** Reproduce one end-to-end workflow without following a step-by-step lab, and demonstrate how it fails safely.
3. **Practice:** Complete official assessments where available. On repeated *fresh, legitimate* questions, aim for strong performance and inspect all explanations. Avoid using memorized question banks as evidence.
4. **Scenario reasoning:** Explain why three plausible alternatives are inferior for cost, operational risk, security, latency or maintainability.
5. **Timing:** Practice allocating time per question, marking uncertain items and reviewing them.
6. **Administrative:** Confirm current exam version, identification requirements, scheduling details and retake policies on the official site.

### Mistake log template

| Date | Objective | Question/scenario summary (in your words) | Wrong assumption | Correct principle | Retest date |
|---|---|---|---|---|---|
| | | | | | |

**Never redistribute live exam questions or use braindumps.** Practice sites are not interchangeable with official exam resources.

---

# Publishable portfolio repo checklist

```text
my-ai-certification-project/
├── README.md                   # purpose, setup, architecture, limitations
├── docs/
│   ├── architecture.md          # design choices and tradeoffs
│   ├── threat-model.md          # risks and mitigations
│   └── cost-and-cleanup.md      # cloud costs and teardown steps
├── src/                         # implementation
├── tests/                       # unit, integration and adversarial cases
├── evaluations/                 # small synthetic/public datasets, metrics
├── infra/                       # reproducible deployment templates
└── .env.example                 # placeholder only; never real credentials
```

**Prove outcomes, not just code:** publish a table of baseline vs improved metrics, describe failed experiments, and explain the biggest design tradeoff. A simple project with evaluation, monitoring and security is more convincing than a complex demo with none of them.

### Responsible cost and security practices
- Use synthetic or clearly licensed public data; don't upload company documents or private customer information.
- Enable budgets, quotas and alerts, but remember alerts aren't always hard spending caps.
- Use least-privilege identities and short-lived credentials; never commit tokens or keys.
- Shut down compute, managed endpoints, storage and other billable resources after experiments.
- Test prompt-injection and tool-use risks before giving an agent external permissions.

---

# Resource directory: official first, GitHub second

| Track | Official study material | GitHub for hands-on learning | Status |
|---|---|---|---|
| AWS AIP-C01 | [Exam page](https://aws.amazon.com/certification/certified-generative-ai-developer-professional/) · [Detailed exam guide](https://docs.aws.amazon.com/aws-certification/latest/ai-professional-01/ai-professional-01.html) | [aws-samples/generative-ai-use-cases](https://github.com/aws-samples/generative-ai-use-cases) | AWS example code, *not* official practice questions |
| Microsoft AI-103 | [Official study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/ai-103) · [Exam page](https://learn.microsoft.com/en-us/credentials/certifications/exams/ai-103/) | [microsoft/generative-ai-for-beginners](https://github.com/microsoft/generative-ai-for-beginners) | Microsoft-led general curriculum, *not* exam-complete |
| Google PMLE | [Certification page](https://cloud.google.com/learn/certification/machine-learning-engineer) · [Guide](https://cloud.google.com/learn/certification/guides/machine-learning-engineer) | [GoogleCloudPlatform/generative-ai](https://github.com/GoogleCloudPlatform/generative-ai) | Google Cloud examples, *not* exam-complete |

## Three interview prompts to test real learning

**AWS:** “Your RAG assistant is accurate on test documents but makes unsourced claims when retrieval returns irrelevant results. Design an evaluation, fallback behavior, and monitoring strategy.”

**Azure:** “Your agent can call a refund API. What prevents a retrieved document from instructing the agent to issue an unauthorized refund? Include permission boundaries and human approval.”

**Google Cloud:** “Accuracy stays stable on the training set but production performance drops after a new data pipeline launch. How do you isolate training-serving skew, drift and schema errors, and decide on rollback?”

For each prompt, write a 1-page answer: architecture, security, alternatives, failure tests, observability, and cost.

---

## Final note

**Certification ≠ job offer.** Credentials can help with structured learning, recruiter keyword matches and demonstrating vendor-specific knowledge. Hiring still depends on software fundamentals, production experience, architecture judgment, communication, and evidence that you can build reliable systems.

**Disclaimer:** Vendor names and marks belong to their owners. This independent educational guide does not guarantee exam results. Official exam blueprints supersede all summaries here; check them immediately before studying and again before booking.