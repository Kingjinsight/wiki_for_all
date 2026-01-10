# Agents Theorem

Agents' work is a continuous cycle of: **Thought** -> **Action** and **Observing**.

1. Thought: The LLM part of the Agent decides what the next step should be
2. Action: The agent takes an action by calling the tools with the associated arguments
3. Observation: The model reflects on the response from the tool.

## **Tools**:

A tool is a function given to the LLM. When the LLM calls a tool, it needs to understand how to use it. Therefore, we provide tool information through a tools parameter (not system message). For example:

```json
{
  "name": "calculator",
  "description": "Multiply two integers",
  "parameters": {
    "type": "object",
    "properties": {
      "a": {"type": "integer"},
      "b": {"type": "integer"}
    }
  }
}
```

When we write tools in Python, we often create a tool class and use decorators to register new tools. We typically write schema conversion methods like to_openai_schema() or to_anthropic_schema() to generate tool definitions for different LLM providers.

However, different LLM providers have different tool calling formats and protocols. This creates several problems:

- **Schema format differences**: Each provider requires different JSON structures
- **Execution model differences**: Tool developers must write adapter code for each LLM
- **Maintenance burden**: One tool needs multiple implementations

This is where MCP (Model Context Protocol) comes in. Tool providers only need to develop one MCP server and deploy it. The MCP server:

- Defines tools using a standardized schema
- Hosts and executes the tools itself
- Communicates with LLMs thorugh a unified protocol

LLMs that implement the MCP client protocol can call these tools directly without requiring tool provider to write provider-specific adapters.

## **Thought**

Common Thought Types:

1. Planning
2. Analysis
3. Decision Making
4. Problem Solving
5. Memory Integration
6. Self-Reflection
7. Goal Setting
8. Prioritization

**Chain-of-Thought**: It is a prompting technique that guides a model to think through a problem step-by-step before producing a final answer. It typically starts with: `Let's think step by step.`

**ReAct: Reasoning + Acting**: It is also a prompting technique that encourages the model to think step-by-step and interleave actions between reasoning steps. Such as

```Text
Thought: I need to find the latest weather in Paris.
Action: Search["weather in Paris"]
Observation: It's 18°C and cloudy.
Thought: Now that I know the weather...
Action: Finish["It's 18°C and cloudy in Paris."]
```

**Internalized CoT**: It is a training-level techniques, where the model learns to think via examples, they use structured tokens like <think> and </think> to explicitly separate the reasoning phse from the final answer.

## **Types of Agent**

- JSON Agent: The action to take is specified in JSON format
- Code Agent: The Agent writes a code block that is interpreted externally
    - Code can natually represent complex logic
    - Generated code can be reused across different actions or tasks
    - With a well-defined programming syntax, code errors are often easier to detect and correct
    - Code agents can integrate directly with external libraries and APIs
![code agent](../images/code_agent.png)
- Function-calling Agent: It is a subcategory of the JSON Agent which has been fine-tuned to generate a new message for each action

## **Type of Actions**

- Information Gathering: Performing web searches, querying databases or retrieving documents
- Tool Usage: Making API calls, running calculations and executing codes
- Environment Interaction: Manipulating digital interfaces or controlling phuysical devices
- Communication: Engaging with users via chat or collaborating with other agents

## **Type of Observation**

- System Feedback
- Data Changes
- Environmental Data
- Response Analysis
- Time-based Events

