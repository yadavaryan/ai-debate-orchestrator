# 🏛️ AI Debate Orchestrator

<div align="center">

[![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-Integration-green?style=for-the-badge)](https://langchain.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT4-red?style=for-the-badge&logo=openai)](https://openai.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**An intelligent orchestration system featuring autonomous AI agents debating complex topics, overseen by an impartial AI judge.**

</div>

---

## 📖 Overview

The **AI Debate Orchestrator** simulates a structured debate environment where AI agents take opposing stances on user-defined topics. By employing advanced orchestration (similar to AutoGen), the system facilitates logical argumentation and counter-argumentation across multiple rounds, culminating in a balanced verdict delivered by a specialized "Judge" agent.

This project demonstrates advanced multi-agent collaboration, dynamic context handling, and complex prompt engineering to maintain distinct personas and logic threads.

## ✨ Features

- **🎭 Persona-Driven Agents**: Pro and Con agents are instantiated with specific expertise (e.g., "Technology Economist", "Labor Economist") to provide grounded, domain-specific arguments.
- **🔄 Multi-Round Debates**: Supports configurable rounds of debate, allowing agents to respond to their opponent's previous points dynamically.
- **⚖️ Impartial AI Judge**: A dedicated GPT-4o model evaluates the entire conversation history, scoring arguments, identifying key insights, and declaring a winner.
- **⚡ Lightweight & Fast**: Built with LangChain and leveraging `gpt-4o-mini` for the debaters for optimal speed, and `gpt-4o` for the judge for high-quality reasoning.

## 🚀 Quick Start

### 1. Prerequisites

- Python 3.10 or higher
- OpenAI API Key

### 2. Installation

Clone this repository and install the required dependencies:

```bash
git clone https://github.com/yourusername/ai-debate-orchestrator.git
cd ai-debate-orchestrator
pip install -r requirements.txt
```

### 3. Configuration

Create a `.env` file in the root directory and add your OpenAI API key:

```env
OPENAI_API_KEY=your_api_key_here
```

### 4. Usage

Run a debate by specifying a topic. You can also define the number of rounds.

```bash
# Basic run with default topic
python agent.py

# Specify a custom topic and number of rounds
python agent.py --topic "Remote work is better than office work" --rounds 3
```

## 🏗️ Architecture

1. **DebateAgent (`Pro` / `Con`)**: Utilizes `gpt-4o-mini`. Context window is dynamically updated with the opponent's previous argument.
2. **DebateJudge**: Utilizes `gpt-4o`. Takes the entire history of `Pro` and `Con` arguments as input and evaluates them using a structured evaluation prompt.
3. **Orchestrator (`run_debate`)**: Manages the flow of the conversation, printing formatted output to the console and feeding arguments between agents.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📜 License

This project is licensed under the MIT License.
