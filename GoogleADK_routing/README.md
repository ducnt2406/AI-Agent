# 🤖 Google ADK Agent Coordinator and Delegation Example

This project demonstrates a multi-agent routing pattern using the **Google Agent Development Kit (ADK)**. A primary **Coordinator Agent** analyzes user intent and delegates the task to one of two specialized **Sub-Agents** (`Booker` or `Info`) based on the request.

---

## 🚀 Getting Started

### 1. Prerequisites

* **Python 3.9+**
* A **Google API Key** for accessing the Gemini API.

### 2. Installation

Install the required Python packages:

```bash
pip install google-adk nest-asyncio
```

### 3. API Key Configuration
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

> **Note:** The line `os.environ['GOOGLE_API_KEY'] = 'GOOGLE_API_KEY'` in the Python file is a placeholder. For successful execution, ensure your actual key is set via the environment variable method above.

---

## ▶️ How to Run the Code

1.  **Save the Code:** Save the provided Python code into a file named `coordinator_example.py`.

2.  **Execute the Script:** Run the file from your terminal:

    ```bash
    python coordinator_example.py
    ```

### Execution Flow and Delegation

The script runs four test requests to showcase automatic delegation:

| Request | Target Agent | Tool Called |
| :--- | :--- | :--- |
| `Book me a hotel in Paris.` | `Booker` | `booking_handler` |
| `Find flights to Tokyo next month.` | `Booker` | `booking_handler` |
| `What is the highest mountain in the world?` | `Info` | `info_handler` |
| `Tell me a random fact.` | `Info` | `info_handler` |

The output will clearly show when the specialized handler functions are called:

```text
--- Google ADK Routing Example (ADK Auto-Flow Style) ---
Note: This requires Google ADK installed and authenticated.

--- Running Coordinator with request: 'Book me a hotel in Paris.' ---
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
-------------------------- Booking Handler Called ----------------------------
Coordinator Final Response: OK. I have booked a hotel for you in Paris.

Final Output A: OK. I have booked a hotel for you in Paris.


--- Running Coordinator with request: 'What is the highest mountain in the world?' ---
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
-------------------------- Info Handler Called ----------------------------
Coordinator Final Response: The highest mountain in the world is Mount Everest.

Final Output B: The highest mountain in the world is Mount Everest.


--- Running Coordinator with request: 'Tell me a random fact.' ---
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
-------------------------- Info Handler Called ----------------------------
Coordinator Final Response: I have retrieved a random fact for you. The average person spends six months of their life waiting for red lights to turn green.

Final Output C: I have retrieved a random fact for you. The average person spends six months of their life waiting for red lights to turn green.


--- Running Coordinator with request: 'Find flights to Tokyo next month.' ---
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
Warning: there are non-text parts in the response: ['function_call'], returning concatenated text result from text parts. Check the full candidates.content.parts accessor to get the full model response.
-------------------------- Booking Handler Called ----------------------------
Coordinator Final Response: OK. I have simulated booking flights to Tokyo next month.

Final Output D: OK. I have simulated booking flights to Tokyo next month.