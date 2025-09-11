# Data-Analyst-Assistant
This project is an agentic AI application designed to help students analyze datasets and generate reports with actionable insights. Using Python and the LangChain framework (or similar concepts), the agent can perceive a user's request, plan a series of data analysis steps, and execute them using specialized tools.

# Key Features
Perceive: Understands user requests about a dataset (e.g., "Find the top-performing region").

Plan: Autonomously breaks down the request into a series of logical data processing steps.

Act: Executes a series of actions using internal tools (e.g., a CSV loader, a Python code interpreter for data manipulation and visualization).

Report: Generates a clean, readable Markdown report with findings and visualizations.

# How It Works (Conceptual)
- A user provides a CSV file and a question.

- The agent parses the question and identifies the core task.

- It selects the appropriate "tools" to complete the task.

- The agent's internal "reasoning engine" decides the sequence of tool usage. For example: [load_csv] -> [find_top_regions] -> [generate_report].

- The final report is presented to the user.

## Documentation

For detailed user-system interaction and agent roles, see:  
➡ [Interaction Guide](docs/Interaction.md)
