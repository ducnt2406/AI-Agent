# 🤖 Google ADK Sequential Agent Pipeline Example

This project demonstrates a sequential multi-agent workflow using the **Google Agent Development Kit (ADK)**. A **Draft Writer Agent** generates initial content, followed by a **Fact Checker Agent** that reviews the content for accuracy in an automated pipeline.

---

## 🚀 Getting Started

### 1. Prerequisites

* **Python 3.9+**
* A **Google API Key** for accessing the Gemini API.
* Google-ADK library installed

### 2. API Key Configuration
The code requires your Google API Key to authenticate API calls.

**Recommended Method: Environment Variable**

Set the `GOOGLE_API_KEY` environment variable in your terminal before running the script:

* **Linux/macOS:**
    ```bash
    export GOOGLE_API_KEY="YOUR_API_KEY_HERE"
    ```
* **Windows (PowerShell):**
    ```powershell
    $env:GOOGLE_API_KEY="YOUR_API_KEY_HERE"
    ```

or create the .env file with GOOGLE_API_KEY outside.

---

## ▶️ How to Run the Code

1.  **Save the Code:** Save the provided Python code into a file named `04-reflection-google-adk.py`.

2.  **Execute the Script:** Run the file from your terminal:

    ```bash
    python 04-reflection-google-adk.py
    ```

### 3. Execution Flow and Pipeline

The script runs test requests to showcase the sequential agent pipeline:

| Request | Agent 1 | Agent 2 | Output |
| :--- | :--- | :--- | :--- |
| `A mug that keeps coffee hot and can be controlled by a smartphone app` | `DraftWriter` → generates content | `FactChecker` → validates content | Structured review with status & reasoning |
| `Explain how solar panels work for home electricity` | `DraftWriter` → generates content | `FactChecker` → validates content | Accuracy assessment with detailed reasoning |