
# Asteroids Game

A small Asteroids-style game built with Python and Pygame.

## Requirements

- Windows, macOS, or Linux
- Python 3.13 or newer
- A graphical desktop session capable of opening a Pygame window

The required dependency is pinned to `pygame==2.6.1` in `pyproject.toml`.

## Setup

Open a terminal in the directory that contains `main.py` and `pyproject.toml`.

### Windows PowerShell

```powershell
cd path\to\asteroids-game
py -3.13 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install pygame==2.6.1
```

If PowerShell blocks activation, either run the commands below in Command Prompt or allow local scripts for your user account:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Windows Command Prompt

```bat
cd path\to\asteroids-game
py -3.13 -m venv .venv
.venv\Scripts\activate.bat
python -m pip install --upgrade pip
python -m pip install pygame==2.6.1
```

### macOS or Linux

```bash
cd path/to/asteroids-game
python3.13 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install pygame==2.6.1
```

When the virtual environment is active, the terminal prompt normally starts with `.venv`.

## Run the game

From the project directory, with the virtual environment active:

```bash
python main.py
```

The game opens a 1280 x 720 window. Close the window to exit. To leave the virtual environment after playing:

```bash
deactivate
```

## Controls

| Key | Action |
| --- | --- |
| `A` | Rotate counterclockwise |
| `D` | Rotate clockwise |
| `W` | Move forward |
| `S` | Move backward |
| `Space` | Shoot |
| Window close button | Quit |

## Runtime logs

While the game runs, it creates these files in the project directory:

- `game_state.jsonl`: periodic snapshots of the screen and sprites
- `game_events.jsonl`: gameplay events such as hits and asteroid splits

These files are generated at runtime and can be deleted before another run. The state log is sampled for approximately the first 16 seconds of gameplay; event logging continues whenever an event occurs.

## Project files

| File | Purpose |
| --- | --- |
| `main.py` | Initializes Pygame and runs the game loop |
| `player.py` | Player movement, rotation, and shooting |
| `asteroid.py` | Asteroid movement, collisions, and splitting |
| `asteroidfield.py` | Spawns asteroids around the screen edges |
| `shot.py` | Projectile behavior |
| `circleshape.py` | Shared circular sprite behavior |
| `constants.py` | Screen size and gameplay settings |
| `logger.py` | JSONL state and event logging |
| `pyproject.toml` | Project metadata and dependency declaration |

## Troubleshooting

### `No module named pygame`

Make sure the virtual environment is active, then install the dependency again:

```bash
python -m pip install pygame==2.6.1
```

You can verify the installation with:

```bash
python -c "import pygame; print(pygame.version.ver)"
```

### The wrong Python version is used

Check the interpreter selected by the active terminal:

```bash
python --version
```

It should report Python 3.13 or newer. Recreate the environment with the Python 3.13 launcher if necessary.

### The game window does not open

Run the game from a normal desktop terminal rather than a headless session, remote shell without display forwarding, or environment that does not provide a graphical display.

## Fresh setup after cloning

After cloning this repository, change into the directory containing `main.py`, create a new `.venv`, install Pygame, and run `python main.py` using the commands above. No database, API key, external service, or additional asset download is required.
