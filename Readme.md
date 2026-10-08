# Asteroids

A classic 2D Asteroids game built in Python using Pygame and managed with `uv`.

---

## Requirements

* **Python 3.12+** (ensure "Add python.exe to PATH" is checked during installation)
* [uv](https://github.com/astral-sh/uv) package manager

To install `uv` on Windows using PowerShell:
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

---

## Setup & Installation

1. **Open PowerShell or Command Prompt (cmd) and clone the repository:**
   ```cmd
   git clone <your-repository-url>
   cd <repository-folder>
   ```

2. **Sync dependencies and setup environment:**
   Using `uv`:
   ```cmd
   uv sync
   ```

---

## How to Run

Run the game directly with `uv`:

```cmd
uv run python main.py
```

*(Optional) If you prefer running inside a standard virtual environment:*
```powershell
# Activate virtual environment in PowerShell
.\.venv\Scripts\Activate.ps1
python main.py
```

> **Note for PowerShell Users:** If you get a script execution policy error when activating `.venv`, run PowerShell as Administrator once and execute:
> ```powershell
> Set-ExecutionPolicy Unrestricted -Scope Process
> ```

---

## Game Controls

| Action | Key / Control |
| :--- | :--- |
| **Rotate Left** | `A` or `Left Arrow` |
| **Rotate Right** | `D` or `Right Arrow` |
| **Thrust Forward** | `W` or `Up Arrow` |
| **Shoot** | `Spacebar` |

---

## Project Structure

```text
├── main.py            # Main game loop and Pygame initialization
├── constants.py       # Game settings (screen dimensions, speeds, scaling)
├── circleshape.py     # Base class for circular game objects with collision logic
├── player.py          # Ship movement, rotation, and shooting logic
├── asteroid.py        # Individual asteroid behavior and splitting mechanic
├── asteroidfield.py   # Spawner managing waves of asteroids
├── shot.py            # Bullet projectile tracking and lifetime
├── logger.py          # Logging and analytics handler
├── pyproject.toml     # Project configurations and dependency list
├── uv.lock            # Lockfile for consistent environment setups
└── .gitignore         # Windows & Python ignore rules
```
