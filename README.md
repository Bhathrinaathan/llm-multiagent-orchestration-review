# LLM Multi-Agent Orchestration — Critical Review

*Multi-Agent Orchestration: Centralize, Decentralize, or Learn?*

**A critical review of LLM-based multi-agent systems** — a group paper (Team Falcon, 6 authors) for the Artificial Intelligence module (CS7IS2), MSc Computer Science (Intelligent Systems), Trinity College Dublin, 2026.

📄 [`paper/Multi-Agent-Orchestration-Critical-Review.pdf`](paper/Multi-Agent-Orchestration-Critical-Review.pdf)

## What the paper does

Eighteen papers published between 2023 and 2026 were selected through a systematic search of Semantic Scholar, the ACL Anthology, arXiv and OpenReview, and compared along three dimensions: **control topology** (centralized ↔ decentralized ↔ learned), **communication pattern** (structured artifacts, natural-language chat, open debate, learned channels) and **agent composition**. Each paradigm was then assessed on **reliability, scalability and cost**.

Frameworks covered include MetaGPT, ChatDev, AutoGen, CAMEL, AgentVerse, Generative Agents, multi-agent debate (Du et al.), Mixture-of-Agents, DyLAN, GPTSwarm, evolving orchestration (Dang et al.), MAS-Orchestra and the failure taxonomy of Cemri et al., with ReAct as the single-agent baseline.

### Research questions

1. **RQ1** — Under what conditions does centralized orchestration outperform decentralized alternatives, and vice versa?
2. **RQ2** — How have orchestration architectures evolved, and where is the field heading?

### Main findings

- **Centralized pipelines win when the task decomposition is known, cost matters, or governance is required**; decentralized debate and ensembles win when reasoning diversity matters, the task structure is unknown, or adversarial error-checking is valuable.
- **Debate shows diminishing returns beyond four to six agents**, and communication cost scales from O(n) for pipelines to O(n²) for broadcast debate; learned topologies (GPTSwarm, DyLAN, RL-trained orchestrators) achieve sub-linear cost growth.
- **Orchestration configuration affects performance more than the choice of base LLM** (MAS-Orchestra), and multi-agent systems frequently underperform a single stronger model once cost is normalised.
- **The field is moving from hand-designed to learned orchestration**, in three phases: proof-of-concept (early 2023), engineered orchestration (mid-2023 to 2024), and empirical reckoning plus learned orchestration (2024 onward).
- Five open problems: architecture selection, cost-normalised evaluation, formal verification, communication standardisation, and scaling beyond small teams.

## My contribution

I wrote **Section 7, Scalability and Cost Behaviour**, and produced the two architecture figures:

- **7.1 Scaling with agent count and task complexity**, built primarily on Kim et al.'s scaling study: centralized architectures scale well for parallelisable work but bottleneck on sequential reasoning, while decentralized debate saturates at four to six agents.
- **7.2 Cost–performance trade-offs**: ChatDev's bounded token budgets versus the multiplicative cost of debate; whether multi-agent gains justify their cost against a single more capable model; and evidence from Dang et al.'s RL-trained orchestrator that learned meta-reasoning can pay for its own overhead.
- **Figure 1**, a five-panel comparison of representative orchestration architectures (pipeline, debate, learned orchestrator and others), and **Figure 2**, the centralized-to-decentralized spectrum positioning every reviewed framework.
- Papers I read and analysed: Kim et al. (Towards a Science of Scaling Agent Systems), Dang et al. (Multi-Agent Collaboration via Evolving Orchestration) and Liu et al. (DyLAN), including DyLAN's Agent Importance Score.

## Authors

Aparna Gayathri Narasimman, Bhathrinaathan Muthuramalingam Bhanumathi, Raghav Gupta, Sneha Meto, Sudesh Muralidharan and Yokesh Muthu Kathiravan. Each author took primary responsibility for specific sections and cross-reviewed the others' drafts.
