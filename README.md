# 🧮 AI Math Agent — CrewAI + Ollama

An **Agentic AI / Generative AI** project that uses a local **Llama 3.2 1B** model through **Ollama** and **CrewAI** to demonstrate how an AI agent can use a custom Python calculator tool to handle mathematical tasks.

## 📌 About the Project

The project demonstrates a simple **LLM-powered AI agent with tool calling**.

Instead of relying entirely on the language model for mathematical computation, the agent is provided with a dedicated calculator tool.

### Workflow

```text
Mathematical Task
       ↓
   CrewAI Agent
       ↓
 Llama 3.2 1B
   via Ollama
       ↓
 Calculator Tool
       ↓
 Mathematical Result
```

The current demonstration uses the task:

```text
Calculate the result of (45+55)*5
```

The notebook demonstrates the agent execution and tool-call workflow for this task.

---

## 🛠️ Tools & Technologies

| Technology | Purpose |
|---|---|
| **Python 3.11.9** | Core programming language |
| **CrewAI** | AI agent creation and orchestration |
| **Ollama** | Local LLM runtime |
| **Llama 3.2 1B** | Language model used by the agent |
| **CrewAI Tools** | Connects Python functions to the agent |
| **Jupyter Notebook** | Development and experimentation |

### Main Components

**AI Agent — Math Solver**

The CrewAI agent is configured with a mathematical-solving role and access to the calculator tool.

**LLM — Llama 3.2 1B**

Runs locally through Ollama instead of using a cloud-based LLM API.

**Calculator Tool**

A custom Python function exposed to the agent using CrewAI's `@tool` decorator.

```python
@tool
def calculator(expression: str) -> str:
    try:
        return str(eval(expression))
    except:
        return "Error in Calculation"
```

**CrewAI Task**

The current task is:

```text
Calculate the result of (45+55)*5
```

---

## 🔄 How It Works

1. A mathematical task is defined.
2. CrewAI initializes the **Math Solver** agent.
3. The agent uses **Llama 3.2 1B** through Ollama.
4. The calculator function is available as an external tool.
5. CrewAI executes the task and records the agent/tool interaction.
6. The expected mathematical result for the demonstration is:

```text
500
```

The saved notebook output demonstrates the structured tool-call workflow, although it does not currently display the final `500` as a clean user-facing response.

---

## 🧠 Key Concepts Demonstrated

- Generative AI
- Agentic AI
- AI Agents
- Large Language Models (LLMs)
- Tool Calling
- Function Calling
- Agent Orchestration
- Local LLMs
- CrewAI
- Ollama
- Prompt/Agent Configuration
- Python-based AI Tools

---

## ⚠️ Current Limitations

The current version is a **proof-of-concept / learning project**.

- The mathematical task is currently hardcoded.
- Only one AI agent is used.
- Only one tool (calculator) is available.
- The calculator currently uses Python `eval()`.
- There is no graphical/web interface.
- The saved execution output does not show a clean final numerical response.

> `eval()` should not be used with unrestricted or untrusted input in a production application.

---

## 🚀 Planned Improvements

### 1. Interactive User Input

Allow users to enter mathematical problems dynamically, for example:

```text
Calculate 25 × 17
What is 18% of 5000?
Calculate (1250 / 5) + 37²
```

### 2. Safer Calculation

Replace `eval()` with a safer mathematical expression parser such as **SymPy**.

### 3. Multiple Tools

Add specialized tools such as:

- Calculator
- Percentage Calculator
- Unit Converter
- Statistics Calculator

This would turn the project into a genuine **multi-tool AI assistant**.

### 4. Multi-Agent Architecture

Introduce specialized agents such as:

```text
Math Solver → Verifier → Explainer → Final Answer
```

- **Math Solver:** solves the problem
- **Verifier:** checks the result
- **Explainer:** explains the solution

### 5. Streamlit Interface

Create a web interface where users can submit mathematical problems and receive the agent's response interactively.

### 6. Better Error Handling & Validation

Add input validation, safer tool execution, and clearer user-facing responses.

---

## 📈 Future Architecture

```text
                    User
                     ↓
                Streamlit UI
                     ↓
                CrewAI Crew
                     ↓
          ┌──────────┼──────────┐
          ↓          ↓          ↓
       Solver     Verifier   Explainer
          │          │          │
          └──────────┼──────────┘
                     ↓
               Tool Selection
                     ↓
          ┌──────────┼──────────┐
          ↓          ↓          ↓
      Calculator  Unit Tool  Statistics
                     ↓
                Final Answer
```

---

## 📂 Repository Structure

```text
ai-math-agent-crewai/
│
├── math_agent.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ⚙️ Setup

### Clone

```bash
git clone https://github.com/YOUR_USERNAME/ai-math-agent-crewai.git
cd ai-math-agent-crewai
```

### Create Virtual Environment

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

Recommended `requirements.txt`:

```text
crewai
ollama
jupyter
ipykernel
```

### Ollama

Install and run Ollama locally and make sure the required model is available:

```text
llama3.2:1b
```

The project expects the local Ollama service at:

```text
http://localhost:11434
```

### Run

Open:

```text
math_agent.ipynb
```

in Jupyter Notebook or VS Code and run the cells sequentially.

---

## 📚 Learning Outcomes

This project provides hands-on experience with:

- Building an AI agent with CrewAI
- Connecting a local LLM using Ollama
- Integrating custom Python tools
- Understanding tool calling
- Designing agent roles and tasks
- Orchestrating LLM-powered workflows
- Understanding the limitations and safety considerations of tool-based agents

---

## 🏷️ Keywords

`Generative AI` `GenAI` `Agentic AI` `AI Agents` `CrewAI` `Ollama` `Llama 3.2` `LLM` `Tool Calling` `Function Calling` `Agent Orchestration` `Local LLM` `Python` `Prompt Engineering` `Artificial Intelligence` `AI Assistant`

---

## 📌 Project Status

🟡 **Proof of Concept / Learning Project**

The current version focuses on demonstrating the fundamentals of **LLM-powered agents and tool calling**. The planned improvements describe how the project can be extended into a more capable multi-tool and multi-agent mathematical assistant.

---

## 👨‍💻 Author

**Arjun Vijayan**

Aspiring **AI/ML Engineer | Data Scientist | Data Analyst**
