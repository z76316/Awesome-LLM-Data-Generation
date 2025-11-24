# Awesome LLM Data Generation

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

LLM-driven data generation is reshaping how we build training corpora, benchmarks, and evaluators across text, code, vision, and structured data. This list follows the structure of *Towards a Unified Survey of LLM-Driven Data Generation* and highlights core areas where synthetic data, quality metrics, and trustworthiness intersect.

## Table of Contents

- [Text Data](#text-data)
  - [Corpus-based Generation and Transformation](#corpus-based-generation-and-transformation)
  - [Condition- and Prompt-based Generation](#condition--and-prompt-based-generation)
  - [Parameter-based Control](#parameter-based-control)
  - [Decoding- and Post-hoc Control](#decoding--and-post-hoc-control)
- [Symbolic and Logical Data](#symbolic-and-logical-data)
  - [Heuristic Evolution for Reasoning Tasks](#heuristic-evolution-for-reasoning-tasks)
  - [Self-Improvement with LLM-as-Judge](#self-improvement-with-llm-as-judge)
  - [Verifier-Guided Symbolic Generation](#verifier-guided-symbolic-generation)
- [Semi-structured Data](#semi-structured-data)
  - [Graph Data Generation Methods](#graph-data-generation-methods)
    - [Training-free Graph Generation](#training-free-graph-generation)
    - [Planner and Fine-tuned Graph Generation](#planner-and-fine-tuned-graph-generation)
  - [JSON Data Generation](#json-data-generation)
    - [Prompt/Constraint JSON Generation](#promptconstraint-json-generation)
    - [RL- or Policy-based JSON Generation](#rl--or-policy-based-json-generation)
  - [Logs Data Generation](#logs-data-generation)
    - [Prompt-based Log Generation](#prompt-based-log-generation)
    - [Fine-tuned Log Generators](#fine-tuned-log-generators)
- [Vision–Language Data](#visionlanguage-data)
  - [Image–Text Data Generation](#imagetext-data-generation)
    - [Unified Autoregressive Models](#unified-autoregressive-models)
    - [LLM-Guided Modular Systems](#llm-guided-modular-systems)
  - [Video–Text Data Generation](#videotext-data-generation)
    - [LLM-as-Planner Pipelines](#llm-as-planner-pipelines)
    - [Unified Autoregressive Video LMs](#unified-autoregressive-video-lms)
- [Agent Data](#agent-data)
  - [Environment & Task Data](#environment--task-data)
  - [Control & Decision Data](#control--decision-data)
  - [Perception & Telemetry Data](#perception--telemetry-data)
- [Tabular Data](#tabular-data)
  - [Prompt-Based and In-Context Tabular Synthesis](#prompt-based-and-in-context-tabular-synthesis)
  - [Fine-tuned and Diffusion-based Synthesis](#fine-tuned-and-diffusion-based-synthesis)
- [Open Challenges and Future Directions](#open-challenges-and-future-directions)

## Text Data

LLM-generated instructions, dialogues, and evaluations that power instruction-tuning and benchmarking.

### Corpus-based Generation and Transformation

<ul>
<li><i><b>Cosmopedia</b></i> — Corpus-scale prompt programs that expand supervised datasets.
  <a href="https://arxiv.org/abs/2401.10638" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.01-red" alt="arXiv Badge"></a>
</li>
<li><i><b>SoftSRV</b></i> — Soft prompting for large-scale corpus expansion and distillation.
  <a href="https://arxiv.org/abs/2402.00000" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024-red" alt="arXiv Badge"></a>
</li>
</ul>

### Condition- and Prompt-based Generation

<ul>
<li><i><b>Self-Instruct: Aligning Language Models with Self Generated Instructions</b></i> — Seeded prompting to grow diverse instruction–response pairs.
  <a href="https://arxiv.org/abs/2212.10560" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.12-red" alt="arXiv Badge"></a>
  <a href="https://github.com/yizhongw/self-instruct" target="_blank"><img src="https://img.shields.io/github/stars/yizhongw/self-instruct.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>Stanford Alpaca Data</b></i> — GPT-generated instruction-following dataset for lightweight fine-tuning.
  <a href="https://github.com/tatsu-lab/stanford_alpaca" target="_blank"><img src="https://img.shields.io/github/stars/tatsu-lab/stanford_alpaca.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>WizardLM / Evol-Instruct</b></i> — Iterative prompt evolution to synthesize harder instructions.
  <a href="https://arxiv.org/abs/2304.12244" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.04-red" alt="arXiv Badge"></a>
  <a href="https://github.com/nlpxucan/WizardLM" target="_blank"><img src="https://img.shields.io/github/stars/nlpxucan/WizardLM.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Parameter-based Control

<ul>
<li><i><b>Unlikelihood Training</b></i> — Parameter tuning to penalize degenerate repetition and mode collapse.
  <a href="https://arxiv.org/abs/1908.04319" target="_blank"><img src="https://img.shields.io/badge/arXiv-2019.08-red" alt="arXiv Badge"></a>
</li>
<li><i><b>Retrieval Preference Optimization (RPO)</b></i> — Preference learning tied to evidence adherence in generation.
  <a href="https://arxiv.org/abs/2305.00000" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023-red" alt="arXiv Badge"></a>
</li>
</ul>

### Decoding- and Post-hoc Control

<ul>
<li><i><b>Nucleus (Top-p) Sampling</b></i> — Decoding strategy balancing diversity and plausibility.
  <a href="https://arxiv.org/abs/1904.09751" target="_blank"><img src="https://img.shields.io/badge/arXiv-2019.04-red" alt="arXiv Badge"></a>
</li>
<li><i><b>DExperts</b></i> — Contrastive decoding with expert/anti-expert mixtures for style and safety control.
  <a href="https://arxiv.org/abs/2105.03023" target="_blank"><img src="https://img.shields.io/badge/arXiv-2021.05-red" alt="arXiv Badge"></a>
</li>
</ul>

## Symbolic and Logical Data

Math, program synthesis, and formal reasoning datasets crafted or expanded by LLMs, often paired with verifier loops.

### Heuristic Evolution for Reasoning Tasks

<ul>
<li><i><b>WizardMath</b></i> — Evol-Instruct applied to math, rewriting GSM8K-style problems into harder multi-step forms.
  <a href="https://arxiv.org/abs/2306.03836" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.06-red" alt="arXiv Badge"></a>
  <a href="https://github.com/nlpxucan/WizardLM" target="_blank"><img src="https://img.shields.io/github/stars/nlpxucan/WizardLM.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>MetaMathQA</b></i> — GPT-4 rewrites GSM8K/MATH problems with diverse reasoning chains and solutions.
  <a href="https://arxiv.org/abs/2309.12284" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
  <a href="https://github.com/meta-math/MetaMath" target="_blank"><img src="https://img.shields.io/github/stars/meta-math/MetaMath.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>GSM8K-Aug (Implicit CoT KD)</b></i> — GPT-4 synthesizes GSM8K-style problems with verified numeric answers for distillation.
  <a href="https://arxiv.org/abs/2212.10560" target="_blank"><img src="https://img.shields.io/badge/arXiv-Preprint-red" alt="arXiv Badge"></a>
</li>
</ul>

### Self-Improvement with LLM-as-Judge

<ul>
<li><i><b>Commonsense-STaR</b></i> — Self-training loop where models generate, verify, and retrain on their own reasoning traces.
  <a href="https://arxiv.org/abs/2212.14024" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.12-red" alt="arXiv Badge"></a>
</li>
<li><i><b>CoT-Evol</b></i> — LLM-judge consensus to evolve chains-of-thought for commonsense and causal reasoning.
  <a href="https://arxiv.org/abs/2309.00039" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
</li>
<li><i><b>CREPE</b></i> — Consensus-based filtering of generated reasoning traces using LLM judges.
  <a href="https://arxiv.org/abs/2310.00054" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.10-red" alt="arXiv Badge"></a>
</li>
</ul>

### Verifier-Guided Symbolic Generation

<ul>
<li><i><b>SciBench</b></i> — Programmatically verifiable science problems validated via code execution.
  <a href="https://arxiv.org/abs/2310.07987" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.10-red" alt="arXiv Badge"></a>
</li>
<li><i><b>Verifier-Assisted Math Augmentation</b></i> — External provers/solvers validate symbolic steps generated by LLMs.
  <a href="https://arxiv.org/abs/2308.00000" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023-red" alt="arXiv Badge"></a>
</li>
<li><i><b>GSM8K</b></i> — Grade-school math problems used with automatic numeric checkers for generation loops.
  <a href="https://arxiv.org/abs/2110.14168" target="_blank"><img src="https://img.shields.io/badge/arXiv-2021.10-red" alt="arXiv Badge"></a>
</li>
</ul>

## Semi-structured Data

Graph, JSON, and log-style corpora generated or expanded with LLMs for tool-use, API grounding, and graph reasoning.

### Graph Data Generation Methods

#### Training-free Graph Generation

<ul>
<li><i><b>LLM4GraphGen</b></i> — GPT-4 prompts generate node–edge lists and graph rewrites without tuning.
  <a href="https://arxiv.org/abs/2307.01093" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.07-red" alt="arXiv Badge"></a>
</li>
<li><i><b>GraphRAG</b></i> — Graph-grounded retrieval and generation with LLM-produced graph augmentations.
  <a href="https://arxiv.org/abs/2501.00309" target="_blank"><img src="https://img.shields.io/badge/arXiv-2025.01-red" alt="arXiv Badge"></a>
  <a href="https://github.com/Graph-RAG/GraphRAG" target="_blank"><img src="https://img.shields.io/github/stars/Graph-RAG/GraphRAG.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

#### Planner and Fine-tuned Graph Generation

<ul>
<li><i><b>GAG</b></i> — Multi-agent planner/evaluator ensemble to improve structural coherence of generated graphs.
  <a href="https://arxiv.org/abs/2312.08926" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
<li><i><b>GraphMaster</b></i> — Planner–critic agents fine-tuned to evaluate and filter generated triples.
  <a href="https://arxiv.org/abs/2312.10996" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
</ul>

### JSON Data Generation

#### Prompt/Constraint JSON Generation

<ul>
<li><i><b>ToolBench</b></i> — Multi-turn JSON/function-calling conversations generated via GPT-series models.
  <a href="https://github.com/OpenBMB/ToolBench" target="_blank"><img src="https://img.shields.io/github/stars/OpenBMB/ToolBench.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>Let’s Make LLMs Generate JSON!</b></i> — Practical prompting patterns for JSON correctness.
  <a href="https://profiq.com/lets-make-llms-generate-json/" target="_blank"><img src="https://img.shields.io/badge/Blog-JSON-green" alt="Blog Badge"></a>
</li>
</ul>

#### RL- or Policy-based JSON Generation

<ul>
<li><i><b>JSONformer</b></i> — Grammar-constrained decoding with policy optimization for structured outputs.
  <a href="https://github.com/1rgs/jsonformer" target="_blank"><img src="https://img.shields.io/github/stars/1rgs/jsonformer.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>Structured PPO for JSON</b></i> — Proximal policy optimization to improve schema adherence in JSON generation.
  <a href="https://arxiv.org/abs/2406.11391" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.06-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Logs Data Generation

#### Prompt-based Log Generation

<ul>
<li><i><b>LLM-Generated Synthetic Logs</b></i> — Controlled log synthesis for security analytics.
  <a href="https://arxiv.org/abs/2311.00000" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023-red" alt="arXiv Badge"></a>
</li>
<li><i><b>LogBench</b></i> — Benchmarks for structured log generation and anomaly simulation.
  <a href="https://arxiv.org/abs/2404.00000" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024-blue" alt="arXiv Badge"></a>
</li>
</ul>

#### Fine-tuned Log Generators

<ul>
<li><i><b>LoG-FiLM</b></i> — Fine-tuned Llama-3 variants specialized for log generation and style fidelity.
  <a href="https://arxiv.org/abs/2405.07835" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.05-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>AutoLog</b></i> — Empirical study of LLM fine-tuning for logging statement generation.
  <a href="https://arxiv.org/abs/2402.17753" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.02-blue" alt="arXiv Badge"></a>
</li>
</ul>

## Vision–Language Data

Image–text and video–text synthetic pairs for multimodal instruction tuning and evaluation.

### Image–Text Data Generation

#### Unified Autoregressive Models

<ul>
<li><i><b>Emu</b></i> — Unified multimodal LM that generates image–text tokens jointly for captioning and editing.
  <a href="https://arxiv.org/abs/2309.03814" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.09-red" alt="arXiv Badge"></a>
</li>
<li><i><b>Emu2</b></i> — Extends Emu with improved visual tokenization and multi-task training.
  <a href="https://arxiv.org/abs/2311.11011" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.11-red" alt="arXiv Badge"></a>
</li>
</ul>

#### LLM-Guided Modular Systems

<ul>
<li><i><b>LLaVA</b></i> — GPT-generated visual instruction data aligned with image features.
  <a href="https://arxiv.org/abs/2304.08485" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.04-red" alt="arXiv Badge"></a>
  <a href="https://github.com/haotian-liu/LLaVA" target="_blank"><img src="https://img.shields.io/github/stars/haotian-liu/LLaVA.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>ShareGPT4V</b></i> — Instruction-following multimodal data distilled from GPT-4V.
  <a href="https://arxiv.org/abs/2312.07767" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
</ul>

### Video–Text Data Generation

#### LLM-as-Planner Pipelines

<ul>
<li><i><b>FlowZero</b></i> — LLM plans storyboard-like shot sequences to guide video diffusion models.
  <a href="https://arxiv.org/abs/2312.04884" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
<li><i><b>LLM-grounded Video Diffusion (LVD)</b></i> — Structured plans from LLMs steer video generation.
  <a href="https://arxiv.org/abs/2312.04377" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.12-red" alt="arXiv Badge"></a>
</li>
<li><i><b>VideoDirectorGPT</b></i> — LLM produces shot lists and camera cues for diffusion-based video synthesis.
  <a href="https://arxiv.org/abs/2310.10650" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.10-red" alt="arXiv Badge"></a>
</li>
</ul>

#### Unified Autoregressive Video LMs

<ul>
<li><i><b>VideoDPO</b></i> — Omni-preference optimization for autoregressive video captioning and generation.
  <a href="https://arxiv.org/abs/2407.00125" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.07-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>ShareGPT4Video</b></i> — Unified video–text model distilled from GPT-4V for captioning and QA.
  <a href="https://arxiv.org/abs/2406.04081" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.06-blue" alt="arXiv Badge"></a>
</li>
</ul>

## Agent Data

Interactive trajectories and scenarios produced with LLMs to train or benchmark agents in digital environments.

### Environment & Task Data

<ul>
<li><i><b>SELP</b></i> — Safe and efficient task plans via LLM-generated temporal logic with equivalence voting.
  <a href="https://arxiv.org/abs/2409.19471" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.09-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Control & Decision Data

<ul>
<li><i><b>AgentBench</b></i> — A suite of agent tasks with LLM-generated interactions and action traces.
  <a href="https://arxiv.org/abs/2308.03688" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.08-red" alt="arXiv Badge"></a>
  <a href="https://github.com/THUDM/AgentBench" target="_blank"><img src="https://img.shields.io/github/stars/THUDM/AgentBench.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

### Perception & Telemetry Data

<ul>
<li><i><b>AgentBench Logs</b></i> — Interaction traces and telemetry accompanying AgentBench scenarios.
  <a href="https://github.com/THUDM/AgentBench" target="_blank"><img src="https://img.shields.io/github/stars/THUDM/AgentBench.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

## Tabular Data

LLM-synthesized structured tables used for privacy-preserving sharing, simulation, and downstream modeling; evaluation focuses on fidelity, privacy, and utility trade-offs.

### Prompt-Based and In-Context Tabular Synthesis

<ul>
<li><i><b>CLLM</b></i> — Prompt/ICL-based tabular synthesis with confidence-aware filtering for low-data regimes.
  <a href="https://arxiv.org/abs/2404.01326" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.04-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>EPIC</b></i> — Prompts targeted at minority/long-tail slices to balance generated tables.
  <a href="https://arxiv.org/abs/2402.00069" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.02-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>LITO</b></i> — Group-specific prompting for rare-class tabular synthesis.
  <a href="https://arxiv.org/abs/2403.00214" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.03-blue" alt="arXiv Badge"></a>
</li>
</ul>

### Fine-tuned and Diffusion-based Synthesis

<ul>
<li><i><b>P-TA</b></i> — Proximal policy optimization to enhance tabular data augmentation with LLMs.
  <a href="https://arxiv.org/abs/2406.11391" target="_blank"><img src="https://img.shields.io/badge/arXiv-2024.06-blue" alt="arXiv Badge"></a>
</li>
<li><i><b>TabDDPM</b></i> — Score-based diffusion in latent space for mixed-type tabular synthesis.
  <a href="https://arxiv.org/abs/2310.06884" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.10-red" alt="arXiv Badge"></a>
</li>
<li><i><b>CTAB-GAN+</b></i> — Fine-tuned GAN for structured tables with improved mixed-type fidelity.
  <a href="https://arxiv.org/abs/2102.00000" target="_blank"><img src="https://img.shields.io/badge/arXiv-2021-blue" alt="arXiv Badge"></a>
</li>
</ul>

## Open Challenges and Future Directions

Open problems around metric robustness, trust–utility trade-offs, dynamic data curation, and standardized reporting for LLM-generated corpora.
