<div align="center">

# 🏥 Awesome Medical LLM & Agent Papers

**超棒的医学大模型 + 智能体论文精选集**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
![Papers](https://img.shields.io/badge/Papers-informational?style=flat-square)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-ff69b4?style=flat-square)

> 专注于 **医学大模型 · LLM 智能体 · 多智能体系统** 的高质量论文合集
> 覆盖临床决策 · 诊断推理 · 多专科协作 · 规划推理等核心方向

</div>

---

## 📌 目录

- [🗺️ 阅读路线图](#️-阅读路线图)
- [🧱 通用 Agent 地基必读（从经典中精选）](#-通用-agent-地基必读从经典中精选)
- [📖 综述论文](#-综述论文-surveys)
- [🧠 医学大模型](#-医学大模型-medical-llm)
- [🤖 医学单智能体](#-医学单智能体-medical-single-agent)
- [👥 医学多智能体](#-医学多智能体-medical-multi-agent)
- [🤝 如何贡献](#-如何贡献)


## 🗺️ 阅读路线图

> 推荐新人按以下顺序阅读，逐步建立完整知识体系

```
阶段零：先补通用 Agent 地基（2-3 天）
──────────────────────────────────────────────────────────
  0. 🧱 ReAct + Toolformer + Reflexion + Plan-and-Solve
     └─ 先掌握 Agent 的 4 个核心能力：推理-行动、工具调用、自反馈、规划

阶段一：了解全局（1-2 天）
──────────────────────────────────────────────────────────
  1. 📖 A Survey of LLMs for Healthcare（Kai He et al., 2023）
     └─ 最系统的综述，了解整个领域发展脉络

  2. 📖 LLMs in Healthcare and Medical Applications（PMC, 2025）
     └─ 最新进展全景，了解当前技术状态

阶段二：掌握基础模型（3-5 天）
──────────────────────────────────────────────────────────
  3. 🧠 Med-PaLM: Large Language Models Encode Clinical Knowledge
     └─ 医学 LLM 奠基之作，必读

  4. 🧠 Med-PaLM 2: Towards Expert-Level Medical QA
     └─ 理解医学 LLM 的能力演进方向

  5. 🧠 GPT-4 on Medical Challenge Problems（Microsoft）
     └─ 通用 LLM 在医疗中的能力边界

阶段三：理解单智能体（3-5 天）
──────────────────────────────────────────────────────────
  6. 🤖 A Survey of LLM-based Agents in Medicine: How Far from Baymax?
     └─ 医学 Agent 综述，快速了解全貌

  7. 🤖 Autonomous AI Agents for Clinical Decision Making in Oncology
     └─ 单 Agent 的经典实现，工具调用范式

  8. 🤖 Agent Hospital: A Simulacrum of Hospital
     └─ 自主进化型 Agent，训练新范式

阶段四：进入多智能体（5-7 天）
──────────────────────────────────────────────────────────
  9. 👥 MedAgents: LLMs as Collaborators（ACL 2024）
     └─ 多智能体医学推理的开山之作

 10. 👥 MDAgents: Adaptive Collaboration（NeurIPS 2024）
     └─ 目前最具影响力的医学多智能体框架

 11. 👥 MedAgentBoard: Benchmarking Multi-Agent
     └─ 客观评估多智能体系统，了解真实差距

深入研究（按方向自选）
──────────────────────────────────────────────────────────
  📖 更多综述  → 本页综述章节其余论文
  🧠 开源模型  → BioGPT · PMC-LLaMA · Meditron-70B
  🤖 可解释性  → CoD（诊断链）· AI-SCE 评估框架
  👥 前沿方向  → ColaCare · MMedAgent-RL · ClinicalAgents
```

---

## 🧱 通用 Agent 地基必读（从经典中精选）

> 你给的表里论文很多，这里只保留**医学方向最必要**的通用 Agent 基石。  
> 建议先读完这一组，再进入本仓库的医学 LLM/医学 Agent 论文。

### 1. ReAct: Synergizing Reasoning and Acting in Language Models

- **作者**：Shunyu Yao et al.（Google Research）
- **时间**：2022
- **链接**：[arXiv 2210.03629](https://arxiv.org/abs/2210.03629)
- **为什么必读**：Agent 最核心范式（Reason + Act）。后续医疗 Agent 的问诊、检索、工具调用流程基本都能映射到 ReAct 思路。

---

### 2. Toolformer: Language Models Can Teach Themselves to Use Tools

- **作者**：Timo Schick et al.（Meta FAIR）
- **时间**：2023
- **链接**：[arXiv 2302.04761](https://arxiv.org/abs/2302.04761)
- **为什么必读**：解释了模型如何学会「何时调用外部工具」，这是医疗场景接入检索、指南库、计算器、影像工具的基础。

---

### 3. Reflexion: Language Agents with Verbal Reinforcement Learning

- **作者**：Noah Shinn et al.
- **时间**：2023
- **链接**：[arXiv 2303.11366](https://arxiv.org/abs/2303.11366)
- **为什么必读**：自我反思与错误修正机制，能直接提升医疗任务里的可靠性与稳健性。

---

### 4. Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought Reasoning

- **作者**：Lei Wang et al.
- **时间**：2023
- **链接**：[arXiv 2305.04091](https://arxiv.org/abs/2305.04091)
- **为什么必读**：把复杂问题拆成计划再执行，对临床分步决策和差错控制非常实用。

---

### 5. Chain-of-Thought Prompting Elicits Reasoning in Large Language Models

- **作者**：Jason Wei et al.（Google Research）
- **时间**：2022
- **链接**：[arXiv 2201.11903](https://arxiv.org/abs/2201.11903)
- **为什么必读**：虽然不是 Agent 论文，但它定义了推理提示的基础，是理解 ReAct/Plan-and-Solve 的前置知识。

---

### 6. Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection

- **作者**：Akari Asai et al.
- **时间**：2024
- **链接**：[arXiv 2310.11511](https://arxiv.org/abs/2310.11511)
- **为什么必读**：把检索与自我批判结合，特别适合医疗场景里「减少幻觉 + 引用证据」的需求。

---

### 7. AgentBench: Evaluating LLMs as Agents

- **作者**：Xiao Liu et al.
- **时间**：2023
- **链接**：[arXiv 2308.03688](https://arxiv.org/abs/2308.03688)
- **为什么必读**：学习 Agent 评测方法学，避免只看单一准确率；对你后续看医学 Agent benchmark 很关键。

---

## 📖 综述论文 (Surveys)

> 全局视角了解领域进展，建议新人优先阅读

### 1. A Survey of Large Language Models for Healthcare: from Data, Technology, and Applications to Accountability and Ethics

- **作者**：Kai He et al.
- **时间**：2023.10（更新至 2025.01）
- **链接**：[arXiv 2310.05694](https://arxiv.org/abs/2310.05694)
- **简介**：系统梳理医疗 LLM 的发展路径，从传统预训练语言模型（PLMs）到 LLMs 的范式转变。重点讨论公平性、可问责性、透明度与伦理（FATE）四大核心障碍，并配套维护了开源数据集、方法和评测基准资源合集。

---

### 2. Large Language Models in Healthcare and Medical Applications: A Review

- **作者**：PMC 综述团队
- **时间**：2025
- **链接**：[PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12189880/)
- **简介**：全面综述 LLM 在医疗领域的基础技术、方法论、应用场景、评估框架与挑战。检索时间跨度 2015–2025 年，覆盖临床决策支持、医学教育、诊断和患者护理等核心方向，并系统讨论隐私、伦理部署和事实准确性等关键问题。

---

### 3. Advances in Large Language Models for Medicine

- **作者**：arXiv 团队
- **时间**：2025.09
- **链接**：[arXiv](https://arxiv.org/html/2509.18690v1)
- **简介**：系统回顾医学 LLM 的最新研究进展，创新性地将医学 LLM 按训练方法分为三类，将评估方法分为两类。分析临床决策支持、个性化治疗、药物研发、医学影像等广泛应用场景，并针对现有问题提出未来研究策略。

---

### 4. A Comprehensive Survey of Large Language Models and Multimodal Large Language Models in Medicine

- **作者**：Hanguang Xiao, Feizhong Zhou et al.
- **时间**：2024
- **链接**：[ScienceDirect](https://www.sciencedirect.com/science/article/abs/pii/S1566253524006663)
- **简介**：综述医学 LLM 和多模态 LLM（MLLM）的发展原理、应用场景、挑战与未来方向。系统梳理微调方法、评估策略和可用训练数据集，涵盖五大临床应用方向，旨在弥合先进技术与临床实践之间的鸿沟。

---

### 5. A Systematic Review of Large Language Model (LLM) Evaluations in Clinical Medicine

- **作者**：BMC Medical Informatics 团队
- **时间**：2025.03
- **链接**：[Springer](https://link.springer.com/article/10.1186/s12911-025-02954-4)
- **简介**：对 2019–2025 年间 735 篇文章进行系统综述，共评测 1534 个 LLM 实例。发现 2023 年研究数量暴增（160 篇），2024 年达到 557 篇，揭示临床 LLM 研究的指数级增长趋势。93.55% 的评测针对通用域 LLM，医学专用模型仅占 6.45%。

---

### 6. A Survey of Datasets in Medicine for Large Language Models

- **作者**：Zhang D, Xue X, Hu M et al.
- **时间**：2024.12
- **链接**：[OAE Publishing](https://www.oaepublish.com/articles/ir.2024.27)
- **简介**：系统梳理驱动医疗 LLM 的数据集资源，涵盖预训练、微调、评估三阶段的数据集特征及关键作用，填补了该领域系统性数据集综述的空白，为研究者选择合适数据集提供全面指引。

---

### 7. Large Language Models in Medical and Healthcare Fields: Applications, Advances, and Challenges

- **作者**：Springer Nature 团队
- **时间**：2024.09
- **链接**：[Springer](https://link.springer.com/article/10.1007/s10462-024-10921-0)
- **简介**：分析 175 篇相关文献，汇总 56 个实验数据集，覆盖医学问答、对话摘要、电子病历生成、科学研究、医学教育、临床决策支持等多个任务，梳理 GPT-4、LLaMA、MedPaLM 等主流模型的医疗应用进展。

---

## 🧠 医学大模型 (Medical LLM)

> 专为医疗领域设计或适配的大语言模型

### 1. Large Language Models Encode Clinical Knowledge (Med-PaLM)

- **作者**：Karan Singhal, Shekoofeh Azizi et al.（Google）
- **时间**：2023.08
- **期刊**：Nature
- **链接**：[Nature](https://www.nature.com/articles/s41586-023-06291-2)
- **简介**：提出 MultiMedQA 评估基准，整合 6 个现有医学问答数据集与 HealthSearchQA，推出 Med-PaLM（PaLM + 指令微调）。首次在 USMLE 风格题目上达到通过线（67.2%），确立了医学 LLM 评估的多维度框架（真实性、理解、推理、危害、偏见）。

---

### 2. Towards Expert-Level Medical Question Answering with Large Language Models (Med-PaLM 2)

- **作者**：Karan Singhal, Tao Tu, Juraj Gottweis et al.（Google）
- **时间**：2023.05 / 2025.01 正式发表
- **期刊**：Nature Medicine
- **链接**：[arXiv 2305.09617](https://arxiv.org/abs/2305.09617)
- **简介**：提出 Med-PaLM 2，结合更强的基础模型（PaLM 2）、医学域微调和集成精炼提示策略。在 MedQA 数据集上准确率比 Med-PaLM 提升 19%，在多个 USMLE 子任务上达到接近医生水平，是医学 LLM 的重要里程碑。

---

### 3. BioGPT: Generative Pre-trained Transformer for Biomedical Text Generation and Mining

- **作者**：Renqian Luo, Liai Sun et al.（Microsoft Research）
- **时间**：2022
- **期刊**：Briefings in Bioinformatics
- **链接**：[Paper](https://academic.oup.com/bib/article/23/6/bbac409/6713511)
- **简介**：在大规模生物医学文献上预训练的生成式语言模型 BioGPT，在 PubMedQA、BC5CDR、KD-DTI 等多项生物医学文本挖掘与问答基准上达到当时最优性能，开创了生物医学领域开放式文本生成方向。

---

### 4. PMC-LLaMA: Towards Building Open-source Language Models for Medicine

- **作者**：Chaoyi Wu et al.
- **时间**：2023
- **链接**：[arXiv 2304.14454](https://arxiv.org/abs/2304.14454)
- **简介**：在 480 万篇生物医学学术论文上对 LLaMA 进行微调，构建开源医学语言模型 PMC-LLaMA。显著提升生物医学领域问答准确性和专业概念理解能力，推动了开源医学 LLM 社区的发展。

---

### 5. ChatDoctor: A Medical Chat Model Fine-Tuned on LLaMA Model Using Medical Domain Knowledge

- **作者**：Yunxiang Li et al.
- **时间**：2023
- **链接**：[arXiv 2303.14070](https://arxiv.org/abs/2303.14070)
- **简介**：基于 LLaMA 模型，利用真实医患对话数据和医学数据库进行微调，构建具备自主信息检索机制的 ChatDoctor 医学问诊模型。面向患者咨询场景，展示了轻量级医学 LLM 的可行路径。

---

### 6. Capabilities of GPT-4 on Medical Challenge Problems

- **作者**：Harsha Nori, Nicholas King, Scott McKinney et al.（Microsoft）
- **时间**：2023
- **链接**：[arXiv 2303.13375](https://arxiv.org/abs/2303.13375)
- **简介**：系统评估 GPT-4 在 USMLE 等多项医学挑战题目上的能力，GPT-4 在 MedQA 上达到 93.1% 的准确率，大幅超越此前所有模型，展现了通用大模型在医疗领域的强大泛化能力。

---

### 7. Meditron-70B: Scaling Medical Pretraining for Large Language Models

- **作者**：Zeming Chen et al.（EPFL）
- **时间**：2023
- **链接**：[arXiv 2311.16079](https://arxiv.org/abs/2311.16079)
- **简介**：基于 Llama-2-70B，在精心筛选的医学语料（PubMed、临床指南等）上继续预训练，构建开源医学 LLM Meditron-70B。在多个医学基准上达到与 GPT-3.5 相当的性能，推动了高质量开源医学模型发展。

---

### 8. Evaluating Large Language Models as Agents in the Clinic

- **作者**：npj Digital Medicine 团队
- **时间**：2024
- **期刊**：npj Digital Medicine
- **链接**：[npj](https://www.nature.com/articles/s41746-024-01083-y)
- **简介**：提出"AI 结构化临床考试"（AI-SCE）评估框架，将 LLM 置于高仿真临床场景中进行能力测试，超越传统基准评估。讨论 LLM Agent 在开放对话、临床决策支持中的能力边界，并类比自动驾驶提出分级自主性概念。

---

## 🤖 医学单智能体 (Medical Single Agent)

> 单 LLM 驱动，集成工具调用、记忆、规划能力的医疗 Agent

### 1. Autonomous Artificial Intelligence Agents for Clinical Decision Making in Oncology

- **作者**：Dyke Ferber, Jakob Nikolas Kather et al.
- **时间**：2024.04
- **链接**：[arXiv 2404.04667](https://arxiv.org/abs/2404.04667)
- **简介**：将 LLM 作为中央推理引擎，自主协调和调用专科医疗 AI 工具（文本、放射影像、病理图像、基因组数据处理、文献检索等）。在多个肿瘤临床场景中验证：工具调用准确率 97%、结论正确率 93.6%，是医疗领域 LLM 自主 Agent 的概念验证里程碑。

---

### 2. Evaluating Large Language Models as Agents in the Clinic

- **作者**：npj Digital Medicine 团队
- **时间**：2024
- **期刊**：npj Digital Medicine
- **链接**：[npj](https://www.nature.com/articles/s41746-024-01083-y)
- **简介**：提出"AI 结构化临床考试"（AI-SCE）评估体系，将 LLM Agent 置于高仿真临床环境中测试，讨论其在开放对话、临床决策支持中的能力边界，并指出与自动驾驶类比的分级自主性问题。

---

### 3. Healthcare Agent: Eliciting the Power of Large Language Models for Medical Consultation

- **作者**：npj Artificial Intelligence 团队
- **时间**：2025.09
- **期刊**：npj Artificial Intelligence
- **链接**：[npj AI](https://www.nature.com/articles/s44387-025-00021-x)
- **简介**：提出包含对话规划、记忆存储和报告生成三大组件的医疗 Agent 框架，专门解决医疗问诊中问询质量低和安全性不足的问题。通过医学专家评估和 ChatGPT 自动评测两套体系验证了显著性能提升。

---

### 4. CoD: Towards an Interpretable Medical Agent Using Chain of Diagnosis

- **作者**：Jiuding Chen et al.
- **时间**：2024
- **链接**：[arXiv 2407.13301](https://arxiv.org/abs/2407.13301)
- **简介**：提出"诊断链"（Chain of Diagnosis）方法，模拟医生的诊断推理思维过程，将复杂诊断决策分解为可解释的多步推理链。在提升诊断准确性的同时，增强了临床决策的可解释性，为医疗 AI 透明化提供新思路。

---

### 5. Large Language Model Agents for Biomedicine: A Comprehensive Review

- **作者**：MDPI Information 团队
- **时间**：2025.10
- **期刊**：Information (MDPI)
- **链接**：[MDPI](https://www.mdpi.com/2078-2489/16/10/894)
- **简介**：系统综述生物医学 LLM Agent 的核心架构（推理、规划、记忆、工具调用）、方法论、真实案例（临床决策、研究自动化、患者模拟）和评估基准。系统分析幻觉、可解释性、工具可靠性、数据偏差和监管缺口等关键挑战，并讨论 Human-in-the-Loop 的必要性。

---

### 6. A Survey of LLM-based Agents in Medicine: How Far Are We from Baymax?

- **作者**：arXiv 团队
- **时间**：2025.02
- **链接**：[arXiv](https://arxiv.org/html/2502.11211v1)
- **简介**：分析 2022–2024 年间 60 篇医学 LLM Agent 论文（从 300 篇中筛选），梳理 Agent 架构（知识检索、任务规划、工具调用）与医疗应用场景，重点讨论幻觉管理、多模态整合和医学推理准确性等核心挑战。

---

### 7. Agent Hospital: A Simulacrum of Hospital with Evolvable Medical Agents

- **作者**：Junkai Li et al.
- **时间**：2024.05
- **链接**：[arXiv 2405.02957](https://arxiv.org/abs/2405.02957)
- **简介**：构建模拟医院环境，让医生 Agent 通过与虚拟患者的持续交互自主进化，解决了医疗 AI 训练数据稀缺的问题。展示了基于仿真自我进化的医疗 Agent 训练新范式，为数据生成和 Agent 能力提升提供新路径。

---

### 8. An Autonomous Agent for Auditing and Improving the Reliability of Clinical AI Models

- **作者**：arXiv 团队
- **时间**：2025
- **链接**：[arXiv](https://arxiv.org/html/2507.05755v1)
- **简介**：提出 ModelAuditor，一个 LLM 驱动的自主 Agent，通过对话形式完成临床 AI 模型的分布偏移审计、指标选择和失败分析。在普通 MacBook Pro 上可在 5–10 分钟内完成审计，成本不足 0.5 美元，大幅降低临床 AI 可靠性验证门槛。

---

## 👥 医学多智能体 (Medical Multi-Agent)

> 多个专科 Agent 协同推理，模拟真实医疗团队协作

### 1. MedAgents: Large Language Models as Collaborators for Zero-Shot Medical Reasoning

- **作者**：Xiangru Tang, Anni Zou, Zhuosheng Zhang et al.
- **时间**：2024（ACL 2024 Findings）
- **链接**：[arXiv 2311.10537](https://arxiv.org/abs/2311.10537)
- **简介**：开创性地将多个 LLM 以"零样本角色扮演"方式组建医学专家团队（如诊断师、药理学家），通过结构化讨论共同生成综合医学报告。在多个医学问答基准上显著优于单模型，是医学多智能体协作的奠基性工作。

---

### 2. MDAgents: An Adaptive Collaboration of LLMs for Medical Decision-Making

- **作者**：Yubin Kim, Chanwoo Park, Hyewon Jeong et al.（MIT Media Lab）
- **时间**：2024（NeurIPS 2024）
- **链接**：[arXiv 2404.15155](https://arxiv.org/abs/2404.15155) · [GitHub](https://github.com/mitmedialab/MDAgents)
- **简介**：提出自适应多智能体框架 MDAgents，根据医学任务复杂度自动分配协作结构（单个初级保健医生 → 多学科团队 → 综合护理团队）。在 10 个医学基准中的 7 个上取得最佳性能，最高提升 11.8%，是目前最具影响力的医学多智能体框架之一。

---

### 3. ColaCare: Enhancing Electronic Health Record Modeling Through LLM-Driven Multi-Agent Collaboration

- **作者**：Wang et al.
- **时间**：2025（WWW 2025）
- **链接**：[arXiv 2410.02551](https://arxiv.org/abs/2410.02551)
- **简介**：提出 ColaCare 框架，将 EHR（电子健康档案）建模与 LLM 推理通过多智能体协作有机融合。在 MIMIC-IV 死亡率预测任务上以 82.91% AUROC 超越单模型基线（DeepSeek-V3：76.86%），同时提升了 EHR 分析的可解释性。

---

### 4. A Survey of LLM-based Multi-Agent Systems in Medicine

- **作者**：TechRxiv 团队
- **时间**：2025.10
- **链接**：[TechRxiv](https://www.techrxiv.org/doi/full/10.36227/techrxiv.176089343.36199495/v1)
- **简介**：系统综述医学领域 LLM 多智能体系统，提出包含团队构成、医学知识增强、智能体交互三个维度的医学专属分类体系。指出人机协作、智能体画像设计和自适应进化系统等未来研究方向。

---

### 5. MedCoAct: Confidence-Aware Multi-Agent Collaboration for Complete Clinical Decision

- **作者**：arXiv 团队
- **时间**：2025.10
- **链接**：[arXiv 2510.10461](https://arxiv.org/html/2510.10461)
- **简介**：提出 MedCoAct 框架，通过医生 Agent 与药剂师 Agent 的置信度感知协作，将诊断推理与用药决策整合在统一系统中。同时发布 DrugCareQA 基准数据集，诊断准确率和用药推荐准确率均达到 67.58%，超越单智能体基线。

---

### 6. ClinicalAgents: Multi-Agent Orchestration for Clinical Decision Making with Dual-Memory

- **作者**：arXiv 团队
- **时间**：2025
- **链接**：[arXiv 2603.26182](https://arxiv.org/html/2603.26182)
- **简介**：提出具备双记忆机制的临床多智能体编排框架 ClinicalAgents，在 MedChain 基准（覆盖问诊→检查→影像→诊断→治疗五步临床工作流）上进行评测，将多智能体协调能力系统化地应用于完整临床流程。

---

### 7. MedAgentBoard: Benchmarking Multi-Agent Collaboration with Complex Medical Tasks

- **作者**：arXiv 团队
- **时间**：2025
- **链接**：[arXiv](https://arxiv.org/pdf/2505.12371)
- **简介**：提出 MedAgentBoard 基准，对 MedAgents、MDAgents、ColaCare 等主流医学多智能体方法进行系统评测。发现多智能体框架的效果主要取决于基础 LLM 能力（如 GPT-4o、DeepSeek-R1），而非协作策略本身，为该领域客观评估提供重要参考。

---

### 8. MMedAgent-RL: Optimizing Multi-Agent Collaboration for Multimodal Medical Reasoning

- **作者**：arXiv 团队
- **时间**：2025
- **链接**：[arXiv](https://arxiv.org/pdf/2506.00555)
- **简介**：将强化学习引入多智能体医学视觉问答，构建 MMedAgent-RL 框架，通过可训练的分诊 Agent 和专科 Agent 协同推理。在院内和跨域医学 VQA 数据集上分别超越 MedAgents (+23%)、MDAgents (+19%)、AFlow (+17%)。

---

### 9. TeamMedAgents: Enhancing Medical Decision-Making of LLMs Through Structured Teamwork

- **作者**：arXiv 团队
- **时间**：2025.08
- **链接**：[arXiv](https://arxiv.org/html/2508.08115)
- **简介**：在 MDAgents 基础上系统性地引入循证团队协作机制（领导力、相互监督、共享心智模型、团队导向、信任五要素），在 8 个医学基准中的 7 个上超越 MDAgents，MedQA 提升 +4.0%、PathVQA 提升 +10.7%。

---

## 🔄 更新日志

| 日期 | 内容 |
|------|------|
| 2025.04 | 🎉 初始版本，收录 32 篇核心论文，覆盖四大方向 |

---

## 🤝 如何贡献

欢迎提 PR 或 Issue 推荐新论文！

**收录标准（满足任意一条）：**
- ⭐ 顶会/顶刊（NeurIPS · ACL · Nature · npj · JMIR 等）
- ⭐ 高引 arXiv 预印本（Semantic Scholar 引用增长快）
- ⭐ 有开源代码且 GitHub Stars 较多

**添加新论文时，在对应章节末尾追加：**

```markdown
### N. 论文英文标题
- **作者**：第一作者 et al.（机构）
- **时间**：年份（会议/期刊）
- **链接**：[arXiv](https://arxiv.org/abs/xxxx.xxxxx)
- **简介**：1-2 句话概括方法、问题与核心结果。
```

同时更新顶部徽章中的论文数量和更新日志。

---

<div align="center">
  <sub>持续更新中 · 如果对你有帮助，欢迎点个 ⭐ Star</sub>
</div>
