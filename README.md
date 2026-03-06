# Setup Instructions

Reusable setup scripts for creating isolated Python environments for Jupyter notebooks.

# Requirements
Install uv:

**Windows (PowerShell):**
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**macOS/Linux:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```


## Quick Start

1. **Rename this folder** to your project name (e.g., `Dafe1000-Oblig1`)
2. **Setup dependencies:**
   - Copy your course's `pyproject.toml` here, OR
   - Use `pyproject.toml` as a template (last updated 04.02.2026 - check for newer package versions if reading this much later)
   - Edit `pyproject.toml`: update project name, comment out unneeded packages with `#`
3. **Run the setup script:**
   
   **Windows:** `.\setup.ps1`  
   **Linux/Mac:** `chmod +x setup.sh && ./setup.sh`

4. **Reload VS Code:** `Ctrl+Shift+P` → "Reload Window"
5. **Select kernel:** Open notebook → "Select Kernel" → "Python 3 (your-folder-name)"

Done!

## How It Works

- Runs `uv sync` to create `.venv` and install dependencies from `pyproject.toml`
- Registers a Jupyter kernel named after the folder
- Each folder gets its own isolated environment

## Reuse

Copy `setup.ps1`/`setup.sh` and `pyproject.toml` to any new folder, rename the folder, and run the script.


## Troubleshooting

**Kernel not appearing:** Reload VS Code window  
**Script errors:** Check `pyproject.toml` syntax  
**Linux/Mac:** Ensure script is executable: `chmod +x setup.sh`