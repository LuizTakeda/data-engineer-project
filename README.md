# NorthMart Data Platform

This repository contains the practical assignments for the Data Engineering course (2026/2027) at Universidade Politécnica Bragança. The project entails building an end-to-end data platform for NorthMart, an online marketplace, utilizing the Brazilian E-Commerce Public Dataset by Olist.

The project is structured into three iterative Practical Assignments (PAs). This document outlines the setup procedures, the commands required to reproduce the execution of each assignment, and placeholders for the mandatory written answers.

## Setup Instructions

1. Create and activate a Python virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

2. Install the necessary dependencies:

   ```bash
   pip install -r requirements.txt
   ```

   *Note: Apache Airflow (introduced in PA2) does not run natively on Windows. It is recommended to use WSL2 or a Linux-based lab machine.*

3. Data Preparation:
   Download the Olist dataset from Kaggle and the NorthMart seller profiles JSON file. Unzip and place all source files into the `data/source/` directory. Do not commit these files to version control.

---

## PA1: Storage Formats and Analytical Modelling

This section covers the transition of raw CSV and JSON exports into a dimensional star schema, queried with DuckDB and persisted in Parquet format.

### Commands to Reproduce

*Note: Replace the generic commands below with the exact commands used by the group.*

- **Data Profiling**:

  ```bash
  duckdb < sql/profiling.sql
  ```

- **Build and Load Model**:

  ```bash
  duckdb < sql/build_model.sql
  ```

### Written Answers

#### Task 1: Data Profiling Findings

- [Finding 1]
- [Finding 2]
- [Finding 3]
- [Finding 4 (JSON-related)]
- [Finding 5 (JSON-related)]

**Task 5: Architecture Recommendation (Max 150 words)**
*Would NorthMart be better served by a data warehouse, a data lake, or a lakehouse? Justify with two facts from your own measurements.*

- [Insert answer here]

---

## PA2: Orchestrated and Tested ELT Pipeline

This section automates the data ingestion and transformation processes via a daily ELT pipeline, utilizing a REST API, dbt for transformations, and Apache Airflow for orchestration.

### Commands to Reproduce

1. **Start the Mock API (Local)**:

   ```bash
   uvicorn mock_api:app --port 8000
   ```

2. **Execute the Airflow Pipeline and dbt Tests**:

   ```bash
   # Provide the specific Airflow and dbt commands to trigger the backfill and run tests.
   ```

### Written Answers

**Task 5: Incident Handling**
*Identify the corrupted day from the test results, show that the DAG failed before the marts were updated, and describe in five lines how the batch should be handled.*

- [Insert answer here]

**Task 6: Pipeline Optimization (Max 100 words)**
*Name the slowest task of the DAG from the Airflow task durations and propose one optimization.*

- [Insert answer here]

---

## PA3: Data Protection and Tool Exploration

This section addresses data privacy requirements (GDPR) via anonymization and erasure mechanisms, and includes hands-on experimentation with a novel data engineering tool.

### Commands to Reproduce

- **Data Erasure Script**:

   ```bash
   # Provide the command to execute the customer erasure procedure.
   ```

- **Tool Exploration Example**:

   ```bash
   # Provide the command to run the minimal working example of the explored tool.
   ```

### Written Answers

**Part A, Task 2: Protection in the Pipeline**
*Explain why the result is anonymized and not anonymized (regarding the hashed identifiers and location vs. dropped free-text fields).*

- [Insert answer here]

**Part B, Task 5: Experiment Execution and Results**
*Short log of what you tried, what failed, and how you solved it. Report the result of the small experiment with its numbers or outputs.*

- [Insert answer here]

**Part B, Task 6: Tool Evaluation (Max 300 words)**
*What the tool is for, when it should not be used, what it costs in complexity, and whether NorthMart should adopt it now.*

- [Insert answer here]
