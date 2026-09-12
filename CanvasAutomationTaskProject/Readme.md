# Canvas Automation Task Project

This directory contains the scripts and configuration needed to automatically check Canvas for updates and send notifications via Telegram.

## 📂 Project Structure

*   **`canvasautomationtaskproject_v1_2.py`**: The main script that checks Canvas for specific tasks/updates and triggers notifications.
*   **`google_tasks_manager.py`**: Handles interactions with Google Tasks (if applicable to your workflow).
*   **`get_refresh_token.py`**: A utility script used to generate or refresh the necessary Google API tokens.
*   **`telegram_sender.py`**: A module dedicated to formatting and sending messages to your Telegram bot.
*   **`requirements.txt`**: A list of Python dependencies required to run these scripts.

## ⚙️ How it Works (GitHub Actions)

The execution of these scripts is automated via a GitHub Action located at `.github/workflows/canvas_check.yml` at the root of the repository. 

The workflow performs the following steps:
1.  Sets up a Python 3.11 environment.
2.  Installs the necessary dependencies from `requirements.txt`.
3.  Executes the main script (`canvasautomationtaskproject_v1_2.py`) twice daily (10:00 AM and 10:00 PM Peru Time).

## 🔐 Environment Variables & Secrets

The scripts rely on several sensitive credentials to function. These are **not** stored in this repository. Instead, they are securely managed via GitHub Repository Secrets and passed to the script at runtime.

To run these scripts locally or configure the workflow, you must provide the following environment variables:

| Variable | Description |
| :--- | :--- |
| `CANVAS_URL` | The base URL for your Canvas institution. |
| `CANVAS_KEY` | Your personal Canvas API access token. |
| `TELEGRAM_BOT_TOKEN` | The API token for your Telegram bot. |
| `TELEGRAM_CHAT_ID` | The ID of the Telegram chat/user to receive notifications. |

*(Note: If your Google Tasks scripts require environment variables, be sure to add them to this list and to your GitHub Secrets).*

## 🚀 Running Locally (Development)

If you need to test the scripts locally on your machine:

1.  Navigate to this folder:
    ```bash
    cd "Canvas AutomationTask Project"
