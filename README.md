<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="docs/logo/dark.png" />
    <source media="(prefers-color-scheme: light)" srcset="docs/logo/light.png" />
    <img alt="praison Logo" src="docs/logo/light.png" />
  </picture>
</p>

<p align="center">
<a href="https://github.com/MervinPraison/praison"><img src="https://static.pepy.tech/badge/praison" alt="Total Downloads" /></a>
<a href="https://github.com/MervinPraison/praison"><img src="https://img.shields.io/github/v/release/MervinPraison/praison" alt="Latest Stable Version" /></a>
<a href="https://github.com/MervinPraison/praison"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License" /></a>
</p>

<div align="center">

# Praison AI

<a href="https://trendshift.io/repositories/9130" target="_blank"><img src="https://trendshift.io/api/badge/repositories/9130" alt="MervinPraison%2Fpraison | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

</div>

praison is a production-ready Multi-AI Agents framework with self-reflection, designed to create AI Agents to automate and solve problems ranging from simple tasks to complex challenges. By integrating praison Agents, AG2 (Formerly AutoGen), and CrewAI into a low-code solution, it streamlines the building and management of multi-agent LLM systems, emphasising simplicity, customisation, and effective human-agent collaboration.

<div align="center">
  <a href="https://docs.praisonlabs.com" target="_blank">
    <p align="center">
      <img src="https://img.shields.io/badge/📚_Documentation-Visit_docs.praison.ai-blue?style=for-the-badge&logo=bookstack&logoColor=white" alt="Documentation" />
    </p>
  </a>
</div>

## Key Features

- 🤖 Automated AI Agents Creation
- 🔄 Self Reflection AI Agents
- 🧠 Reasoning AI Agents
- 👁️ Multi Modal AI Agents
- 🤝 Multi Agent Collaboration
- 🎭 AI Agent Workflow
- 📚 Add Custom Knowledge
- 🧠 Agents with Short and Long Term Memory
- 📄 Chat with PDF Agents
- 💻 Code Interpreter Agents
- 📚 RAG Agents
- 🤔 Async & Parallel Processing
- 🔄 Auto Agents
- 🔢 Math Agents
- 🎯 Structured Output Agents
- 🔗 LangChain Integrated Agents
- 📞 Callback Agents
- 🤏 Mini AI Agents
- 🛠️ 100+ Custom Tools
- 📄 YAML Configuration
- 💯 100+ LLM Support

## Using Python Code

Light weight package dedicated for coding:
```bash
pip install praisonagents
```

```bash
export OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxx
```

### 1. Single Agent

Create app.py file and add the code below:
```python
from praisonagents import Agent
agent = Agent(instructions="Your are a helpful AI assistant")
agent.start("Write a movie script about a robot in Mars")
```

Run:
```bash
python app.py
```

### 2. Multi Agents

Create app.py file and add the code below:
```python
from praisonagents import Agent, praisonAgents

research_agent = Agent(instructions="Research about AI")
summarise_agent = Agent(instructions="Summarise research agent's findings")
agents = praisonAgents(agents=[research_agent, summarise_agent])
agents.start()
```

Run:
```bash
python app.py
```

## Using No Code

### Auto Mode:
```bash
pip install praison
export OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxx
praison --auto create a movie script about Robots in Mars
```

## Using JavaScript Code

```bash
npm install praison
export OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxx
```

```javascript
const { Agent } = require('praison');
const agent = new Agent({ instructions: 'You are a helpful AI assistant' });
agent.start('Write a movie script about a robot in Mars');
```

![praison CLI Demo](docs/demo/praison-cli-demo.gif)

## AI Agents Flow

