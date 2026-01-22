<div align="center">
  <img src="logo.png" alt="sandbox-smolagents" width="512"/>

  [![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
  [![smolagents](https://img.shields.io/badge/smolagents-HuggingFace-orange.svg)](https://github.com/huggingface/smolagents)
  [![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

  **A sandbox for experimenting with HuggingFace's smolagents - build AI agents that reason, search, and execute code**

  [smolagents docs](https://github.com/huggingface/smolagents) · [Anthropic agents guide](https://www.anthropic.com/research/building-effective-agents)
</div>

## Overview

This project is a playground for learning HuggingFace's [smolagents](https://github.com/huggingface/smolagents) library - a lightweight framework for building agentic AI systems. The included example demonstrates a CodeAgent that uses web search and multi-step reasoning to answer complex questions.

## Features

- **CodeAgent** - Agents that write and execute Python code to solve problems
- **Tool Integration** - Built-in DuckDuckGoSearchTool for web search capabilities
- **Multi-step Reasoning** - Agents break down complex queries into actionable steps
- **HuggingFace Integration** - Uses HfApiModel for inference via HuggingFace's API

## Quick Start

```bash
# Clone and setup
git clone https://github.com/tsilva/sandbox-smolagents.git
cd sandbox-smolagents
conda env create -f environment.yml
conda activate smolagents

# Run the example
python main.py
```

## Installation

### Prerequisites

- [Conda](https://docs.conda.io/en/latest/miniconda.html) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- Python 3.10

### Environment Setup

```bash
# Create the conda environment
conda env create -f environment.yml

# Activate it
conda activate smolagents

# (Optional) Copy .env.example to .env if using OpenAI models
cp .env.example .env
```

### Update Environment

After modifying `environment.yml`:

```bash
conda env update -f environment.yml --prune
```

## Usage

The example in `main.py` demonstrates a CodeAgent with web search:

```python
from smolagents import CodeAgent, DuckDuckGoSearchTool, HfApiModel

agent = CodeAgent(tools=[DuckDuckGoSearchTool()], model=HfApiModel())
agent.run("How many seconds would it take for a leopard at full speed to run through Pont des Arts?")
```

The agent will:
1. Search for the leopard's top speed
2. Search for the length of Pont des Arts
3. Calculate the time using Python code
4. Return the answer

## Project Structure

```
sandbox-smolagents/
├── main.py              # Example agent script
├── environment.yml      # Conda environment definition
├── .env.example         # Environment variables template
├── LICENSE              # MIT License
└── README.md            # This file
```

## Resources

- [smolagents GitHub](https://github.com/huggingface/smolagents) - Official smolagents repository
- [Building Effective Agents](https://www.anthropic.com/research/building-effective-agents) - Anthropic's guide to agentic systems
- [SmolVLM Blog Post](https://huggingface.co/blog/smolervlm) - HuggingFace blog on small vision-language models

## License

[MIT](LICENSE)
