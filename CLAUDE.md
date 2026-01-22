# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a sandbox project for experimenting with HuggingFace's smolagents library - a framework for building agentic AI systems. The project uses the smolagents CodeAgent with tools like DuckDuckGoSearchTool to create agents that can perform complex reasoning and search tasks.

Reference materials:
- https://github.com/huggingface/smolagents
- https://www.anthropic.com/research/building-effective-agents
- https://huggingface.co/blog/smolervlm

## Environment Setup

This project uses Conda for environment management with Python 3.10, PyTorch, and smolagents.

**Create and activate environment:**
```bash
conda env create -f environment.yml
conda activate smolagents
```

**Update environment after changes to environment.yml:**
```bash
conda env update -f environment.yml --prune
```

**Deactivate environment:**
```bash
conda deactivate
```

## Running the Project

**Run the example agent:**
```bash
python main.py
```

## Environment Variables

Copy `.env.example` to `.env` and configure:
- `OPENAI_API_KEY`: Required if using OpenAI models with smolagents (though the example uses HfApiModel which uses HuggingFace's inference API)

## Architecture

The project is currently minimal with a single example in `main.py` that demonstrates:
1. Initializing a CodeAgent with the DuckDuckGoSearchTool
2. Using HfApiModel as the underlying language model
3. Running queries that require web search and reasoning

The smolagents framework enables agents to:
- Execute Python code dynamically to solve problems
- Use external tools (like web search)
- Perform multi-step reasoning

## Important Notes

- README.md must be kept up to date with any significant project changes
- This is a sandbox/experimental project for learning about agent frameworks
