#  Project Management Shortcuts — Developer Edition

This guide covers **shortcuts and commands** to streamline **project management** — from Git, terminal navigation, Docker, Poetry, and VS Code — all the way to workflow automation.

Each section lists **key shortcuts or commands (10 aspects × 5 each)** to help you switch, manage, and automate projects efficiently.

---

## 1.  Navigation & Context Switching

| Shortcut / Command | Description |
|---------------------|--------------|
| `cd <project_name>` | Move into a project directory. |
| `cd -` | Switch to previous directory. |
| `ls -lh` | List files with readable details. |
| `pwd` | Show current working directory path. |
| `find . -name "*.py"` | Quickly locate files in project. |

---

## 2.  Project Initialization

| Shortcut / Command | Description |
|---------------------|--------------|
| `mkdir <project_name>` | Create new project folder. |
| `git init` | Initialize a Git repository. |
| `poetry init` | Create new Python project with dependencies. |
| `npm init -y` | Initialize Node.js project. |
| `touch README.md` | Create documentation file. |

---

## 3. 🧩 Dependency Management

| Shortcut / Command | Description |
|---------------------|--------------|
| `poetry add <package>` | Add new dependency. |
| `pip install -r requirements.txt` | Install from file. |
| `npm install` | Install Node dependencies. |
| `poetry update` | Update dependencies. |
| `poetry show --tree` | View dependency tree. |

---

## 4. Environment Handling

| Shortcut / Command | Description |
|---------------------|--------------|
| `poetry shell` | Enter project virtual environment. |
| `deactivate` | Exit virtual environment. |
| `conda activate <env_name>` | Activate Conda environment. |
| `python -m venv venv` | Create Python virtual environment. |
| `direnv allow` | Auto-load env vars per directory. |

---

## 5.  Building & Testing

| Shortcut / Command | Description |
|---------------------|--------------|
| `pytest -v` | Run tests with verbose output. |
| `npm test` | Run JavaScript tests. |
| `pytest --maxfail=1 --disable-warnings` | Stop after first test failure. |
| `docker build -t myapp .` | Build Docker image. |
| `docker run -p 8000:8000 myapp` | Run app container locally. |

---

## 6. 🚀 Deployment Shortcuts

| Shortcut / Command | Description |
|---------------------|--------------|
| `vercel deploy` | Deploy locally to Vercel. |
| `docker-compose up -d` | Run multi-container apps. |
| `git push origin main` | Deploy via CI/CD. |
| `gh workflow run deploy.yml` | Trigger GitHub Actions manually. |
| `kubectl apply -f deployment.yaml` | Apply Kubernetes deployment. |

---

## 7.  Version Control & PRs

| Shortcut / Command | Description |
|---------------------|--------------|
| `git checkout -b <feature_branch>` | Create new branch. |
| `git commit -am "message"` | Commit all tracked changes. |
| `git push origin <branch>` | Push branch to GitHub. |
| `gh pr create --fill` | Create pull request. |
| `gh pr view --web` | Open PR in browser. |

---

## 8.  VS Code Productivity

| Shortcut | Description |
|-----------|--------------|
| `Ctrl + Shift + P` | Open Command Palette. |
| `Ctrl + `` | Toggle terminal. |
| `Ctrl + B` | Show/hide sidebar. |
| `Alt + ↑ / ↓` | Move line up/down. |
| `Ctrl + /` | Comment/uncomment code. |

---

## 9. Workflow Automation

| Shortcut / Command | Description |
|---------------------|--------------|
| `make test` | Run predefined test commands. |
| `make deploy` | Simplify deployment steps. |
| `task list` | Show available tasks in Taskfile. |
| `pre-commit run --all-files` | Run Git hooks before commits. |
| `watchmedo auto-restart --pattern="*.py"` | Auto-reload app on changes. |

---

## 10. Cleanup & Maintenance

| Shortcut / Command | Description |
|---------------------|--------------|
| `git clean -fd` | Remove untracked files. |
| `docker system prune -af` | Clean up Docker images/volumes. |
| `poetry cache clear . --all` | Clear Poetry cache. |
| `rm -rf venv/ __pycache__/` | Remove env and cache files. |
| `find . -type f -name "*.log" -delete` | Delete all log files. |

---

## Bonus: Quick Switching Between Projects

| Command / Trick | Description |
|------------------|--------------|
| `cd ~/projects && ls` | View all projects in one folder. |
| `alias proj="cd ~/projects/$1"` | Create alias to jump by project name. |
| `direnv` | Auto-load project env when entering folder. |
| `tmux new -s <project>` | Create project-specific terminal session. |
| `poetry shell` | Auto-spawn environment for current project. |

---

##  Summary

| Category | Focus |
|-----------|--------|
| Navigation | Move easily between projects |
| Initialization | Bootstrap new projects quickly |
| Dependencies | Install/update/manage libraries |
| Environment | Isolate project configs |
| Testing | Run automated tests |
| Deployment | Local & remote deployment |
| Version Control | Manage branches & PRs |
| IDE | Boost coding speed |
| Automation | Simplify repeat tasks |
| Cleanup | Keep workspace clean |

---
