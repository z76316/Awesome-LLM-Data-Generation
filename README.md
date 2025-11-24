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

- **Self-Instruct** — Seeded prompting to grow diverse instruction–response pairs. Paper: https://arxiv.org/abs/2212.10560 • Repo: https://github.com/yizhongw/self-instruct
- **Stanford Alpaca Data** — GPT-generated instruction-following dataset for lightweight fine-tuning. Repo: https://github.com/tatsu-lab/stanford_alpaca

## Symbolic and Logical Data

Math, program synthesis, and formal reasoning datasets crafted or expanded by LLMs, often paired with verifier loops.

- **GSM8K** — Grade-school math word problems frequently used with LLM-generated augmentations. Paper: https://arxiv.org/abs/2110.14168

## Semi-structured Data

Graph, JSON, and log-style corpora generated or expanded with LLMs for tool-use, API grounding, and graph reasoning.

- **ToolBench** — Multi-turn JSON/function-calling conversations generated via GPT-series models. Repo: https://github.com/OpenBMB/ToolBench

## Vision–Language Data

Image–text and video–text synthetic pairs for multimodal instruction tuning and evaluation.

- **LLaVA** — GPT-generated visual instruction data aligned with image features. Paper: https://arxiv.org/abs/2304.08485 • Repo: https://github.com/haotian-liu/LLaVA

## Agent Data

Interactive trajectories and scenarios produced with LLMs to train or benchmark agents in digital environments.

- **AgentBench** — A suite of agent tasks with LLM-generated interactions. Paper: https://arxiv.org/abs/2308.03688 • Repo: https://github.com/THUDM/AgentBench

## Tabular Data

LLM-synthesized structured tables used for privacy-preserving sharing, simulation, and downstream modeling; evaluation focuses on fidelity, privacy, and utility trade-offs.

## Open Challenges and Future Directions

Open problems around metric robustness, trust–utility trade-offs, dynamic data curation, and standardized reporting for LLM-generated corpora.
