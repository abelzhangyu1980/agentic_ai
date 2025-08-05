Vertex AI Agent Builder helps you turn your processes into multi-agent experiences by building on them, and not disrupting them–regardless of where you stand in your AI journey or which technology stack you've chosen.

Agent Development Kit (ADK) is a flexible and modular framework for developing and deploying AI agents

Agents¶
In the Agent Development Kit (ADK), an Agent is a self-contained execution unit designed to act autonomously to achieve specific goals. Agents can perform tasks, interact with users, utilize external tools, and coordinate with other agents.

The foundation for all agents in ADK is the BaseAgent class. It serves as the fundamental blueprint. To create functional agents, you typically extend BaseAgent in one of three main ways, catering to different needs – from intelligent reasoning to structured process control.

  ![agent](agent-types.png)
Core Agent Categories¶
ADK provides distinct agent categories to build sophisticated applications:

LLM Agents (LlmAgent, Agent): These agents utilize Large Language Models (LLMs) as their core engine to understand natural language, reason, plan, generate responses, and dynamically decide how to proceed or which tools to use, making them ideal for flexible, language-centric tasks. Learn more about LLM Agents...

Workflow Agents (SequentialAgent, ParallelAgent, LoopAgent): These specialized agents control the execution flow of other agents in predefined, deterministic patterns (sequence, parallel, or loop) without using an LLM for the flow control itself, perfect for structured processes needing predictable execution. Explore Workflow Agents...

Custom Agents: Created by extending BaseAgent directly, these agents allow you to implement unique operational logic, specific control flows, or specialized integrations not covered by the standard types, catering to highly tailored application requirements. Discover how to build Custom Agents...

The following table provides a high-level comparison to help distinguish between the agent types. As you explore each type in more detail in the subsequent sections, these distinctions will become clearer.


Agents Working Together: Multi-Agent Systems¶
While each agent type serves a distinct purpose, the true power often comes from combining them. Complex applications frequently employ multi-agent architectures where:

- LLM Agents handle intelligent, language-based task execution.
- Workflow Agents manage the overall process flow using standard patterns.
- Custom Agents provide specialized capabilities or rules needed for unique integrations.
Understanding these core types is the first step toward building sophisticated, capable AI applications with ADK.

## LLM Agent
The LlmAgent (often aliased simply as Agent) is a core component in ADK, acting as the "thinking" part of your application. It leverages the power of a Large Language Model (LLM) for reasoning, understanding natural language, making decisions, generating responses, and interacting with tools.

Building an effective LlmAgent involves defining its identity, clearly guiding its behavior through instructions, and equipping it with the necessary tools and capabilities.

### Defining the Agent's Identity and Purpose¶
First, you need to establish what the agent is and what it's for.

- name (Required): Every agent needs a unique string identifier. This name is crucial for internal operations, especially in multi-agent systems where agents need to refer to or delegate tasks to each other. Choose a descriptive name that reflects the agent's function (e.g., customer_support_router, billing_inquiry_agent). Avoid reserved names like user.

- description (Optional, Recommended for Multi-Agent): Provide a concise summary of the agent's capabilities. This description is primarily used by other LLM agents to determine if they should route a task to this agent. Make it specific enough to differentiate it from peers (e.g., "Handles inquiries about current billing statements," not just "Billing agent").

- model (Required): Specify the underlying LLM that will power this agent's reasoning. This is a string identifier like "gemini-2.0-flash". The choice of model impacts the agent's capabilities, cost, and performance. See the Models page for available options and considerations.

Example: Defining the basic identity
capital_agent = LlmAgent(
    model="gemini-2.0-flash",
    name="capital_agent",
    description="Answers user questions about the capital city of a given country."
    # instruction and tools will be added next
)

### Guiding the Agent: Instructions
The instruction parameter is arguably the most critical for shaping an LlmAgent's behavior. It's a string (or a function returning a string) that tells the agent:

- Its core task or goal.
- Its personality or persona (e.g., "You are a helpful assistant," "You are a witty pirate").
- Constraints on its behavior (e.g., "Only answer questions about X," "Never reveal Y").
- How and when to use its tools. You should explain the purpose of each tool and the circumstances under which it should be called, supplementing any descriptions within the tool itself.
- The desired format for its output (e.g., "Respond in JSON," "Provide a bulleted list").

Tips for Effective Instructions:

- Be Clear and Specific: Avoid ambiguity. Clearly state the desired actions and outcomes.
- Use Markdown: Improve readability for complex instructions using headings, lists, etc.
- Provide Examples (Few-Shot): For complex tasks or specific output formats, include examples directly in the instruction.
- Guide Tool Use: Don't just list tools; explain when and why the agent should use them.

State:

The instruction is a string template, you can use the {var} syntax to insert dynamic values into the instruction.
{var} is used to insert the value of the state variable named var.
{artifact.var} is used to insert the text content of the artifact named var.
If the state variable or artifact does not exist, the agent will raise an error. If you want to ignore the error, you can append a ? to the variable name as in {var?}.

Example: Adding instructions
capital_agent = LlmAgent(
    model="gemini-2.0-flash",
    name="capital_agent",
    description="Answers user questions about the capital city of a given country.",
    instruction="""You are an agent that provides the capital city of a country.
When a user asks for the capital of a country:
1. Identify the country name from the user's query.
2. Use the `get_capital_city` tool to find the capital.
3. Respond clearly to the user, stating the capital city.
Example Query: "What's the capital of {country}?"
Example Response: "The capital of France is Paris."
""",
    tools will be added next
)

### Equipping the Agent: Tools
Tools give your LlmAgent capabilities beyond the LLM's built-in knowledge or reasoning. They allow the agent to interact with the outside world, perform calculations, fetch real-time data, or execute specific actions.

tools (Optional): Provide a list of tools the agent can use. Each item in the list can be:
A native function or method (wrapped as a FunctionTool). Python ADK automatically wraps the native function into a FuntionTool whereas, you must explicitly wrap your Java methods using FunctionTool.create(...)
An instance of a class inheriting from BaseTool.
An instance of another agent (AgentTool, enabling agent-to-agent delegation - see Multi-Agents).
The LLM uses the function/tool names, descriptions (from docstrings or the description field), and parameter schemas to decide which tool to call based on the conversation and its instructions.

## Multi-Agent System (MAS).



