# Data-Analyst-Assistant

This project is an **agentic AI application** designed to help students analyze datasets and generate reports with actionable insights.  
It uses **Python** and frameworks like **LangChain** (or similar concepts) to perceive a user’s request, plan a series of analysis steps, and execute them with specialized agents.

---

## Goal

This page covers the **overall user-agent interaction** for the Data Analyst Assistant.

---

## Happy Path

**User:** (Uploads a CSV file and asks)  
*"Find the top-performing region."*

**AI:** (Thinking...)  
1. The system will load the CSV file.  
2. The system will analyze the sales by region.  
3. The system will identify the top-performing region.  
4. The system will generate a Markdown report with insights and visualizations.  
5. The system will present the report to the user.  

**AI Output:**  
*"The top-performing region is North America. A full report has been generated."*

---

## Detailed Agent Breakdown

### Planner Agent

#### Role  
Make a **plan** using the available agents to service the user’s request. Powered by an **LLM**.

#### Responsibilities  
- Ask the user for clarification on ambiguous requests.  
- Present the plan to the user for approval & edits.  
- Prepare a detailed multi-step execution plan.  
- Invoke the specialized agents in the correct order.  
- Inform the user about the final successful output.  
- Report errors if the plan fails at any stage.  

#### Tools  
- Access to **Pre-curated Plans** (for common tasks).  
- Ability to **invoke other agents** as functions/tools.  
- Ability to **interact with the user** (clarification, updates).  

---

### CSV Loader Agent

#### Role  
Safely load CSV data into the system for further analysis.  

#### Responsibilities  
- Read the file from the specified path.  
- Handle errors (e.g., missing file, bad formatting).  
- Return a structured **pandas DataFrame** to the Planner.  

#### Tools  
- **Pandas** for CSV ingestion.  
- **File System Access** to fetch local or cloud-stored files.  

---

### Data Analysis Agent

#### Role  
Perform the actual **data computations and transformations** requested by the Planner.  

#### Responsibilities  
- Filter, group, and aggregate data.  
- Run statistical analysis (averages, standard deviations, correlations).  
- Identify key insights (top values, trends, anomalies).  

#### Tools  
- **Pandas** for data manipulation.  
- **Matplotlib / Seaborn** for data visualization.  

---

### Report Generation Agent

#### Role  
Generate a **human-readable report** from the analysis.  

#### Responsibilities  
- Construct a clean **Markdown document**.  
- Embed charts and graphs as images.  
- Write concise **summaries of findings**.  
- Save the final report to disk.  

#### Tools  
- **Markdown Formatter**.  
- **File System Access** to save reports.  

---

