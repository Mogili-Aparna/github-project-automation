# TaskGenie ✨

TaskGenie is an automation tool that creates **GitHub Project boards** (Kanban style) and fills them with issues, labels, and status columns automatically — perfect for study checklists, project backlogs, or onboarding tasks.

---

## 🚀 Features
- Create GitHub labels automatically.
- Add issues (tasks) in bulk from resource files.
- Create project boards with custom columns (`To Do`, `In Progress`, `Completed`, etc.).
- Assign issues to the correct column on creation.
- Logs actions and errors for easy debugging.

---

## 🗂️ Project Structure
```
github-project-automation/
│── resources/ # Define labels, issues, columns for different boards
│ └── rest_api/
│ ├── projectBoard.py # project metadata (future use)
│ ├── columns.py # Kanban column definitions
│ ├── labels.py # labels for issues
│ └── issues.py # task list
│
│── src/
│ ├── github_api.py # GraphQL helper
│ ├── label_manager.py # create and manage labels
│ ├── issue_manager.py # create issues
│ ├── project_manager.py # create columns and add issues to project
│ └── utils.py # (optional) helpers
│
│── config.py # GitHub token, repo info
│── main.py # CLI entry point
│── requirements.txt
│── logs/app.log
```

---

## ⚙️ Setup

1. ### **Clone the repo**
   ```bash
   git clone https://github.com/<your-username>/TaskGenie.git
   cd TaskGenie
   ```
2. ### **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```
3. ### **Set your GitHub Personal Access Token**
   * Create a PAT from GitHub with repo + project permissions.
   * Add it to config.py:
   ```python
    GITHUB_TOKEN = "your-token-here"
   ```
5. ### **Configure your repo/project in config.py**
    ```python
    REPO_OWNER = "Mogili-Aparna"
    REPO_NAME = "REST-APIs"
    PROJECT_ID = "your-project-id"
    ```
6. ### **▶️ Usage**
  Run the script with the resource of your choice:
  ```python
    python main.py --resource rest_api
  ```
    This will:
    * Create labels from resources/rest_api/labels.py
    * Create issues from resources/rest_api/issues.py
    * Add columns from resources/rest_api/columns.py
    * Populate your GitHub Project board automatically 🎉
8. ### 💡 Example Use Cases
    * Study checklists (APIs, DSA, System Design, etc.)
    * Project backlog automation
    * Onboarding checklist for new developers
    * Bug triage boards
9. ### 🛠️ Roadmap
    - [x] Setup basic project structure
    - [x] Automate label creation
    - [x] Automate issue creation from task lists
    - [x] Add issues to GitHub Project board
    - [ ] Auto-create Kanban columns (To Do, In Progress, etc.)
    - [ ] Load resources dynamically (APIs, DSA, System Design, etc.)
    - [ ] Improve logging and exception handling
    - [ ] Add CLI options for repo/owner/project configuration
    - [ ] Support multiple boards per repo
    - [ ] Add UI for task upload (CSV/Excel)
    - [ ] Streamlit-based UI for non-technical users
    - [ ] Integration with other project management tools (Jira/Trello)
10. ### 📜 License
    MIT
---



