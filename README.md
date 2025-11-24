# Awesome LLM Data Generation

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

LLM-driven data generation is reshaping how we build training corpora, benchmarks, and evaluators across text, code, vision, and structured data. This list follows the structure of *Towards a Unified Survey of LLM-Driven Data Generation* and highlights core areas where synthetic data, quality metrics, and trustworthiness intersect.

## Table of Contents

- [Text Data](#text-data)
- [Symbolic and Logical Data](#symbolic-and-logical-data)
- [Semi-structured Data](#semi-structured-data)
- [Vision–Language Data](#visionlanguage-data)
- [Agent Data](#agent-data)
- [Tabular Data](#tabular-data)
- [Open Challenges and Future Directions](#open-challenges-and-future-directions)

## Text Data

LLM-generated instructions, dialogues, and evaluations that power instruction-tuning and benchmarking.

<ul>
<li><i><b>Self-Instruct: Aligning Language Models with Self Generated Instructions</b></i> — Seeded prompting to grow diverse instruction–response pairs.
  <a href="https://arxiv.org/abs/2212.10560" target="_blank"><img src="https://img.shields.io/badge/arXiv-2022.12-red" alt="arXiv Badge"></a>
  <a href="https://github.com/yizhongw/self-instruct" target="_blank"><img src="https://img.shields.io/github/stars/yizhongw/self-instruct.svg?style=social" alt="GitHub stars"></a>
</li>
<li><i><b>Stanford Alpaca Data</b></i> — GPT-generated instruction-following dataset for lightweight fine-tuning.
  <a href="https://github.com/tatsu-lab/stanford_alpaca" target="_blank"><img src="https://img.shields.io/github/stars/tatsu-lab/stanford_alpaca.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

## Symbolic and Logical Data

Math, program synthesis, and formal reasoning datasets crafted or expanded by LLMs, often paired with verifier loops.

<ul>
<li><i><b>GSM8K</b></i> — Grade-school math word problems frequently used with LLM-generated augmentations.
  <a href="https://arxiv.org/abs/2110.14168" target="_blank"><img src="https://img.shields.io/badge/arXiv-2021.10-red" alt="arXiv Badge"></a>
</li>
</ul>

## Semi-structured Data

Graph, JSON, and log-style corpora generated or expanded with LLMs for tool-use, API grounding, and graph reasoning.

<ul>
<li><i><b>ToolBench</b></i> — Multi-turn JSON/function-calling conversations generated via GPT-series models.
  <a href="https://github.com/OpenBMB/ToolBench" target="_blank"><img src="https://img.shields.io/github/stars/OpenBMB/ToolBench.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

## Vision–Language Data

Image–text and video–text synthetic pairs for multimodal instruction tuning and evaluation.

<ul>
<li><i><b>LLaVA</b></i> — GPT-generated visual instruction data aligned with image features.
  <a href="https://arxiv.org/abs/2304.08485" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.04-red" alt="arXiv Badge"></a>
  <a href="https://github.com/haotian-liu/LLaVA" target="_blank"><img src="https://img.shields.io/github/stars/haotian-liu/LLaVA.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

## Agent Data

Interactive trajectories and scenarios produced with LLMs to train or benchmark agents in digital environments.

<ul>
<li><i><b>AgentBench</b></i> — A suite of agent tasks with LLM-generated interactions.
  <a href="https://arxiv.org/abs/2308.03688" target="_blank"><img src="https://img.shields.io/badge/arXiv-2023.08-red" alt="arXiv Badge"></a>
  <a href="https://github.com/THUDM/AgentBench" target="_blank"><img src="https://img.shields.io/github/stars/THUDM/AgentBench.svg?style=social" alt="GitHub stars"></a>
</li>
</ul>

## Tabular Data

LLM-synthesized structured tables used for privacy-preserving sharing, simulation, and downstream modeling; evaluation focuses on fidelity, privacy, and utility trade-offs.

## Open Challenges and Future Directions

Open problems around metric robustness, trust–utility trade-offs, dynamic data curation, and standardized reporting for LLM-generated corpora.