```mermaid
graph LR
    %% Define the main flow
    Start([▶ Start]) --> Agent1
    Agent1 --> Process[⚙ Process]
    Process --> Agent2
    Agent2 --> Output([✓ Output])
    Process -.-> Agent1
    
    %% Define subgraphs for agents and their tasks
    subgraph Agent1[ ]
        Task1[📋 Task]
        AgentIcon1[🤖 AI Agent]
        Tools1[🔧 Tools]
        
        Task1 --- AgentIcon1
        AgentIcon1 --- Tools1
    end
    
    subgraph Agent2[ ]
        Task2[📋 Task]
        AgentIcon2[🤖 AI Agent]
        Tools2[🔧 Tools]
        
        Task2 --- AgentIcon2
        AgentIcon2 --- Tools2
    end

    classDef input fill:#8B0000,stroke:#7C90A0,color:#fff
    classDef process fill:#189AB4,stroke:#7C90A0,color:#fff
    classDef tools fill:#2E8B57,stroke:#7C90A0,color:#fff
    classDef transparent fill:none,stroke:none

    class Start,Output,Task1,Task2 input
    class Process,AgentIcon1,AgentIcon2 process
    class Tools1,Tools2 tools
    class Agent1,Agent2 transparent
```

## AI Agents with Tools

Create AI agents that can use tools to interact with external systems and perform actions.

```mermaid
flowchart TB
    subgraph Tools
        direction TB
        T3[Internet Search]
        T1[Code Execution]
        T2[Formatting]
    end

    Input[Input] ---> Agents
    subgraph Agents
        direction LR
        A1[Agent 1]
        A2[Agent 2]
        A3[Agent 3]
    end
    Agents ---> Output[Output]

    T3 --> A1
    T1 --> A2
    T2 --> A3

    style Tools fill:#189AB4,color:#fff
    style Agents fill:#8B0000,color:#fff
    style Input fill:#8B0000,color:#fff
    style Output fill:#8B0000,color:#fff
```

## AI Agents with Memory

Create AI agents with memory capabilities for maintaining context and information across tasks.

```mermaid
flowchart TB
    subgraph Memory
        direction TB
        STM[Short Term]
        LTM[Long Term]
    end

    subgraph Store
        direction TB
        DB[(Vector DB)]
    end

    Input[Input] ---> Agents
    subgraph Agents
        direction LR
        A1[Agent 1]
        A2[Agent 2]
        A3[Agent 3]
    end
    Agents ---> Output[Output]

    Memory <--> Store
    Store <--> A1
    Store <--> A2
    Store <--> A3

    style Memory fill:#189AB4,color:#fff
    style Store fill:#2E8B57,color:#fff
    style Agents fill:#8B0000,color:#fff
    style Input fill:#8B0000,color:#fff
    style Output fill:#8B0000,color:#fff
```

## AI Agents with Different Processes

### Sequential Process

The simplest form of task execution where tasks are performed one after another.

```mermaid
graph LR
    Input[Input] --> A1
    subgraph Agents
        direction LR
        A1[Agent 1] --> A2[Agent 2] --> A3[Agent 3]
    end
    A3 --> Output[Output]

    classDef input fill:#8B0000,stroke:#7C90A0,color:#fff
    classDef process fill:#189AB4,stroke:#7C90A0,color:#fff
    classDef transparent fill:none,stroke:none

    class Input,Output input
    class A1,A2,A3 process
    class Agents transparent
```

### Hierarchical Process

Uses a manager agent to coordinate task execution and agent assignments.

```mermaid
graph TB
    Input[Input] --> Manager
    
    subgraph Agents
        Manager[Manager Agent]
        
        subgraph Workers
            direction LR
            W1[Worker 1]
            W2[Worker 2]
            W3[Worker 3]
        end
        
        Manager --> W1
        Manager --> W2
        Manager --> W3
    end
    
    W1 --> Manager
    W2 --> Manager
    W3 --> Manager
    Manager --> Output[Output]

    classDef input fill:#8B0000,stroke:#7C90A0,color:#fff
    classDef process fill:#189AB4,stroke:#7C90A0,color:#fff
    classDef transparent fill:none,stroke:none

    class Input,Output input
    class Manager,W1,W2,W3 process
    class Agents,Workers transparent
```

### Workflow Process

Advanced process type supporting complex task relationships and conditional execution.

