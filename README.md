# Financial Analyst – DeepSeek (MCP Powered)

Financial Analyst – DeepSeek is a local, multi-agent system built using the Modular Command Platform (MCP). It enables natural language-driven financial analysis by leveraging CrewAI agents and running a local DeepSeek-R1 language model through Docker-hosted Ollama.

This project converts natural language queries into Python code that retrieves, analyzes, and visualizes stock market data, then securely executes the code and returns the results.

---

## Features

- Natural language interface for financial data analysis
- Modular, agent-based architecture using CrewAI:
  - Query Parser Agent – interprets natural language queries
  - Code Writer Agent – generates Python code for analysis and plotting
  - Code Executor Agent – safely executes code in a sandbox
- Fully local LLM inference using DeepSeek-R1 via Docker-hosted Ollama
- Chart generation with `pandas`, `yfinance`, and `matplotlib`
- Runs locally using the MCP runtime

---

### Prerequisites

- Python 3.10+
- Visual Studio Code
- Docker
- [Ollama](https://ollama.com) installed and running via Docker
- `uv` for running the MCP server (or use pip)

To start Ollama with DeepSeek-R1 in Docker:

```bash
docker run -it -p 11434:11434 --name give_name ollama/ollama
docker_terminal:
    ollama pull deepseek-r1
    exit
````

> Ensure the Ollama server is up and listening on `localhost:11434`

---

### Install Dependencies

Install Python dependencies using `uv`:

```bash
uv pip install -r requirements.txt
```
---

### Running the MCP Server

You can run the server directly from VS Code terminal:

```bash
uv --directory /absolute/path/to/financial-analyst-deepseek run server.py
```

This will launch the MCP server that manages the CrewAI agents and handles user queries.

---

## Example Query

Query:

```
Plot year-to-date performance for AAPL and MSFT
```

The system will:

1. Parse the query into structured instructions
2. Generate Python code to fetch stock data using `yfinance`
3. Plot the result using `matplotlib`
4. Execute the code and return the image output

---

## Example Output

*Insert a sample output chart below*

![Example Chart](screenshots/example_plot.png)

---

## Use Cases

* Stock performance analysis and visualization
* Equity comparisons
* Interactive financial reporting
* Demonstrations of multi-agent and LLM-based systems

---

## Technologies Used

* Python
* CrewAI
* Modular Command Platform (MCP)
* DeepSeek-R1 (hosted via Docker and Ollama)
* pandas, matplotlib, yfinance