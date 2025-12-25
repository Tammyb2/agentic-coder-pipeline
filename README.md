LangGraph Engineer
LangGraph Engineer is an automated software development pipeline that leverages a multi-agent system to transform high-level user requirements into functional code. By utilizing a specialized Planner-Architect-Coder workflow, the system ensures that complex requests are broken down into logical engineering tasks before implementation begins.

🤖 The Agent Trio
The system orchestrates three distinct personas to manage the development lifecycle:

The Planner: Analyzes the user's initial prompt to define the project scope, tech stack, and necessary file structure.

The Architect: Takes the high-level plan and decomposes it into a sequence of granular, dependency-aware implementation tasks.

The Coder: An iterative agent that executes the implementation tasks one by one, using ReAct logic to read and write files within the project directory.

🛠 Features
Structured State Management: Uses Pydantic models to ensure strict data validation during agent hand-offs.

Safety Sandboxing: All file operations are restricted to a generated_project/ directory to prevent unauthorized system access.

Iterative Implementation: The Coder agent maintains a stateful index, allowing it to work through complex projects step-by-step rather than all at once.

Tool Integration: Includes built-in tools for reading/writing files, listing directories, and running shell commands.

🚀 Getting Started
Prerequisites
Python 3.9+

A Groq API Key (configured in your .env file)

Installation
Clone the repository:

Bash

git clone https://github.com/Tammyb2/langgraph-engineer.git
cd langgraph-engineer
Install dependencies:

Bash

pip install langgraph langchain-groq pydantic python-dotenv
Usage
Run the main entry point and provide a prompt when requested:

Bash

python main.py
Example prompt: "Create a simple calculator web application using Flask."

📂 Project Structure
graph.py: Defines the LangGraph state machine and agent nodes.

states.py: Contains Pydantic schemas for project plans and agent states.

tools.py: Provides the filesystem and shell tools used by the Coder.

prompts.py: Houses the specialized system instructions for each agent.