```mermaid
graph LR
    Input[Input] --> Start
    
    subgraph Workflow
        direction LR
        Start[Start] --> C1{Condition}
        C1 --> |Yes| A1[Agent 1]
        C1 --> |No| A2[Agent 2]
        A1 --> Join
        A2 --> Join
        Join --> A3[Agent 3]
    end
    
    A3 --> Output[Output]

    classDef input fill:#8B0000,stroke:#7C90A0,color:#fff
    classDef process fill:#189AB4,stroke:#7C90A0,color:#fff
    classDef decision fill:#2E8B57,stroke:#7C90A0,color:#fff
    classDef transparent fill:none,stroke:none

    class Input,Output input
    class Start,A1,A2,A3,Join process
    class C1 decision
    class Workflow transparent
```

#### Agentic Routing Workflow

Create AI agents that can dynamically route tasks to specialized LLM instances.

```mermaid
flowchart LR
    In[In] --> Router[LLM Call Router]
    Router --> LLM1[LLM Call 1]
    Router --> LLM2[LLM Call 2]
    Router --> LLM3[LLM Call 3]
    LLM1 --> Out[Out]
    LLM2 --> Out
    LLM3 --> Out
    
    style In fill:#8B0000,color:#fff
    style Router fill:#2E8B57,color:#fff
    style LLM1 fill:#2E8B57,color:#fff
    style LLM2 fill:#2E8B57,color:#fff
    style LLM3 fill:#2E8B57,color:#fff
    style Out fill:#8B0000,color:#fff
```

#### Agentic Orchestrator Worker

Create AI agents that orchestrate and distribute tasks among specialized workers.

```mermaid
flowchart LR
    In[In] --> Router[LLM Call Router]
    Router --> LLM1[LLM Call 1]
    Router --> LLM2[LLM Call 2]
    Router --> LLM3[LLM Call 3]
    LLM1 --> Synthesizer[Synthesizer]
    LLM2 --> Synthesizer
    LLM3 --> Synthesizer
    Synthesizer --> Out[Out]
    
    style In fill:#8B0000,color:#fff
    style Router fill:#2E8B57,color:#fff
    style LLM1 fill:#2E8B57,color:#fff
    style LLM2 fill:#2E8B57,color:#fff
    style LLM3 fill:#2E8B57,color:#fff
    style Synthesizer fill:#2E8B57,color:#fff
    style Out fill:#8B0000,color:#fff
```

#### Agentic Autonomous Workflow

Create AI agents that can autonomously monitor, act, and adapt based on environment feedback.

```mermaid
flowchart LR
    Human[Human] <--> LLM[LLM Call]
    LLM -->|ACTION| Environment[Environment]
    Environment -->|FEEDBACK| LLM
    LLM --> Stop[Stop]
    
    style Human fill:#8B0000,color:#fff
    style LLM fill:#2E8B57,color:#fff
    style Environment fill:#8B0000,color:#fff
    style Stop fill:#333,color:#fff
```

#### Agentic Parallelization

Create AI agents that can execute tasks in parallel for improved performance.

```mermaid
flowchart LR
    In[In] --> LLM2[LLM Call 2]
    In --> LLM1[LLM Call 1]
    In --> LLM3[LLM Call 3]
    LLM1 --> Aggregator[Aggregator]
    LLM2 --> Aggregator
    LLM3 --> Aggregator
    Aggregator --> Out[Out]
    
    style In fill:#8B0000,color:#fff
    style LLM1 fill:#2E8B57,color:#fff
    style LLM2 fill:#2E8B57,color:#fff
    style LLM3 fill:#2E8B57,color:#fff
    style Aggregator fill:#fff,color:#000
    style Out fill:#8B0000,color:#fff
```

#### Agentic Prompt Chaining

Create AI agents with sequential prompt chaining for complex workflows.

```mermaid
flowchart LR
    In[In] --> LLM1[LLM Call 1] --> Gate{Gate}
    Gate -->|Pass| LLM2[LLM Call 2] -->|Output 2| LLM3[LLM Call 3] --> Out[Out]
    Gate -->|Fail| Exit[Exit]
    
    style In fill:#8B0000,color:#fff
    style LLM1 fill:#2E8B57,color:#fff
    style LLM2 fill:#2E8B57,color:#fff
    style LLM3 fill:#2E8B57,color:#fff
    style Out fill:#8B0000,color:#fff
    style Exit fill:#8B0000,color:#fff
```

