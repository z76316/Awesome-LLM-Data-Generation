# Awesome LLM Data Generation

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![arXiv](https://img.shields.io/badge/arXiv-2601.17717-b31b1b.svg)](https://arxiv.org/abs/2601.17717)

LLM-driven data generation is reshaping how we build training corpora, benchmarks, and evaluators across text, code, vision, and structured data. This list follows the taxonomy of *[The LLM Data Auditor: A Metric-oriented Survey on Quality and Trustworthiness in Evaluating Synthetic Data](https://arxiv.org/abs/2601.17717)* and highlights generation methods across six data modalities where LLM-driven synthetic data is advancing training, evaluation, and deployment.

<p align="center">
  <img src="assets/figures/Fig_Data_Auditor.png" width="100%" alt="Overview of the LLM Data Auditor Framework">
  <br>
  <em>Figure 1: Overview of the LLM Data Auditor Framework — four stages covering generation methods, quality metrics, trustworthy metrics, evaluation gap analysis, and data usage patterns.</em>
</p>

<p align="center">
  <img src="assets/figures/Survey_Figure_1.png" width="100%" alt="Overview of LLM-driven synthetic data generation across six modalities">
  <br>
  <em>Figure 2: Overview of LLM-driven synthetic data generation across six modalities — text, symbolic and logical, tabular, semi-structured, vision-language, and agent data.</em>
</p>

## Table of Contents

- [Text Data](#text-data)
  - [Source Corpus Control and Composition](#source-corpus-control-and-composition)
  - [Prompt-Driven Generation and Refinement](#prompt-driven-generation-and-refinement)
  - [Parameter-Efficient and Alignment-Based Control](#parameter-efficient-and-alignment-based-control)
  - [Inference-Time Steering and Verification](#inference-time-steering-and-verification)
- [Symbolic and Logical Data](#symbolic-and-logical-data)
  - [Heuristic Evolution Methods for Expanding Reasoning Tasks](#heuristic-evolution-methods-for-expanding-reasoning-tasks)
  - [Tool-Verified Generation Methods](#tool-verified-generation-methods)
  - [Trajectory Harvesting via Rewarded Rollouts and Distillation](#trajectory-harvesting-via-rewarded-rollouts-and-distillation)
  - [Preference-Curated Generation via LLM as a Judge](#preference-curated-generation-via-llm-as-a-judge)
- [Tabular Data](#tabular-data)
  - [Prompt-Based Tabular Synthesis](#prompt-based-tabular-synthesis)
  - [Fine-Tuning-Based Tabular Synthesis](#fine-tuning-based-tabular-synthesis)
  - [Hybrid Architectures](#hybrid-architectures)
- [Semi-structured Data](#semi-structured-data)
  - [Graph Data Generation](#graph-data-generation)
  - [JSON Data Generation](#json-data-generation)
  - [Log Data Generation](#log-data-generation)
- [Vision-Language Data](#vision-language-data)
  - [Image-Text Native Autoregressive Models](#image-text-native-autoregressive-models)
  - [Image-Text External Diffusion Control](#image-text-external-diffusion-control)
  - [Video-Text Native Spatiotemporal Models](#video-text-native-spatiotemporal-models)
  - [Video-Text Planner-based Diffusion](#video-text-planner-based-diffusion)
- [Agent Data](#agent-data)
  - [Environment & Task Data](#environment--task-data)
  - [Control & Decision Data](#control--decision-data)
  - [Perception & Telemetry Data](#perception--telemetry-data)
- [Open Challenges and Future Directions](#open-challenges-and-future-directions)

## Text Data

LLM-generated instructions, dialogues, and evaluations that power instruction-tuning and benchmarking.

### Source Corpus Control and Composition

<ul>
<li><i><b>RedPajama-V2</b></i> — Web text corpus with quality-related metadata for customizable selection and mixture design.
  <a href="https://arxiv.org/abs/2411.12372" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.11-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/togethercomputer/RedPajama-Data" target="_blank"><img src="https://img.shields.io/github/stars/togethercomputer/RedPajama-Data.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>FineWeb</b></i> — Modern curation pipeline with normalization, deduplication, and document-level filtering for high-quality web text.
  <a href="https://arxiv.org/abs/2406.17557" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.06-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>FineWeb2</b></i> — Enhanced pipeline implementing transparent mixture design and quality signal processing across domains.
  <a href="https://arxiv.org/abs/2506.20920" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.06-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>Dolma</b></i> — Toolkit enabling reproducible data mixture adjustment across domains without requiring recrawling.
  <a href="https://arxiv.org/abs/2402.00159" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.02-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Prompt-Driven Generation and Refinement

<ul>
<li><i><b>Self-Instruct: Aligning Language Models with Self Generated Instructions</b></i> — Seeded prompting to grow diverse instruction–response pairs from model internal knowledge.
  <a href="https://arxiv.org/abs/2212.10560" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.12-red" alt="arXiv Badge"></a>
  <a href="https://github.com/yizhongw/self-instruct" target="_blank"><img src="https://img.shields.io/github/stars/yizhongw/self-instruct.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>WizardLM / Evol-Instruct</b></i> — Evolutionary mutation operators systematically rewriting instructions for increased complexity.
  <a href="https://arxiv.org/abs/2304.12244" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.04-red" alt="arXiv Badge"></a>
  <a href="https://github.com/nlpxucan/WizardLM" target="_blank"><img src="https://img.shields.io/github/stars/nlpxucan/WizardLM.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>UltraFeedback</b></i> — Pipeline evaluating outputs via auxiliary LLM judge across helpfulness and honesty criteria.
  <a href="https://arxiv.org/abs/2310.01377" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.10-red" alt="arXiv Badge"></a>
</li>
</ul>

### Parameter-Efficient and Alignment-Based Control

<ul>
<li><i><b>SPIN (Self-Play Fine-Tuning)</b></i> — Iterative self-play mechanism contrasting generated responses against human demonstrations.
  <a href="https://arxiv.org/abs/2401.01335" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.01-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/uclaml/SPIN" target="_blank"><img src="https://img.shields.io/github/stars/uclaml/SPIN.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>SimPO (Simple Preference Optimization)</b></i> — Reference-free objective eliminating memory-heavy reference model for direct instruction alignment.
  <a href="https://arxiv.org/abs/2405.14734" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.05-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/princeton-nlp/SimPO" target="_blank"><img src="https://img.shields.io/github/stars/princeton-nlp/SimPO.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>ORPO (Odds Ratio Preference Optimization)</b></i> — Method mitigating length bias without requiring separate reward modeling.
  <a href="https://arxiv.org/abs/2403.07691" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.03-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>GRPO (Group Relative Policy Optimization)</b></i> — Normalizes rewards across group outputs rather than using critic models for efficient optimization.
  <a href="https://arxiv.org/abs/2402.03300" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.02-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Inference-Time Steering and Verification

<ul>
<li><i><b>Nucleus (Top-p) Sampling</b></i> — Stochastic decoding balancing diversity and plausibility via dynamic vocabulary truncation.
  <a href="https://arxiv.org/abs/1904.09751" target="_blank"><img src="https://img.shields.io/badge/arXiv-2019.04-red" alt="arXiv Badge"></a>
</li>
<li><i><b>Diverse Beam Search</b></i> — Diversity-promoting penalties preventing redundancy in beam search outputs.
  <a href="https://arxiv.org/abs/1610.02424" target="_blank"><img src="https://img.shields.io/badge/arXiv-2016.10-red" alt="arXiv Badge"></a>
</li>
<li><i><b>JAM (Latent Activation Editing)</b></i> — Latent space interventions adjusting attributes like sentiment and safety via activation vectors.
  <a href="https://arxiv.org/abs/2502.20684" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.02-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>Chain-of-Verification (CoVe)</b></i> — Post-hoc verification where models cross-check own outputs for reliability filtering.
  <a href="https://arxiv.org/abs/2309.11495" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
</li>
<li><i><b>RARR (Retrofit Attribution using Research and Revision)</b></i> — Framework revising drafts via retrieved evidence comparison for hallucination mitigation.
  <a href="https://arxiv.org/abs/2210.08726" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.10-red" alt="arXiv Badge"></a>
</li>
<li><i><b>SelfCheckGPT</b></i> — Consistency sampling detecting likely hallucinated content via multiple generations.
  <a href="https://arxiv.org/abs/2303.08896" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.03-red" alt="arXiv Badge"></a>
</li>
</ul>

## Symbolic and Logical Data

Math, program synthesis, and formal reasoning datasets crafted or expanded by LLMs, often paired with verifier loops.

### Heuristic Evolution Methods for Expanding Reasoning Tasks

<ul>
<li><i><b>WizardMath</b></i> — Evol-Instruct applied to math with reinforcement learning from evolution feedback to strengthen step-by-step reasoning.
  <a href="https://arxiv.org/abs/2308.09583" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.08-red" alt="arXiv Badge"></a>
  <a href="https://github.com/nlpxucan/WizardLM" target="_blank"><img src="https://img.shields.io/github/stars/nlpxucan/WizardLM.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>MetaMathQA</b></i> — Scales mathematics corpora by diversifying questions, answers, and reasoning paths via GPT-4 rewrites.
  <a href="https://arxiv.org/abs/2309.12284" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
  <a href="https://github.com/meta-math/MetaMath" target="_blank"><img src="https://img.shields.io/github/stars/meta-math/MetaMath.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>WizardCoder</b></i> — Adapts instruction evolution to coding tasks by generating progressively harder instructions from simpler seeds.
  <a href="https://arxiv.org/abs/2306.08568" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.06-red" alt="arXiv Badge"></a>
  <a href="https://github.com/nlpxucan/WizardLM" target="_blank"><img src="https://img.shields.io/github/stars/nlpxucan/WizardLM.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Tool-Verified Generation Methods

<ul>
<li><i><b>OpenMathInstruct-1</b></i> — Large-scale math problem–solution pairs synthesized with code interpreter verification for consistency.
  <a href="https://arxiv.org/abs/2402.10176" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.02-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>OpenCodeInstruct</b></i> — Code instruction tuning corpora with execution feedback and unit test signals as acceptance criteria.
  <a href="https://arxiv.org/abs/2504.04030" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.04-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>ProofWriter</b></i> — Instances with validity grounded in formal rules enabling deterministic checking of entailment and proof steps.
  <a href="https://arxiv.org/abs/2012.13048" target="_blank"><img src="https://img.shields.io/badge/arXiv-2020.12-red" alt="arXiv Badge"></a>
</li>
<li><i><b>SynLogic</b></i> — Diverse logical tasks whose correctness can be verified by simple rule-based checkers.
  <a href="https://arxiv.org/abs/2505.19641" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.05-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>ALT / FLD</b></i> — Formal logic deduction dataset enabling deterministic verification of symbolic reasoning steps.
  <a href="https://arxiv.org/abs/2411.12498" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.11-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Trajectory Harvesting via Rewarded Rollouts and Distillation

<ul>
<li><i><b>DeepSeek R1</b></i> — Rule-based and verifiable outcome rewards providing precise feedback for mathematics and coding domains.
  <a href="https://arxiv.org/abs/2501.12948" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.01-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/deepseek-ai/DeepSeek-R1" target="_blank"><img src="https://img.shields.io/github/stars/deepseek-ai/DeepSeek-R1.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Preference-Curated Generation via LLM as a Judge

<ul>
<li><i><b>STaR (Self-Taught Reasoner)</b></i> — Generate-and-filter reasoning loops where correctness serves as the acceptance signal for rationale curation.
  <a href="https://arxiv.org/abs/2203.14465" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.03-red" alt="arXiv Badge"></a>
</li>
<li><i><b>Code-UltraFeedback</b></i> — Preference curation for programming via judges assessing candidate solutions on coding quality dimensions.
  <a href="https://arxiv.org/abs/2403.09032" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.03-blue" alt="arXiv Badge"></a>
</li>
</ul>

## Tabular Data

LLM-synthesized structured tables used for privacy-preserving sharing, simulation, and downstream modeling; evaluation focuses on fidelity, privacy, and utility trade-offs.

### Prompt-Based Tabular Synthesis

<ul>
<li><i><b>CLLM</b></i> — Prompt/ICL-based tabular synthesis with confidence-aware filtering for low-data regimes.
  <a href="https://arxiv.org/abs/2312.12112" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
<li><i><b>EPIC</b></i> — Prompts targeted at minority and long-tail slices to balance generated tables.
  <a href="https://arxiv.org/abs/2404.12404" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.04-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>LITO</b></i> — Group-specific prompting for rare-class tabular synthesis.
  <a href="https://openreview.net/forum?id=8F6bws5JBy" target="_blank"><img src="https://img.shields.io/badge/ICLR-2024-blue" alt="ICLR Badge"></a>
</li>
<li><i><b>TabGen-ICL</b></i> — In-context learning framework for tabular data synthesis with few-shot exemplars.
  <a href="https://arxiv.org/abs/2502.16414" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.02-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>OCTree</b></i> — LLM-based optimized feature generation for tabular data using decision tree reasoning as feedback.
  <a href="https://arxiv.org/abs/2406.08527" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.06-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Fine-Tuning-Based Tabular Synthesis

<ul>
<li><i><b>GReaT</b></i> — Fine-tuned language model serializing tabular rows as natural language for realistic data generation.
  <a href="https://arxiv.org/abs/2210.06280" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.10-red" alt="arXiv Badge"></a>
</li>
<li><i><b>HARMONIC</b></i> — Fine-tuning method for harmonized tabular synthesis with improved mixed-type fidelity.
  <a href="https://arxiv.org/abs/2408.02927" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.08-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>TableDreamer</b></i> — Fine-tuning-based tabular data generation with enhanced column correlation modeling.
  <a href="https://arxiv.org/abs/2506.08646" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.06-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>Table-LLM-Specialist</b></i> — Specialized LLM fine-tuning for structured table generation tasks.
  <a href="https://arxiv.org/abs/2410.12164" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.10-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Hybrid Architectures

<ul>
<li><i><b>AIGT</b></i> — Hybrid architecture combining table-to-text and text-to-table transformations for bidirectional synthesis.
  <a href="https://arxiv.org/abs/2412.18111" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.12-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>gTBLS</b></i> — Hybrid LLM and tabular architecture combining generative and discriminative approaches.
  <a href="https://arxiv.org/abs/2403.14457" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.03-blue" alt="arXiv Badge"></a>
</li>
</ul>

## Semi-structured Data

Graph, JSON, and log-style corpora generated or expanded with LLMs for tool-use, API grounding, and graph reasoning.

### Graph Data Generation

<ul>
<li><i><b>LLM4GraphGen</b></i> — GPT-4 prompts generate node–edge lists and graph rewrites without tuning.
  <a href="https://arxiv.org/abs/2403.14358" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.03-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>GoG (Generate-on-Graph)</b></i> — LLM-based graph generation framework leveraging graph structure for guided synthesis.
  <a href="https://arxiv.org/abs/2404.14741" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.04-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>Ontology-grounded KG Generation</b></i> — Knowledge graph generation grounded in ontological constraints for structural coherence.
  <a href="https://arxiv.org/abs/2412.20942" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.12-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>GraphJudge</b></i> — Judge-based approach for graph quality validation and filtering of generated structures.
  <a href="https://arxiv.org/abs/2411.17388" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.11-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>GAG</b></i> — Multi-agent planner/evaluator ensemble to improve structural coherence of generated graphs.
  <a href="https://arxiv.org/abs/2410.09824" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.10-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>GraphMaster</b></i> — Planner–critic agents fine-tuned to evaluate and filter generated triples.
  <a href="https://arxiv.org/abs/2504.00711" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.04-blue" alt="arXiv Badge"></a>
</li>
</ul>

### JSON Data Generation

<ul>
<li><i><b>Outlines</b></i> — Framework for structured JSON output enforcement via grammar-constrained decoding.
  <a href="https://arxiv.org/abs/2307.09702" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.07-red" alt="arXiv Badge"></a>
  <a href="https://github.com/outlines-ai/outlines" target="_blank"><img src="https://img.shields.io/github/stars/outlines-ai/outlines.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>SchemaBench</b></i> — Benchmark and reinforcement learning methods for schema-compliant JSON generation.
  <a href="https://arxiv.org/abs/2502.18878" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.02-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>LM Format Enforcer</b></i> — Ensures LLM outputs conform to JSON schema specifications at decoding time.
  <a href="https://github.com/noamgat/lm-format-enforcer" target="_blank"><img src="https://img.shields.io/github/stars/noamgat/lm-format-enforcer.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Log Data Generation

<ul>
<li><i><b>LogBench</b></i> — Benchmark for structured log generation and analysis with LLMs.
  <a href="https://arxiv.org/abs/2307.05950" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.07-red" alt="arXiv Badge"></a>
</li>
<li><i><b>AUCAD</b></i> — Log anomaly detection enhanced with LLM-synthesized augmentation data.
  <a href="https://arxiv.org/abs/2412.18835" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.12-blue" alt="arXiv Badge"></a>
</li>
</ul>

## Vision-Language Data

Image–text and video–text synthetic pairs for multimodal instruction tuning and evaluation.

### Image-Text Native Autoregressive Models

<ul>
<li><i><b>Emu</b></i> — Unified multimodal LM that generates image–text tokens jointly for captioning and editing.
  <a href="https://arxiv.org/abs/2307.05222" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.07-red" alt="arXiv Badge"></a>
</li>
<li><i><b>Emu3</b></i> — Enhanced vision-language model with improved visual tokenization for unified multimodal generation.
  <a href="https://arxiv.org/abs/2409.18869" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.09-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>Chameleon</b></i> — Native autoregressive model for unified multimodal generation across text and images.
  <a href="https://arxiv.org/abs/2405.09818" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.05-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Image-Text External Diffusion Control

<ul>
<li><i><b>Kosmos-G</b></i> — Diffusion-based image generation with grounded language-visual alignment for compositional control.
  <a href="https://arxiv.org/abs/2310.02992" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.10-red" alt="arXiv Badge"></a>
</li>
<li><i><b>GILL</b></i> — Grounded image–language learning enabling interleaved text-and-image generation from frozen LLMs.
  <a href="https://arxiv.org/abs/2305.17216" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.05-red" alt="arXiv Badge"></a>
</li>
</ul>

### Video-Text Native Spatiotemporal Models

<ul>
<li><i><b>VideoPoet</b></i> — Native spatiotemporal autoregressive video generation from text and image prompts.
  <a href="https://arxiv.org/abs/2312.14125" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
</ul>

### Video-Text Planner-based Diffusion

<ul>
<li><i><b>FlowZero</b></i> — LLM plans storyboard-like shot sequences to guide video diffusion models.
  <a href="https://arxiv.org/abs/2311.15813" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.11-red" alt="arXiv Badge"></a>
</li>
<li><i><b>LVD (LLM-grounded Video Diffusion)</b></i> — Structured plans from LLMs steer latent video diffusion generation.
  <a href="https://arxiv.org/abs/2309.17444" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
</li>
<li><i><b>VideoDirectorGPT</b></i> — LLM produces shot lists and camera cues for diffusion-based video synthesis.
  <a href="https://arxiv.org/abs/2309.15091" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
</li>
</ul>

## Agent Data

Interactive trajectories and scenarios produced with LLMs to train or benchmark agents in digital and embodied environments.

### Environment & Task Data

<ul>
<li><i><b>ChatSUMO</b></i> — LLM-driven conversational traffic scenario generation for autonomous driving simulation.
  <a href="https://arxiv.org/abs/2409.09040" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.09-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>AutoScenario</b></i> — Automated scenario generation for autonomous driving evaluation and testing.
  <a href="https://arxiv.org/abs/2412.00243" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.12-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>TTSG</b></i> — Task and trajectory scenario generation for training embodied agents.
  <a href="https://arxiv.org/abs/2409.09575" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.09-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/basiclab/TTSG" target="_blank"><img src="https://img.shields.io/github/stars/basiclab/TTSG.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>L3M+P</b></i> — Language-guided embodied agent planning and trajectory generation with LLM integration.
  <a href="https://arxiv.org/abs/2508.01917" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.08-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>SELP</b></i> — Safe and efficient task plans via LLM-generated temporal logic with equivalence voting.
  <a href="https://arxiv.org/abs/2409.19471" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.09-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/lt-asset/selp" target="_blank"><img src="https://img.shields.io/github/stars/lt-asset/selp.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>T3 Planner</b></i> — Task, trajectory, and test planning system for embodied agent evaluation.
  <a href="https://arxiv.org/abs/2510.16767" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.10-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/leeejia/T3_Planner" target="_blank"><img src="https://img.shields.io/github/stars/leeejia/T3_Planner.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>PARTNR</b></i> — Procedurally generated multi-agent scenarios for training collaborative agents.
  <a href="https://arxiv.org/abs/2411.00081" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.11-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/facebookresearch/partnr-planner" target="_blank"><img src="https://img.shields.io/github/stars/facebookresearch/partnr-planner.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Control & Decision Data

<ul>
<li><i><b>Grid-Agent</b></i> — Grid-world agent trajectory generation for systematic decision-making evaluation.
  <a href="https://arxiv.org/abs/2508.05702" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.08-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>Twin-2K-500</b></i> — Digital twin synthetic control and decision dataset for agent benchmarking.
  <a href="https://arxiv.org/abs/2505.17479" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.05-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>BehaviorChain</b></i> — Behavioral chain-of-thought for generating structured agent trajectories.
  <a href="https://arxiv.org/abs/2502.14642" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.02-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/O-L1RU1/BehaviorChain" target="_blank"><img src="https://img.shields.io/github/stars/O-L1RU1/BehaviorChain.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>LLM Trainer</b></i> — LLM-based training data generation for robotic control policies.
  <a href="https://arxiv.org/abs/2509.20070" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.09-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>ELLMER</b></i> — Embodied LLM learning with merging and refining for manipulation task trajectories.
  <a href="https://arxiv.org/abs/2406.11231" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.06-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/ruaridhmon/ELLMER" target="_blank"><img src="https://img.shields.io/github/stars/ruaridhmon/ELLMER.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>Instruct2Act</b></i> — Instruction-guided action synthesis for robotic manipulation via LLM code generation.
  <a href="https://arxiv.org/abs/2305.11176" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.05-red" alt="arXiv Badge"></a>
  <a href="https://github.com/OpenGVLab/Instruct2Act" target="_blank"><img src="https://img.shields.io/github/stars/OpenGVLab/Instruct2Act.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>ProgPrompt</b></i> — Programmatic prompting generating robot action plans from natural language instructions.
  <a href="https://arxiv.org/abs/2209.11302" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.09-red" alt="arXiv Badge"></a>
  <a href="https://github.com/NVlabs/progprompt-vh" target="_blank"><img src="https://img.shields.io/github/stars/NVlabs/progprompt-vh.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Perception & Telemetry Data

<ul>
<li><i><b>DefectTwin</b></i> — Synthetic defect detection data via digital twins and LLM-guided augmentation.
  <a href="https://arxiv.org/abs/2409.06725" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.09-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/turna1/DefectTwin" target="_blank"><img src="https://img.shields.io/github/stars/turna1/DefectTwin.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>SceneCraft</b></i> — LLM-guided 3D scene layout synthesis for perception training data generation.
  <a href="https://arxiv.org/abs/2403.01248" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.03-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>BlenderLLM</b></i> — Blender-based synthetic perception data generation with LLM guidance for 3D scene understanding.
  <a href="https://arxiv.org/abs/2412.14203" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.12-blue" alt="arXiv Badge"></a>
  <a href="https://github.com/FreedomIntelligence/BlenderLLM" target="_blank"><img src="https://img.shields.io/github/stars/FreedomIntelligence/BlenderLLM.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

## Open Challenges and Future Directions

Open problems around metric robustness, trust–utility trade-offs, dynamic data curation, and standardized reporting for LLM-generated corpora. Key areas identified by the survey include evaluation practice gaps across all six modalities, under-reported metrics for fairness, robustness, and faithfulness, and the need for unified quality and trustworthiness frameworks that go beyond downstream task performance.
