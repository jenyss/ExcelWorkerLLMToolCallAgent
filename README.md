# Excel Worker LLM Tool Call AI Agent

This Agent enabling analysis of Excel files using free-form queries as user input.

If you have any questions or would like to collaborate, feel free to reach out to me on [LinkedIn](https://www.linkedin.com/in/jenya-stoeva-60477249/). You're more than welcome!

**Core Architecture**
* State-based agent using StateGraph pattern for workflow control
* OpenAI GPT-4o model for query generation and validation
* Two-node system: query generation and validation nodes
* Type-safe state management with AgentState TypedDict

**Main Tools**
* load_preview_data: Excel structure analysis and metadata extraction
* complex_duckdb_query: SQL operations with DuckDB connection
* simple_dataframe_query: Pandas operations with safe eval environment

**Key Features**
* **State Management:**
  * Tracks query execution, validation states
  * Manages conversation history
  * Thread-safe checkpointing
  * Error propagation and recovery

* **Tool Orchestration:**
  * Dynamic tool selection by LLM
  * Parallel tool execution capability
  * Safety limits: max 3 calls per tool
  * Automatic tool argument injection
  * Tool result validation

* **Data Processing:**
  * Excel file structure analysis
  * SQL query execution via DuckDB
  * Pandas operations in a safe environment
  * Null/NaN value handling
  * Data type preservation

* **Control Flow:**
  * Two-stage validation pipeline
  * Max 7 iterations per query
  * Conditional edge routing
  * State-based decision making


## Intallation

<b>Prerequisites</b>

* Access to <b>JupyterLab, Google Colab</b>, or another interactive computing environment to run this Jupyter Notebook.
* Access to LLM API.

### Step 1: Clone the Repository

Clone this repository to your local machine:
```
git clone <REPOSITORY_URL>
cd <PROJECT_FOLDER>
```

### Step 2: Open Jupyter Notebook in JupyterLab

Ensure that ```<PROJECT_FOLDER>``` is accessible in JupyterLab by setting it as your working directory in JupyterLab.
 * In JupyterLab, use the "Open from Path" option to load ```ExcelWorkerLLMToolCallAgent.ipynb```.
 * Similarly, load ```.env``` and populate the variable keys with appropriate values.
 * The first cell in the Notebook installs the required libraries: **%pip install langchain langgraph pandas python-dotenv duckdb**

### Step 3: Run the Jupyter Notebook

To execute the notebook, select each cell and press ```Shift + Enter```.