#### Agentic Evaluator Optimizer

Create AI agents that can generate and optimize solutions through iterative feedback.

```mermaid
flowchart LR
    In[In] --> Generator[LLM Call Generator] 
    Generator -->|SOLUTION| Evaluator[LLM Call Evaluator] -->|ACCEPTED| Out[Out]
    Evaluator -->|REJECTED + FEEDBACK| Generator
    
    style In fill:#8B0000,color:#fff
    style Generator fill:#2E8B57,color:#fff
    style Evaluator fill:#2E8B57,color:#fff
    style Out fill:#8B0000,color:#fff
```

#### Repetitive Agents

Create AI agents that can efficiently handle repetitive tasks through automated loops.

```mermaid
flowchart LR
    In[Input] --> LoopAgent[("Looping Agent")]
    LoopAgent --> Task[Task]
    Task --> |Next iteration| LoopAgent
    Task --> |Done| Out[Output]
    
    style In fill:#8B0000,color:#fff
    style LoopAgent fill:#2E8B57,color:#fff,shape:circle
    style Task fill:#2E8B57,color:#fff
    style Out fill:#8B0000,color:#fff
```

## Adding Models

<div align="center">
  <a href="https://docs.praisonlabs.com" target="_blank">
    <p align="center">
      <img src="https://img.shields.io/badge/📚_Documentation-Visit_docs.praison.ai-blue?style=for-the-badge&logo=bookstack&logoColor=white" alt="Documentation" />
    </p>
  </a>
</div>

## Ollama Integration
```bash
export OPENAI_BASE_URL=http://localhost:11434/v1
```

## Groq Integration
Replace xxxx with Groq API KEY:
```bash
export OPENAI_API_KEY=xxxxxxxxxxx
export OPENAI_BASE_URL=https://api.groq.com/openai/v1
```

## No Code Options

## Agents Playbook

### Simple Playbook Example

Create `agents.yaml` file and add the code below:

```yaml
framework: praison
topic: Artificial Intelligence
roles:
  screenwriter:
    backstory: "Skilled in crafting scripts with engaging dialogue about {topic}."
    goal: Create scripts from concepts.
    role: Screenwriter
    tasks:
      scriptwriting_task:
        description: "Develop scripts with compelling characters and dialogue about {topic}."
        expected_output: "Complete script ready for production."
```

*To run the playbook:*
```bash
praison agents.yaml
```

## Use 100+ Models

- https://docs.praisonlabs.com/models/
<div align="center">
  <a href="https://docs.praisonlabs.com" target="_blank">
    <p align="center">
      <img src="https://img.shields.io/badge/📚_Documentation-Visit_docs.praison.ai-blue?style=for-the-badge&logo=bookstack&logoColor=white" alt="Documentation" />
    </p>
  </a>
</div>

## Development:

Below is used for development only.

### Using uv
```bash
# Install uv if you haven't already
pip install uv

# Install from requirements
uv pip install -r pyproject.toml

# Install with extras
uv pip install -r pyproject.toml --extra code
uv pip install -r pyproject.toml --extra "crewai,autogen"
```

## Contributing

- Fork on GitHub: Use the "Fork" button on the repository page.
- Clone your fork: `git clone https://github.com/yourusername/praison.git`
- Create a branch: `git checkout -b new-feature`
- Make changes and commit: `git commit -am "Add some feature"`
- Push to your fork: `git push origin new-feature`
- Submit a pull request via GitHub's web interface.
- Await feedback from project maintainers.

## Other Features

- 🔄 Use CrewAI or AG2 (Formerly AutoGen) Framework
- 💻 Chat with ENTIRE Codebase
- 🎨 Interactive UIs
- 📄 YAML-based Configuration
- 🛠️ Custom Tool Integration
- 🔍 Internet Search Capability (using Crawl4AI and Tavily)
- 🖼️ Vision Language Model (VLM) Support
- 🎙️ Real-time Voice Interaction
